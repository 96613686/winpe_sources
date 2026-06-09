# ConcatenatePaths

- ea: `0x180002dc8`
- end: `0x180002eaf`
- name: `ConcatenatePaths`
- size: `231`
- prototype: `_BOOL8 __fastcall(__int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003514`

## callees

- `0x180002dc8`
- `0x180002eb8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180002e94`
- `KERNEL32!SetLastError` at `0x180002e94`
- `USER32!CharPrevW` at `0x180002e08`
- `USER32!CharPrevW` at `0x180002e08`

## pseudocode

```c
_BOOL8 __fastcall ConcatenatePaths(__int64 a1, unsigned __int16 *a2)
{
  __int64 v2; // rdi
  unsigned __int64 v4; // rbx
  LPWSTR v6; // rax
  int v7; // ecx
  DWORD v8; // edi
  int v9; // eax

  v2 = -1;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a1 + 2 * v4) );
  do
    ++v2;
  while ( a2[v2] );
  if ( v4 )
  {
    v6 = CharPrevW((LPCWSTR)a1, (LPCWSTR)(a1 + 2 * v4));
    if ( *v6 == 92 || *v6 == 47 )
      --v4;
  }
  if ( *a2 == 92 || *a2 == 47 )
  {
    v7 = 1;
    --v2;
  }
  else
  {
    v7 = 0;
  }
  if ( v4 + v2 + 2 > 0x104 )
  {
    v8 = 206;
LABEL_23:
    SetLastError(v8);
    return v8 == 0;
  }
  if ( !v7 )
  {
    if ( v4 >= 0x104 )
    {
LABEL_17:
      v8 = 206;
      goto LABEL_20;
    }
    *(_WORD *)(a1 + 2 * v4++) = 92;
  }
  if ( v4 >= 0x104 )
    goto LABEL_17;
  v8 = 0;
  v9 = StringCchCopyW((unsigned __int16 *)(a1 + 2 * v4), 260 - v4, a2);
  if ( v9 < 0 )
    v8 = (unsigned __int16)v9;
LABEL_20:
  *(_WORD *)(a1 + 518) = 0;
  if ( v8 )
    goto LABEL_23;
  return v8 == 0;
}

```

## disassembly

```asm
0x180002dc8  push    rbx
0x180002dca  push    rbp
0x180002dcb  push    rsi
0x180002dcc  push    rdi
0x180002dcd  push    r14
0x180002dcf  push    r15
0x180002dd1  sub     rsp, 28h
0x180002dd5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002dd9  mov     rbp, rdx
0x180002ddc  mov     rbx, rdi
0x180002ddf  xor     r14d, r14d
0x180002de2  mov     rsi, rcx
0x180002de5  inc     rbx
0x180002de8  cmp     [rcx+rbx*2], r14w
0x180002ded  jnz     short loc_180002DE5
0x180002def  inc     rdi
0x180002df2  cmp     [rdx+rdi*2], r14w
0x180002df7  jnz     short loc_180002DEF
0x180002df9  mov     r15d, 5Ch ; '\'
0x180002dff  test    rbx, rbx
0x180002e02  jz      short loc_180002E1D
0x180002e04  lea     rdx, [rcx+rbx*2]; lpszCurrent
0x180002e08  call    cs:__imp_CharPrevW
0x180002e0e  cmp     [rax], r15w
0x180002e12  jz      short loc_180002E1A
0x180002e14  cmp     word ptr [rax], 2Fh ; '/'
0x180002e18  jnz     short loc_180002E1D
0x180002e1a  dec     rbx
0x180002e1d  cmp     [rbp+0], r15w
0x180002e22  jz      short loc_180002E30
0x180002e24  cmp     word ptr [rbp+0], 2Fh ; '/'
0x180002e29  jz      short loc_180002E30
0x180002e2b  mov     ecx, r14d
0x180002e2e  jmp     short loc_180002E38
0x180002e30  mov     ecx, 1
0x180002e35  dec     rdi
0x180002e38  lea     rax, [rdi+2]
0x180002e3c  mov     edx, 104h
0x180002e41  add     rax, rbx
0x180002e44  cmp     rax, rdx
0x180002e47  ja      short loc_180002E8D
0x180002e49  test    ecx, ecx
0x180002e4b  jnz     short loc_180002E5A
0x180002e4d  cmp     rbx, rdx
0x180002e50  jnb     short loc_180002E5F
0x180002e52  mov     [rsi+rbx*2], r15w
0x180002e57  inc     rbx
0x180002e5a  cmp     rbx, rdx
0x180002e5d  jb      short loc_180002E66
0x180002e5f  mov     edi, 0CEh
0x180002e64  jmp     short loc_180002E7F
0x180002e66  sub     rdx, rbx; unsigned __int64
0x180002e69  lea     rcx, [rsi+rbx*2]; unsigned __int16 *
0x180002e6d  mov     r8, rbp; unsigned __int16 *
0x180002e70  mov     edi, r14d
0x180002e73  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002e78  test    eax, eax
0x180002e7a  jns     short loc_180002E7F
0x180002e7c  movzx   edi, ax
0x180002e7f  mov     [rsi+206h], r14w
0x180002e87  test    edi, edi
0x180002e89  jz      short loc_180002E9A
0x180002e8b  jmp     short loc_180002E92
0x180002e8d  mov     edi, 0CEh
0x180002e92  mov     ecx, edi; dwErrCode
0x180002e94  call    cs:__imp_SetLastError
0x180002e9a  test    edi, edi
0x180002e9c  mov     eax, r14d
0x180002e9f  setz    al
0x180002ea2  add     rsp, 28h
0x180002ea6  pop     r15
0x180002ea8  pop     r14
0x180002eaa  pop     rdi
0x180002eab  pop     rsi
0x180002eac  pop     rbp
0x180002ead  pop     rbx
0x180002eae  retn
```
