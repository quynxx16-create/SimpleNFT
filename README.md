# SimpleNFT
SimpleNFT.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract SimpleNFT {
    string public name = "SimpleNFT";
    string public symbol = "SNFT";
    
    mapping(uint256 => address) public ownerOf;
    mapping(address => uint256) public balanceOf;
    
    uint256 public totalSupply;

    event Transfer(address indexed from, address indexed to, uint256 tokenId);

    function mint() public {
        uint256 tokenId = totalSupply;
        ownerOf[tokenId] = msg.sender;
        balanceOf[msg.sender]++;
        totalSupply++;
        
        emit Transfer(address(0), msg.sender, tokenId);
    }
}
