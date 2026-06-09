# std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *)

- ea: `0x1800210e0`
- end: `0x18002111b`
- name: `?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@@Z`
- size: `59`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800203f8`
- `0x1800238e2`

## callees

- `0x1800210e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800210f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800210f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180021114`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::_Destroy_if_not_nil(
        __int64 a1,
        __int64 a2)
{
  if ( *(_QWORD *)(a2 + 56) >= 8u )
    operator delete(*(void **)(a2 + 32));
  *(_QWORD *)(a2 + 56) = 7;
  *(_QWORD *)(a2 + 48) = 0;
  *(_WORD *)(a2 + 32) = 0;
  operator delete((void *)a2);
}

```

## disassembly

```asm
0x1800210e0  push    rbx
0x1800210e2  sub     rsp, 20h
0x1800210e6  cmp     qword ptr [rdx+38h], 8
0x1800210eb  mov     rbx, rdx
0x1800210ee  jb      short loc_1800210FA
0x1800210f0  mov     rcx, [rdx+20h]
0x1800210f4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800210fa  xor     eax, eax
0x1800210fc  mov     qword ptr [rbx+38h], 7
0x180021104  mov     [rbx+30h], rax
0x180021108  mov     rcx, rbx
0x18002110b  mov     [rbx+20h], ax
0x18002110f  add     rsp, 20h
0x180021113  pop     rbx
0x180021114  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
