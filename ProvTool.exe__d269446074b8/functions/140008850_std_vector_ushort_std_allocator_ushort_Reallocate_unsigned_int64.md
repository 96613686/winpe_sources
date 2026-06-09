# std::vector<ushort,std::allocator<ushort>>::_Reallocate(unsigned __int64)

- ea: `0x140008850`
- end: `0x1400088e9`
- name: `?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z`
- size: `153`
- prototype: `char *__fastcall(__int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140003598`
- `0x14000a780`
- `0x14000b250`
- `0x14000b454`

## callees

- `0x140001674`
- `0x140008850`
- `0x14000de92`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000888a`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000888a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400088c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400088c6`

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
0x140008850  push    rbx
0x140008852  push    rsi
0x140008853  push    rdi
0x140008854  push    r14
0x140008856  sub     rsp, 28h
0x14000885a  mov     rdi, rcx
0x14000885d  test    rdx, rdx
0x140008860  jz      short loc_140008891
0x140008862  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000886c  cmp     rdx, rax
0x14000886f  ja      short loc_14000888A
0x140008871  lea     r14, [rdx+rdx]
0x140008875  mov     rcx, r14; Size
0x140008878  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000887d  mov     rbx, rax
0x140008880  mov     [rsp+48h+arg_8], rax
0x140008885  test    rax, rax
0x140008888  jnz     short loc_14000889B
0x14000888a  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140008890  int     3; Trap to Debugger
0x140008891  xor     ebx, ebx
0x140008893  mov     [rsp+48h+arg_8], rbx
0x140008898  xor     r14d, r14d
0x14000889b  mov     r8, [rdi+8]
0x14000889f  sub     r8, [rdi]
0x1400088a2  sar     r8, 1
0x1400088a5  add     r8, r8; Size
0x1400088a8  mov     rdx, [rdi]; Src
0x1400088ab  mov     rcx, rbx; void *
0x1400088ae  call    memmove_0
0x1400088b3  nop
0x1400088b4  mov     rcx, [rdi]
0x1400088b7  mov     rsi, [rdi+8]
0x1400088bb  sub     rsi, rcx
0x1400088be  sar     rsi, 1
0x1400088c1  test    rcx, rcx
0x1400088c4  jz      short loc_1400088CC
0x1400088c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400088cc  lea     rax, [r14+rbx]
0x1400088d0  mov     [rdi+10h], rax
0x1400088d4  lea     rax, [rbx+rsi*2]
0x1400088d8  mov     [rdi+8], rax
0x1400088dc  mov     [rdi], rbx
0x1400088df  add     rsp, 28h
0x1400088e3  pop     r14
0x1400088e5  pop     rdi
0x1400088e6  pop     rsi
0x1400088e7  pop     rbx
0x1400088e8  retn
```
