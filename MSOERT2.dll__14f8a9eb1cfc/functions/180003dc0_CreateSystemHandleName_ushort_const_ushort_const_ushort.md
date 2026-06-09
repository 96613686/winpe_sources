# CreateSystemHandleName(ushort const *,ushort const *,ushort * *)

- ea: `0x180003dc0`
- end: `0x180003e73`
- name: `?CreateSystemHandleName@@YAJPEBG0PEAPEAG@Z`
- size: `179`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003f80`

## callees

- `0x180001f50`
- `0x180003dc0`
- `0x18000470c`
- `0x18000ff30`

## import_xrefs

- `USER32!CharLowerW` at `0x180003e60`
- `USER32!CharLowerW` at `0x180003e60`

## pseudocode

```c
__int64 __fastcall CreateSystemHandleName(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v3; // rax
  __int64 v7; // r9
  unsigned int v8; // esi
  unsigned __int16 *v9; // rax
  int v10; // ebx

  v3 = -1;
  *a3 = 0;
  if ( a1 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a1[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  if ( a2 )
  {
    do
      ++v3;
    while ( a2[v3] );
  }
  else
  {
    LODWORD(v3) = 0;
  }
  v8 = v7 + v3 + 30;
  v9 = (unsigned __int16 *)PszAllocW(v8, (__int64)a2);
  *a3 = v9;
  if ( v9 )
  {
    v10 = StringCchPrintfW(v9, v8, L"Local\\%s%s", a1, a2);
    if ( v10 >= 0 )
      ReplaceCharsW(*a3 + 6, 92, 95);
    CharLowerW(*a3 + 1);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003dc0  push    rbx
0x180003dc2  push    rbp
0x180003dc3  push    rsi
0x180003dc4  push    rdi
0x180003dc5  push    r14
0x180003dc7  sub     rsp, 30h
0x180003dcb  xor     r14d, r14d
0x180003dce  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003dd2  mov     [r8], r14
0x180003dd5  mov     rdi, r8
0x180003dd8  mov     rbx, rdx
0x180003ddb  mov     rbp, rcx
0x180003dde  test    rcx, rcx
0x180003de1  jz      short loc_180003DF2
0x180003de3  mov     r9, rax
0x180003de6  inc     r9
0x180003de9  cmp     [rcx+r9*2], r14w
0x180003dee  jnz     short loc_180003DE6
0x180003df0  jmp     short loc_180003DF5
0x180003df2  mov     r9, r14
0x180003df5  test    rbx, rbx
0x180003df8  jz      short loc_180003E06
0x180003dfa  inc     rax
0x180003dfd  cmp     [rdx+rax*2], r14w
0x180003e02  jnz     short loc_180003DFA
0x180003e04  jmp     short loc_180003E09
0x180003e06  mov     rax, r14
0x180003e09  lea     esi, [rax+1Eh]
0x180003e0c  add     esi, r9d
0x180003e0f  mov     ecx, esi
0x180003e11  call    PszAllocW
0x180003e16  mov     [rdi], rax
0x180003e19  test    rax, rax
0x180003e1c  jnz     short loc_180003E25
0x180003e1e  mov     ebx, 8007000Eh
0x180003e23  jmp     short loc_180003E66
0x180003e25  mov     edx, esi; unsigned __int64
0x180003e27  lea     r8, aLocalSS; "Local\\%s%s"
0x180003e2e  mov     r9, rbp
0x180003e31  mov     [rsp+58h+var_38], rbx
0x180003e36  mov     rcx, rax; unsigned __int16 *
0x180003e39  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003e3e  mov     ebx, eax
0x180003e40  test    eax, eax
0x180003e42  js      short loc_180003E59
0x180003e44  mov     rcx, [rdi]
0x180003e47  mov     edx, 5Ch ; '\'
0x180003e4c  add     rcx, 0Ch
0x180003e50  lea     r8d, [rdx+3]
0x180003e54  call    ReplaceCharsW
0x180003e59  mov     rcx, [rdi]
0x180003e5c  add     rcx, 2; lpsz
0x180003e60  call    cs:__imp_CharLowerW
0x180003e66  mov     eax, ebx
0x180003e68  add     rsp, 30h
0x180003e6c  pop     r14
0x180003e6e  pop     rdi
0x180003e6f  pop     rsi
0x180003e70  pop     rbp
0x180003e71  pop     rbx
0x180003e72  retn
```
