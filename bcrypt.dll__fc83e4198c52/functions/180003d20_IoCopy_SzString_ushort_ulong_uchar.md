# IoCopy_SzString(ushort *,ulong *,uchar *)

- ea: `0x180003d20`
- end: `0x180003dab`
- name: `?IoCopy_SzString@@YAKPEAGPEAKPEAE@Z`
- size: `139`
- prototype: `unsigned int __fastcall(unsigned __int16 *Src, unsigned int *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000283c`
- `0x180019cbc`

## callees

- `0x180003d20`
- `0x180004120`
- `0x18001b79d`

## pseudocode

```c
unsigned int __fastcall IoCopy_SzString(unsigned __int16 *Src, unsigned int *a2, unsigned __int8 *a3)
{
  unsigned int result; // eax
  unsigned int v7; // edi
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  if ( !Src )
    return 87;
  if ( a2 )
    *a2 = 0;
  result = SzString_CchLength(Src, &v8, 0);
  if ( !result )
  {
    v7 = v8;
    if ( a3 )
      memcpy_0(a3, Src, 2LL * (v8 + 1));
    if ( a2 )
      *a2 = (2 * v7 + 9) & 0xFFFFFFF8;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003d20  mov     [rsp+arg_10], rbx
0x180003d25  mov     [rsp+arg_18], rbp
0x180003d2a  push    rsi
0x180003d2b  sub     rsp, 20h
0x180003d2f  xor     eax, eax
0x180003d31  mov     rbp, r8
0x180003d34  mov     [rsp+28h+arg_0], eax
0x180003d38  mov     rbx, rdx
0x180003d3b  mov     rsi, rcx
0x180003d3e  test    rcx, rcx
0x180003d41  jz      short loc_180003DA4
0x180003d43  test    rdx, rdx
0x180003d46  jz      short loc_180003D4A
0x180003d48  mov     [rdx], eax
0x180003d4a  xor     r8d, r8d; unsigned int
0x180003d4d  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x180003d52  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x180003d57  test    eax, eax
0x180003d59  jnz     short loc_180003D93
0x180003d5b  mov     [rsp+28h+arg_8], rdi
0x180003d60  mov     edi, [rsp+28h+arg_0]
0x180003d64  test    rbp, rbp
0x180003d67  jz      short loc_180003D7B
0x180003d69  lea     r8d, [rdi+1]
0x180003d6d  mov     rdx, rsi; Src
0x180003d70  add     r8, r8; Size
0x180003d73  mov     rcx, rbp; void *
0x180003d76  call    memcpy_0
0x180003d7b  test    rbx, rbx
0x180003d7e  jz      short loc_180003D8C
0x180003d80  lea     eax, ds:9[rdi*2]
0x180003d87  and     eax, 0FFFFFFF8h
0x180003d8a  mov     [rbx], eax
0x180003d8c  mov     rdi, [rsp+28h+arg_8]
0x180003d91  xor     eax, eax
0x180003d93  mov     rbx, [rsp+28h+arg_10]
0x180003d98  mov     rbp, [rsp+28h+arg_18]
0x180003d9d  add     rsp, 20h
0x180003da1  pop     rsi
0x180003da2  retn
0x180003da4  mov     eax, 57h ; 'W'
0x180003da9  jmp     short loc_180003D93
```
