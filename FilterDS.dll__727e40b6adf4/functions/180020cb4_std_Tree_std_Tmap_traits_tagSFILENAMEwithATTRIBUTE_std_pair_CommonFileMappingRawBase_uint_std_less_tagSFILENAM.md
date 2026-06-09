# std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::~_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>(void)

- ea: `0x180020cb4`
- end: `0x180020d53`
- name: `??1?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023b90`

## callees

- `0x180020cb4`
- `0x180021124`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180020cf0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020d0f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020cf0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020d0f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020d4c`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::~_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>(
        void **a1)
{
  __int64 *v2; // rdi
  __int64 *i; // rsi

  v2 = (__int64 *)*((_QWORD *)*a1 + 1);
  for ( i = v2; !*((_BYTE *)i + 25); v2 = i )
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
  *((_QWORD *)*a1 + 1) = *a1;
  *(_QWORD *)*a1 = *a1;
  *((_QWORD *)*a1 + 2) = *a1;
  a1[1] = 0;
  operator delete(*a1);
}

```

## disassembly

```asm
0x180020cb4  mov     [rsp+arg_0], rbx
0x180020cb9  mov     [rsp+arg_8], rsi
0x180020cbe  push    rdi
0x180020cbf  sub     rsp, 20h
0x180020cc3  mov     rbx, rcx
0x180020cc6  mov     rax, [rcx]
0x180020cc9  mov     rdi, [rax+8]
0x180020ccd  mov     rsi, rdi
0x180020cd0  cmp     byte ptr [rdi+19h], 0
0x180020cd4  jnz     short loc_180020D1E
0x180020cd6  mov     rdx, [rsi+10h]
0x180020cda  mov     rcx, rbx
0x180020cdd  call    ?_Erase@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::_Erase(std::_Tree_node<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,void *> *)
0x180020ce2  mov     rsi, [rsi]
0x180020ce5  cmp     qword ptr [rdi+38h], 8
0x180020cea  jb      short loc_180020CF6
0x180020cec  mov     rcx, [rdi+20h]
0x180020cf0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020cf6  mov     qword ptr [rdi+38h], 7
0x180020cfe  mov     qword ptr [rdi+30h], 0
0x180020d06  xor     eax, eax
0x180020d08  mov     [rdi+20h], ax
0x180020d0c  mov     rcx, rdi
0x180020d0f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020d15  mov     rdi, rsi
0x180020d18  cmp     byte ptr [rsi+19h], 0
0x180020d1c  jz      short loc_180020CD6
0x180020d1e  mov     rax, [rbx]
0x180020d21  mov     [rax+8], rax
0x180020d25  mov     rax, [rbx]
0x180020d28  mov     [rax], rax
0x180020d2b  mov     rax, [rbx]
0x180020d2e  mov     [rax+10h], rax
0x180020d32  mov     qword ptr [rbx+8], 0
0x180020d3a  mov     rcx, [rbx]
0x180020d3d  mov     rbx, [rsp+28h+arg_0]
0x180020d42  mov     rsi, [rsp+28h+arg_8]
0x180020d47  add     rsp, 20h
0x180020d4b  pop     rdi
0x180020d4c  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
