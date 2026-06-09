# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(void)

- ea: `0x18000e148`
- end: `0x18000e1c5`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000eb20`

## callees

- `0x180001894`
- `0x18000c564`
- `0x18000e148`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rdi
  _QWORD *v3; // rbx
  void *v4; // rcx
  void *v5; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = *(_QWORD **)(*(_QWORD *)(v1 + 40) + 8LL);
    while ( !*((_BYTE *)v3 + 25) )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(
        v1 + 40,
        v1 + 40,
        v3[2]);
      v4 = v3;
      v3 = (_QWORD *)*v3;
      operator delete(v4);
    }
    operator delete(*(void **)(v1 + 40));
  }
  v5 = *(void **)(a1 + 8);
  if ( v5 )
    operator delete(v5);
}

```

## disassembly

```asm
0x18000e148  mov     [rsp+arg_0], rbx
0x18000e14d  mov     [rsp+arg_8], rsi
0x18000e152  push    rdi
0x18000e153  sub     rsp, 20h
0x18000e157  mov     rdi, [rcx+8]
0x18000e15b  mov     rsi, rcx
0x18000e15e  test    rdi, rdi
0x18000e161  jz      short loc_18000E1A2
0x18000e163  mov     rax, [rdi+28h]
0x18000e167  mov     rbx, [rax+8]
0x18000e16b  jmp     short loc_18000E18E
0x18000e16d  mov     r8, [rbx+10h]
0x18000e171  lea     rdx, [rdi+28h]
0x18000e175  lea     rcx, [rdi+28h]
0x18000e179  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x18000e17e  mov     rcx, rbx; Block
0x18000e181  mov     edx, 30h ; '0'
0x18000e186  mov     rbx, [rbx]
0x18000e189  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e18e  cmp     byte ptr [rbx+19h], 0
0x18000e192  jz      short loc_18000E16D
0x18000e194  mov     rcx, [rdi+28h]; Block
0x18000e198  mov     edx, 30h ; '0'
0x18000e19d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e1a2  mov     rcx, [rsi+8]; Block
0x18000e1a6  test    rcx, rcx
0x18000e1a9  jz      short loc_18000E1B5
0x18000e1ab  mov     edx, 38h ; '8'
0x18000e1b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e1b5  mov     rbx, [rsp+28h+arg_0]
0x18000e1ba  mov     rsi, [rsp+28h+arg_8]
0x18000e1bf  add     rsp, 20h
0x18000e1c3  pop     rdi
0x18000e1c4  retn
```
