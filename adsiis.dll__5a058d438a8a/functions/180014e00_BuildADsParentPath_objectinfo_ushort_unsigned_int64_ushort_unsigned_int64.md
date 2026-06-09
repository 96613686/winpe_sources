# BuildADsParentPath(_objectinfo *,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180014e00`
- end: `0x180014f9d`
- name: `?BuildADsParentPath@@YAJPEAU_objectinfo@@PEAG_K12@Z`
- size: `413`
- prototype: `int(struct _objectinfo *, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180015424`
- `0x180015564`
- `0x180015b1c`
- `0x180015d04`

## callees

- `0x180014e00`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180014e3e`
- `msvcrt!swprintf_s` at `0x180014e53`
- `msvcrt!swprintf_s` at `0x180014eb2`
- `msvcrt!swprintf_s` at `0x180014f75`
- `msvcrt!swprintf_s` at `0x180014e3e`
- `msvcrt!swprintf_s` at `0x180014e53`
- `msvcrt!swprintf_s` at `0x180014eb2`
- `msvcrt!swprintf_s` at `0x180014f75`
- `msvcrt!wcscat_s` at `0x180014ed1`
- `msvcrt!wcscat_s` at `0x180014efb`
- `msvcrt!wcscat_s` at `0x180014f0e`
- `msvcrt!wcscat_s` at `0x180014f26`
- `msvcrt!wcscat_s` at `0x180014ed1`
- `msvcrt!wcscat_s` at `0x180014efb`
- `msvcrt!wcscat_s` at `0x180014f0e`
- `msvcrt!wcscat_s` at `0x180014f26`
- `msvcrt!wcscpy_s` at `0x180014e7c`
- `msvcrt!wcscpy_s` at `0x180014e7c`

## pseudocode

```c
__int64 __fastcall BuildADsParentPath(struct _objectinfo *a1, unsigned __int16 *a2, __int64 a3, unsigned __int16 *a4)
{
  int v4; // r13d
  const wchar_t *v8; // r8
  unsigned __int64 v9; // rax
  unsigned int v11; // r15d
  unsigned int v12; // r13d
  __int64 v13; // r12
  __int64 v14; // rax
  const wchar_t *v15; // r8
  wchar_t *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx

  v4 = *((_DWORD *)a1 + 136);
  if ( v4 )
  {
    swprintf_s(a2, 0x10Eu, L"%s://%s", *(_QWORD *)a1, *((_QWORD *)a1 + 1));
    v11 = 0;
    v12 = v4 - 1;
    if ( v12 )
    {
      v13 = 0;
      do
      {
        wcscat_s(a2, 0x10Eu, L"/");
        v14 = *((_QWORD *)a1 + 69);
        v15 = *(const wchar_t **)(v14 + 16 * v13);
        if ( v15 )
        {
          v16 = a2;
          if ( *(_QWORD *)(v14 + 16 * v13 + 8) )
          {
            wcscat_s(a2, 0x10Eu, v15);
            wcscat_s(a2, 0x10Eu, L"=");
            v16 = a2;
            v15 = *(const wchar_t **)(*((_QWORD *)a1 + 69) + 16 * v13 + 8);
          }
          wcscat_s(v16, 0x10Eu, v15);
        }
        ++v11;
        ++v13;
      }
      while ( v11 < v12 );
    }
    v17 = *((_QWORD *)a1 + 69);
    v8 = *(const wchar_t **)(v17 + 16LL * v12);
    if ( !v8 )
      return 0;
    v18 = *(_QWORD *)(v17 + 16LL * v12 + 8);
    if ( v18 )
    {
      swprintf_s(a4, 0x104u, L"%s=%s", v8, v18);
      return 0;
    }
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
  }
  else
  {
    if ( !*((_QWORD *)a1 + 1) )
    {
      swprintf_s(a2, 0x10Eu, L"ADs:");
      return 0;
    }
    swprintf_s(a2, 0x10Eu, L"%s:", *(_QWORD *)a1);
    v8 = (const wchar_t *)*((_QWORD *)a1 + 1);
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
  }
  if ( v9 < 0x104 )
  {
    wcscpy_s(a4, 0x104u, v8);
    return 0;
  }
  return 2147504136LL;
}

