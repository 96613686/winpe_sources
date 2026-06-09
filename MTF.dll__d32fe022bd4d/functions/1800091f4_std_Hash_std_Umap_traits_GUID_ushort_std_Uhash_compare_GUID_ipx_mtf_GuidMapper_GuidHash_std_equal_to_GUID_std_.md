# std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::~_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>(void)

- ea: `0x1800091f4`
- end: `0x180009262`
- name: `??1?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@QEAA@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002e130`

## callees

- `0x1800091f4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000920c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009240`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000920c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009240`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000925b`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::~_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>(
        __int64 a1)
{
  void *v2; // rcx
  _QWORD *v3; // rdx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  v2 = *(void **)(a1 + 16);
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 32) = 0;
  }
  v3 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  v4 = *(_QWORD **)a1;
  *(_QWORD *)(a1 + 8) = 0;
  if ( v3 != v4 )
  {
    do
    {
      v5 = (_QWORD *)*v3;
      operator delete(v3);
      v4 = *(_QWORD **)a1;
      v3 = v5;
    }
    while ( v5 != *(_QWORD **)a1 );
  }
  operator delete(v4);
}

```

## disassembly

```asm
0x1800091f4  mov     [rsp+arg_0], rbx
0x1800091f9  push    rdi
0x1800091fa  sub     rsp, 20h
0x1800091fe  mov     rdi, rcx
0x180009201  xor     ebx, ebx
0x180009203  mov     rcx, [rcx+10h]
0x180009207  test    rcx, rcx
0x18000920a  jz      short loc_18000921E
0x18000920c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009212  mov     [rdi+10h], rbx
0x180009216  mov     [rdi+18h], rbx
0x18000921a  mov     [rdi+20h], rbx
0x18000921e  mov     rax, [rdi]
0x180009221  mov     rdx, [rax]
0x180009224  mov     [rax], rax
0x180009227  mov     rax, [rdi]
0x18000922a  mov     [rax+8], rax
0x18000922e  mov     rcx, [rdi]
0x180009231  mov     [rdi+8], rbx
0x180009235  cmp     rdx, rcx
0x180009238  jz      short loc_180009251
0x18000923a  mov     rbx, [rdx]
0x18000923d  mov     rcx, rdx
0x180009240  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009246  mov     rcx, [rdi]
0x180009249  mov     rdx, rbx
0x18000924c  cmp     rbx, rcx
0x18000924f  jnz     short loc_18000923A
0x180009251  mov     rbx, [rsp+28h+arg_0]
0x180009256  add     rsp, 20h
0x18000925a  pop     rdi
0x18000925b  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
