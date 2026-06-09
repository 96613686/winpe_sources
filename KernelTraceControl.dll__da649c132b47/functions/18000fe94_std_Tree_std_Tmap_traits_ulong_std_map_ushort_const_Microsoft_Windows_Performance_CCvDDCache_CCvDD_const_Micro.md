# std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Buynode(void)

- ea: `0x18000fe94`
- end: `0x18000fee2`
- name: `?_Buynode@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@2@XZ`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800098d0`

## callees

- `0x18000fe94`
- `0x18002687c`

## pseudocode

```c
_QWORD *std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Buynode()
{
  _QWORD *result; // rax
  _QWORD *v1; // rcx

  result = operator new(0x40u);
  try
  {
    if ( result )
      *result = 0;
    if ( result != (_QWORD *)-8LL )
      result[1] = 0;
    v1 = result + 2;
    if ( result != (_QWORD *)-16LL )
      *v1 = 0;
  }
  catch ( ... )
  {
    std::allocator<unsigned int>::deallocate(v1, result);
    throw;
  }
  *((_WORD *)result + 28) = 1;
  return result;
}

```

## disassembly

```asm
0x18000fe94  mov     [rsp+arg_0], rcx
0x18000fe99  sub     rsp, 38h
0x18000fe9d  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000fea6  mov     ecx, 40h ; '@'; Size
0x18000feab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000feb0  mov     [rsp+38h+arg_0], rax
0x18000feb5  xor     edx, edx
0x18000feb7  test    rax, rax
0x18000feba  jz      short loc_18000FEBF
0x18000febc  mov     [rax], rdx
0x18000febf  lea     rcx, [rax+8]
0x18000fec3  test    rcx, rcx
0x18000fec6  jz      short loc_18000FECB
0x18000fec8  mov     [rcx], rdx
0x18000fecb  lea     rcx, [rax+10h]
0x18000fecf  test    rcx, rcx
0x18000fed2  jz      short loc_18000FED7
0x18000fed4  mov     [rcx], rdx
0x18000fed7  mov     word ptr [rax+38h], 1
0x18000fedd  add     rsp, 38h
0x18000fee1  retn
```
