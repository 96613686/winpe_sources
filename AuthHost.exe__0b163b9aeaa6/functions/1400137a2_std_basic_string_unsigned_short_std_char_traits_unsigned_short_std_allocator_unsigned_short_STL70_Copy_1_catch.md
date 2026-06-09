# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch$3

- ea: `0x1400137a2`
- end: `0x140013842`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch$3`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400029d3`
- `0x140012d10`
- `0x1400137a2`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1400137e8`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1400137e8`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  unsigned __int64 v4; // rcx

  v3 = *(_QWORD *)(a2 + 152);
  *(_QWORD *)(a2 + 168) = v3;
  v4 = v3 + 1;
  if ( v4 && 0xFFFFFFFFFFFFFFFFuLL / v4 < 2 )
  {
    *(_QWORD *)(a2 + 152) = 0;
    exception::exception((exception *)(a2 + 56), (const char *const *)(a2 + 152));
    *(_QWORD *)(a2 + 56) = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)(a2 + 56);
  }
  *(_QWORD *)(a2 + 152) = 0;
  Common::GlobalHeap::Alloc((ReservedForLocalUse *)(2 * v4), (void **)(a2 + 152));
  *(_QWORD *)(a2 + 152) = *(_QWORD *)(a2 + 152);
  return 0;
}

```

## disassembly

```asm
0x1400137a2  mov     [rsp+arg_8], rdx
0x1400137a7  push    rbp
0x1400137a8  sub     rsp, 20h
0x1400137ac  mov     rbp, rdx
0x1400137af  mov     rcx, [rbp+98h]
0x1400137b6  mov     [rbp+0A8h], rcx
0x1400137bd  add     rcx, 1
0x1400137c1  jz      short loc_140013809
0x1400137c3  xor     edx, edx
0x1400137c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400137c9  div     rcx
0x1400137cc  cmp     rax, 2
0x1400137d0  jnb     short loc_140013809
0x1400137d2  mov     qword ptr [rbp+98h], 0
0x1400137dd  lea     rdx, [rbp+98h]
0x1400137e4  lea     rcx, [rbp+38h]
0x1400137e8  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x1400137ee  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1400137f5  mov     [rbp+38h], rax
0x1400137f9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x140013800  lea     rcx, [rbp+38h]; pExceptionObject
0x140013804  call    _CxxThrowException_0
0x140013809  mov     qword ptr [rbp+98h], 0
0x140013814  add     rcx, rcx; unsigned __int64
0x140013817  lea     rdx, [rbp+98h]; void **
0x14001381e  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x140013823  mov     rax, [rbp+98h]
0x14001382a  mov     [rbp+98h], rax
0x140013831  mov     rax, 0
0x14001383b  add     rsp, 20h
0x14001383f  pop     rbp
0x140013840  retn
```
