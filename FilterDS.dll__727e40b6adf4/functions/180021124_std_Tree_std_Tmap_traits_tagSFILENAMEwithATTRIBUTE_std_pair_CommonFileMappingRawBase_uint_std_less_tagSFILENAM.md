# std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::_Erase(std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *)

- ea: `0x180021124`
- end: `0x18002119a`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@@Z`
- size: `118`
- prototype: `void __fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020cb4`
- `0x180021124`

## callees

- `0x180021124`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002115c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002117b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002115c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002117b`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::_Erase(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rbx
  __int64 *i; // rdi

  v2 = a2;
  for ( i = a2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::_Erase(
      a1,
      i[2]);
    i = (__int64 *)*i;
    if ( (unsigned __int64)v2[7] >= 8 )
      operator delete((void *)v2[4]);
    v2[7] = 7;
    v2[6] = 0;
    *((_WORD *)v2 + 16) = 0;
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x180021124  mov     [rsp+arg_0], rbx
0x180021129  mov     [rsp+arg_8], rsi
0x18002112e  push    rdi
0x18002112f  sub     rsp, 20h
0x180021133  cmp     byte ptr [rdx+19h], 0
0x180021137  mov     rbx, rdx
0x18002113a  mov     rsi, rcx
0x18002113d  mov     rdi, rdx
0x180021140  jnz     short loc_18002118A
0x180021142  mov     rdx, [rdi+10h]
0x180021146  mov     rcx, rsi
0x180021149  call    ?_Erase@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::_Erase(std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *)
0x18002114e  cmp     qword ptr [rbx+38h], 8
0x180021153  mov     rdi, [rdi]
0x180021156  jb      short loc_180021162
0x180021158  mov     rcx, [rbx+20h]
0x18002115c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180021162  xor     eax, eax
0x180021164  mov     qword ptr [rbx+38h], 7
0x18002116c  mov     qword ptr [rbx+30h], 0
0x180021174  mov     rcx, rbx
0x180021177  mov     [rbx+20h], ax
0x18002117b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180021181  cmp     byte ptr [rdi+19h], 0
0x180021185  mov     rbx, rdi
0x180021188  jz      short loc_180021142
0x18002118a  mov     rbx, [rsp+28h+arg_0]
0x18002118f  mov     rsi, [rsp+28h+arg_8]
0x180021194  add     rsp, 20h
0x180021198  pop     rdi
0x180021199  retn
```
