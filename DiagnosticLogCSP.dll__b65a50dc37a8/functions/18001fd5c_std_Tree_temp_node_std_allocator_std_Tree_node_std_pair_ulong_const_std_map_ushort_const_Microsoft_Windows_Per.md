# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(void)

- ea: `0x18001fd5c`
- end: `0x18001fdda`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020760`

## callees

- `0x180001bf8`
- `0x18001e41c`
- `0x18001fd5c`

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
0x18001fd5c  mov     [rsp+arg_0], rbx
0x18001fd61  mov     [rsp+arg_8], rsi
0x18001fd66  push    rdi
0x18001fd67  sub     rsp, 20h
0x18001fd6b  mov     rdi, [rcx+8]
0x18001fd6f  mov     rsi, rcx
0x18001fd72  test    rdi, rdi
0x18001fd75  jz      short loc_18001FDB6
0x18001fd77  mov     rax, [rdi+28h]
0x18001fd7b  mov     rbx, [rax+8]
0x18001fd7f  jmp     short loc_18001FDA2
0x18001fd81  mov     r8, [rbx+10h]
0x18001fd85  lea     rdx, [rdi+28h]
0x18001fd89  lea     rcx, [rdi+28h]
0x18001fd8d  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x18001fd92  mov     rcx, rbx; void *
0x18001fd95  mov     edx, 30h ; '0'; unsigned __int64
0x18001fd9a  mov     rbx, [rbx]
0x18001fd9d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fda2  cmp     byte ptr [rbx+19h], 0
0x18001fda6  jz      short loc_18001FD81
0x18001fda8  mov     rcx, [rdi+28h]; void *
0x18001fdac  mov     edx, 30h ; '0'; unsigned __int64
0x18001fdb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fdb6  mov     rcx, [rsi+8]; void *
0x18001fdba  test    rcx, rcx
0x18001fdbd  jz      short loc_18001FDC9
0x18001fdbf  mov     edx, 38h ; '8'; unsigned __int64
0x18001fdc4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fdc9  mov     rbx, [rsp+28h+arg_0]
0x18001fdce  mov     rsi, [rsp+28h+arg_8]
0x18001fdd3  add     rsp, 20h
0x18001fdd7  pop     rdi
0x18001fdd8  retn
```
