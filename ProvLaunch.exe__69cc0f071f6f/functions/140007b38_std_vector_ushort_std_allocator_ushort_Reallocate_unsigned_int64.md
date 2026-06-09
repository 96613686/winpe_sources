# std::vector<ushort,std::allocator<ushort>>::_Reallocate(unsigned __int64)

- ea: `0x140007b38`
- end: `0x140007bd1`
- name: `?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z`
- size: `153`
- prototype: `char *__fastcall(__int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140006e18`
- `0x140007e3c`
- `0x140008a2c`
- `0x1400090ec`

## callees

- `0x140001864`
- `0x140007b38`
- `0x14000a332`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140007b72`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140007b72`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007bae`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007bae`

## pseudocode

```c
char *__fastcall std::vector<unsigned short>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  __int64 v3; // r14
  char *v4; // rax
  char *v5; // rbx
  void *v6; // rcx
  __int64 v7; // rsi
  char *result; // rax
  char *v9; // [rsp+58h] [rbp+10h]

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFFFFFFFFFFLL || (v3 = 2 * a2, v4 = (char *)operator new(2 * a2), v5 = v4, (v9 = v4) == 0) )
    {
      std::_Xbad_alloc();
      __debugbreak();
    }
  }
  else
  {
    v5 = 0;
    v9 = 0;
    v3 = 0;
  }
  try
  {
    memmove_0(v5, *(const void **)a1, 2 * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1));
    v6 = *(void **)a1;
    v7 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1;
    if ( *(_QWORD *)a1 )
      operator delete(v6);
    *(_QWORD *)(a1 + 16) = &v5[v3];
    result = &v5[2 * v7];
    *(_QWORD *)(a1 + 8) = result;
    *(_QWORD *)a1 = v5;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v6, v9);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x140007b38  push    rbx
0x140007b3a  push    rsi
0x140007b3b  push    rdi
0x140007b3c  push    r14
0x140007b3e  sub     rsp, 28h
0x140007b42  mov     rdi, rcx
0x140007b45  test    rdx, rdx
0x140007b48  jz      short loc_140007B79
0x140007b4a  mov     rax, 7FFFFFFFFFFFFFFFh
0x140007b54  cmp     rdx, rax
0x140007b57  ja      short loc_140007B72
0x140007b59  lea     r14, [rdx+rdx]
0x140007b5d  mov     rcx, r14; Size
0x140007b60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007b65  mov     rbx, rax
0x140007b68  mov     [rsp+48h+arg_8], rax
0x140007b6d  test    rax, rax
0x140007b70  jnz     short loc_140007B83
0x140007b72  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140007b78  int     3; Trap to Debugger
0x140007b79  xor     ebx, ebx
0x140007b7b  mov     [rsp+48h+arg_8], rbx
0x140007b80  xor     r14d, r14d
0x140007b83  mov     r8, [rdi+8]
0x140007b87  sub     r8, [rdi]
0x140007b8a  sar     r8, 1
0x140007b8d  add     r8, r8; Size
0x140007b90  mov     rdx, [rdi]; Src
0x140007b93  mov     rcx, rbx; void *
0x140007b96  call    memmove_0
0x140007b9b  nop
0x140007b9c  mov     rcx, [rdi]
0x140007b9f  mov     rsi, [rdi+8]
0x140007ba3  sub     rsi, rcx
0x140007ba6  sar     rsi, 1
0x140007ba9  test    rcx, rcx
0x140007bac  jz      short loc_140007BB4
0x140007bae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140007bb4  lea     rax, [r14+rbx]
0x140007bb8  mov     [rdi+10h], rax
0x140007bbc  lea     rax, [rbx+rsi*2]
0x140007bc0  mov     [rdi+8], rax
0x140007bc4  mov     [rdi], rbx
0x140007bc7  add     rsp, 28h
0x140007bcb  pop     r14
0x140007bcd  pop     rdi
0x140007bce  pop     rsi
0x140007bcf  pop     rbx
0x140007bd0  retn
```
