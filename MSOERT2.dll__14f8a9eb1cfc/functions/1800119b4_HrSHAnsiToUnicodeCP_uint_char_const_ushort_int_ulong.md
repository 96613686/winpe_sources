# HrSHAnsiToUnicodeCP(uint,char const *,ushort *,int,ulong *)

- ea: `0x1800119b4`
- end: `0x180011a6f`
- name: `?HrSHAnsiToUnicodeCP@@YAJIPEBDPEAGHPEAK@Z`
- size: `187`
- prototype: `int(unsigned int, const char *, unsigned __int16 *, int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009a50`
- `0x180011fec`

## callees

- `0x1800119b4`
- `0x18001240c`
- `0x180012f8e`

## pseudocode

```c
__int64 __fastcall HrSHAnsiToUnicodeCP(unsigned int a1, const char *a2, unsigned __int16 *a3, int a4, unsigned int *a5)
{
  __int64 v5; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rbx
  __int64 v9; // r8

  v5 = a4;
  v7 = -2147024809;
  if ( a2 && a3 && a4 && a5 )
  {
    v8 = -1;
    *a3 = 0;
    v9 = -1;
    *a5 = 0;
    do
      ++v9;
    while ( a2[v9] );
    if ( !OESHAnsiToUnicodeNativeCP(a1, a2, v9 + 1, a3, a4) )
    {
      v7 = -2147467259;
      goto LABEL_13;
    }
    do
      ++v8;
    while ( a3[v8] );
    if ( (int)v8 + 10 > (int)v5 )
    {
      v7 = -2147024774;
LABEL_13:
      memset_0(a3, 0, 2 * v5);
      return v7;
    }
    memset_0(&a3[(unsigned int)v8], 0, 2LL * (unsigned int)(v5 - v8));
    *a5 = v8;
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800119b4  push    rbx
0x1800119b6  push    rbp
0x1800119b7  push    rsi
0x1800119b8  push    rdi
0x1800119b9  push    r14
0x1800119bb  sub     rsp, 30h
0x1800119bf  xor     ebp, ebp
0x1800119c1  movsxd  rdi, r9d
0x1800119c4  mov     rsi, r8
0x1800119c7  mov     ebx, 80070057h
0x1800119cc  test    rdx, rdx
0x1800119cf  jz      loc_180011A62
0x1800119d5  test    r8, r8
0x1800119d8  jz      loc_180011A62
0x1800119de  test    r9d, r9d
0x1800119e1  jz      short loc_180011A62
0x1800119e3  mov     r14, [rsp+58h+arg_20]
0x1800119eb  test    r14, r14
0x1800119ee  jz      short loc_180011A62
0x1800119f0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800119f4  mov     [r8], bp
0x1800119f8  mov     r8, rbx
0x1800119fb  mov     [r14], ebp
0x1800119fe  inc     r8
0x180011a01  cmp     [rdx+r8], bpl
0x180011a05  jnz     short loc_1800119FE
0x180011a07  inc     r8d; int
0x180011a0a  mov     [rsp+58h+var_38], edi; int
0x180011a0e  mov     r9, rsi; unsigned __int16 *
0x180011a11  call    ?OESHAnsiToUnicodeNativeCP@@YAHIPEBDHPEAGH@Z; OESHAnsiToUnicodeNativeCP(uint,char const *,int,ushort *,int)
0x180011a16  test    eax, eax
0x180011a18  jz      short loc_180011A4D
0x180011a1a  inc     rbx
0x180011a1d  cmp     [rsi+rbx*2], bp
0x180011a21  jnz     short loc_180011A1A
0x180011a23  lea     eax, [rbx+0Ah]
0x180011a26  cmp     eax, edi
0x180011a28  jle     short loc_180011A31
0x180011a2a  mov     ebx, 8007007Ah
0x180011a2f  jmp     short loc_180011A52
0x180011a31  mov     eax, ebx
0x180011a33  sub     edi, ebx
0x180011a35  mov     r8d, edi
0x180011a38  xor     edx, edx; Val
0x180011a3a  add     r8, r8; Size
0x180011a3d  lea     rcx, [rsi+rax*2]; void *
0x180011a41  call    memset_0
0x180011a46  mov     [r14], ebx
0x180011a49  mov     ebx, ebp
0x180011a4b  jmp     short loc_180011A62
0x180011a4d  mov     ebx, 80004005h
0x180011a52  mov     r8, rdi
0x180011a55  xor     edx, edx; Val
0x180011a57  add     r8, r8; Size
0x180011a5a  mov     rcx, rsi; void *
0x180011a5d  call    memset_0
0x180011a62  mov     eax, ebx
0x180011a64  add     rsp, 30h
0x180011a68  pop     r14
0x180011a6a  pop     rdi
0x180011a6b  pop     rsi
0x180011a6c  pop     rbp
0x180011a6d  pop     rbx
0x180011a6e  retn
```