```

## disassembly

```asm
0x180014e00  push    rbx
0x180014e02  push    rbp
0x180014e03  push    rsi
0x180014e04  push    rdi
0x180014e05  push    r12
0x180014e07  push    r13
0x180014e09  push    r14
0x180014e0b  push    r15
0x180014e0d  sub     rsp, 38h
0x180014e11  mov     r13d, [rcx+220h]
0x180014e18  xor     r14d, r14d
0x180014e1b  mov     rbp, r9
0x180014e1e  mov     rsi, rdx
0x180014e21  mov     rbx, rcx
0x180014e24  test    r13d, r13d
0x180014e27  jnz     short loc_180014E95
0x180014e29  mov     edx, 10Eh; BufferCount
0x180014e2e  cmp     [rcx+8], r14
0x180014e32  jnz     short loc_180014E46
0x180014e34  lea     r8, aAds; "ADs:"
0x180014e3b  mov     rcx, rsi; Buffer
0x180014e3e  call    cs:__imp_swprintf_s
0x180014e44  jmp     short loc_180014E82
0x180014e46  mov     r9, [rcx]
0x180014e49  lea     r8, aS_0; "%s:"
0x180014e50  mov     rcx, rsi; Buffer
0x180014e53  call    cs:__imp_swprintf_s
0x180014e59  mov     r8, [rbx+8]; Source
0x180014e5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014e61  inc     rax
0x180014e64  cmp     [r8+rax*2], r14w
0x180014e69  jnz     short loc_180014E61
0x180014e6b  mov     edx, 104h; SizeInWords
0x180014e70  cmp     rax, rdx
0x180014e73  jnb     loc_180014F93
0x180014e79  mov     rcx, rbp; Destination
0x180014e7c  call    cs:__imp_wcscpy_s
0x180014e82  xor     eax, eax
0x180014e84  add     rsp, 38h
0x180014e88  pop     r15
0x180014e8a  pop     r14
0x180014e8c  pop     r13
0x180014e8e  pop     r12
0x180014e90  pop     rdi
0x180014e91  pop     rsi
0x180014e92  pop     rbp
0x180014e93  pop     rbx
0x180014e94  retn
0x180014e95  mov     rax, [rcx+8]
0x180014e99  lea     r8, aSS; "%s://%s"
0x180014ea0  mov     r9, [rcx]
0x180014ea3  mov     edi, 10Eh
0x180014ea8  mov     edx, edi; BufferCount
0x180014eaa  mov     [rsp+78h+var_58], rax
0x180014eaf  mov     rcx, rsi; Buffer
0x180014eb2  call    cs:__imp_swprintf_s
0x180014eb8  mov     r15d, r14d
0x180014ebb  sub     r13d, 1
0x180014ebf  jz      short loc_180014F3A
0x180014ec1  mov     r12, r14
0x180014ec4  lea     r8, Source; "/"
0x180014ecb  mov     rdx, rdi; SizeInWords
0x180014ece  mov     rcx, rsi; Destination
0x180014ed1  call    cs:__imp_wcscat_s
0x180014ed7  mov     rax, [rbx+228h]
0x180014ede  mov     r14, r12
0x180014ee1  add     r14, r14
0x180014ee4  mov     r8, [rax+r14*8]; Source
0x180014ee8  test    r8, r8
0x180014eeb  jz      short loc_180014F2C
0x180014eed  cmp     qword ptr [rax+r14*8+8], 0
0x180014ef3  mov     rdx, rdi; SizeInWords
0x180014ef6  mov     rcx, rsi; Destination
0x180014ef9  jz      short loc_180014F26
0x180014efb  call    cs:__imp_wcscat_s
0x180014f01  lea     r8, asc_1800213A0; "="
0x180014f08  mov     rdx, rdi; SizeInWords
0x180014f0b  mov     rcx, rsi; Destination
0x180014f0e  call    cs:__imp_wcscat_s
0x180014f14  mov     r8, [rbx+228h]
0x180014f1b  mov     rdx, rdi; SizeInWords
0x180014f1e  mov     rcx, rsi; Destination
0x180014f21  mov     r8, [r8+r14*8+8]; Source
0x180014f26  call    cs:__imp_wcscat_s
0x180014f2c  inc     r15d
0x180014f2f  inc     r12
0x180014f32  cmp     r15d, r13d
0x180014f35  jb      short loc_180014EC4
0x180014f37  xor     r14d, r14d
0x180014f3a  mov     rcx, [rbx+228h]
0x180014f41  mov     eax, r13d
0x180014f44  add     rax, rax
0x180014f47  mov     r8, [rcx+rax*8]
0x180014f4b  test    r8, r8
0x180014f4e  jz      loc_180014E82
0x180014f54  mov     rcx, [rcx+rax*8+8]
0x180014f59  test    rcx, rcx
0x180014f5c  jz      short loc_180014F80
0x180014f5e  mov     [rsp+78h+var_58], rcx
0x180014f63  mov     r9, r8
0x180014f66  lea     r8, aSS_0; "%s=%s"
0x180014f6d  mov     rcx, rbp; Buffer
0x180014f70  mov     edx, 104h; BufferCount
0x180014f75  call    cs:__imp_swprintf_s
0x180014f7b  jmp     loc_180014E82
0x180014f80  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014f84  inc     rax
0x180014f87  cmp     [r8+rax*2], r14w
0x180014f8c  jnz     short loc_180014F84
0x180014f8e  jmp     loc_180014E6B
0x180014f93  mov     eax, 80005008h
0x180014f98  jmp     loc_180014E84
```
