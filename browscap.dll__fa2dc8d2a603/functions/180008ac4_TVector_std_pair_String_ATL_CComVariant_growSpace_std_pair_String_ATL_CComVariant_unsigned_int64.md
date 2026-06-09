# TVector<std::pair<String,ATL::CComVariant>>::growSpace(std::pair<String,ATL::CComVariant> * &,unsigned __int64)

- ea: `0x180008ac4`
- end: `0x180008bbb`
- name: `?growSpace@?$TVector@U?$pair@VString@@VCComVariant@ATL@@@std@@@@AEAAXAEAPEAU?$pair@VString@@VCComVariant@ATL@@@std@@_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007570`

## callees

- `0x180008ac4`
- `0x1800099f8`
- `0x18000b602`

## import_xrefs

- `msvcrt!free` at `0x180008b87`
- `msvcrt!free` at `0x180008b87`

## pseudocode

```c
__int64 __fastcall TVector<std::pair<String,ATL::CComVariant>>::growSpace(unsigned __int64 *a1, _QWORD *a2)
{
  __int64 v4; // r14
  __int64 v5; // r15
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rax
  char *v9; // rsi
  void *v10; // rcx
  __int64 result; // rax

  v4 = (__int64)(*a2 - a1[1]) / 40;
  v5 = (__int64)(a1[2] - a1[1]) / 40;
  v6 = *a1;
  if ( *a1 )
  {
    v7 = 2 * v6;
    v8 = v6 + 1;
    while ( v7 < v8 )
      v7 *= 2LL;
  }
  else
  {
    v7 = 64;
  }
  v9 = (char *)operator new(40 * v7);
  memmove_0(v9, (const void *)a1[1], 40 * ((__int64)(a1[2] - a1[1]) / 40));
  v10 = (void *)a1[1];
  if ( v10 )
    free(v10);
  *a1 = v7;
  a1[1] = (unsigned __int64)v9;
  a1[2] = (unsigned __int64)&v9[40 * v5];
  result = 5 * v4;
  *a2 = &v9[40 * v4];
  return result;
}

```

## disassembly

```asm
0x180008ac4  push    rbx
0x180008ac6  push    rbp
0x180008ac7  push    rsi
0x180008ac8  push    rdi
0x180008ac9  push    r12
0x180008acb  push    r14
0x180008acd  push    r15
0x180008acf  sub     rsp, 20h
0x180008ad3  mov     r8, [rdx]
0x180008ad6  mov     rdi, rcx
0x180008ad9  sub     r8, [rcx+8]
0x180008add  mov     r12, 6666666666666667h
0x180008ae7  mov     rcx, [rcx+10h]
0x180008aeb  mov     rbp, rdx
0x180008aee  mov     rax, r12
0x180008af1  sub     rcx, [rdi+8]
0x180008af5  imul    r8
0x180008af8  mov     r14, rdx
0x180008afb  sar     r14, 4
0x180008aff  mov     rax, r14
0x180008b02  shr     rax, 3Fh
0x180008b06  add     r14, rax
0x180008b09  mov     rax, r12
0x180008b0c  imul    rcx
0x180008b0f  mov     r15, rdx
0x180008b12  sar     r15, 4
0x180008b16  mov     rax, r15
0x180008b19  shr     rax, 3Fh
0x180008b1d  add     r15, rax
0x180008b20  mov     rax, [rdi]
0x180008b23  test    rax, rax
0x180008b26  jnz     short loc_180008B2D
0x180008b28  lea     ebx, [rax+40h]
0x180008b2b  jmp     short loc_180008B3E
0x180008b2d  lea     rbx, [rax+rax]
0x180008b31  inc     rax
0x180008b34  jmp     short loc_180008B39
0x180008b36  add     rbx, rbx
0x180008b39  cmp     rbx, rax
0x180008b3c  jb      short loc_180008B36
0x180008b3e  lea     rcx, [rbx+rbx*4]
0x180008b42  shl     rcx, 3; unsigned __int64
0x180008b46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008b4b  mov     rcx, [rdi+10h]
0x180008b4f  mov     rsi, rax
0x180008b52  sub     rcx, [rdi+8]
0x180008b56  mov     rax, r12
0x180008b59  imul    rcx
0x180008b5c  sar     rdx, 4
0x180008b60  mov     rcx, rdx
0x180008b63  shr     rcx, 3Fh
0x180008b67  add     rdx, rcx
0x180008b6a  mov     rcx, rsi; void *
0x180008b6d  lea     r8, [rdx+rdx*4]
0x180008b71  mov     rdx, [rdi+8]; Src
0x180008b75  shl     r8, 3; Size
0x180008b79  call    memmove_0
0x180008b7e  mov     rcx, [rdi+8]; Block
0x180008b82  test    rcx, rcx
0x180008b85  jz      short loc_180008B8D
0x180008b87  call    cs:__imp_free
0x180008b8d  lea     rax, [r15+r15*4]
0x180008b91  mov     [rdi], rbx
0x180008b94  lea     rcx, [rsi+rax*8]
0x180008b98  mov     [rdi+8], rsi
0x180008b9c  mov     [rdi+10h], rcx
0x180008ba0  lea     rax, [r14+r14*4]
0x180008ba4  lea     rcx, [rsi+rax*8]
0x180008ba8  mov     [rbp+0], rcx
0x180008bac  add     rsp, 20h
0x180008bb0  pop     r15
0x180008bb2  pop     r14
0x180008bb4  pop     r12
0x180008bb6  pop     rdi
0x180008bb7  pop     rsi
0x180008bb8  pop     rbp
0x180008bb9  pop     rbx
0x180008bba  retn
```
