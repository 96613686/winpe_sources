# RouterAesKeyUnwrap

- ea: `0x180015a7c`
- end: `0x180015dab`
- name: `RouterAesKeyUnwrap`
- size: `815`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000b1d0`

## callees

- `0x1800041d0`
- `0x180004200`
- `0x180005060`
- `0x180015a7c`
- `0x18001b79d`
- `0x18001b7e0`
- `0x18001c010`

## string_xrefs

- `0x180015c82`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x180015d3e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

## pseudocode

```c
__int64 __fastcall RouterAesKeyUnwrap(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        void *Src,
        size_t Size)
{
  __int64 v7; // rax
  __int64 (__fastcall *v8)(_QWORD, __int64, __int64, _QWORD, _BYTE *, int, _DWORD); // rcx
  __int64 (__fastcall *v9)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD); // r8
  __int64 (__fastcall *v10)(__int64, const wchar_t *, int *, __int64, int *, _DWORD); // rax
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r15
  __int64 v15; // rcx
  __int64 v16; // r14
  char *v17; // rdi
  __int64 v18; // rax
  unsigned __int64 v19; // rax
  _BYTE *v20; // r9
  unsigned int i; // r12d
  unsigned int v22; // r8d
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int128 *v26; // rax
  unsigned __int64 *v27; // rax
  __int64 v28; // rcx
  _BYTE *v29; // rax
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v33; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v35)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD); // [rsp+78h] [rbp-88h]
  __int64 v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+90h] [rbp-70h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  unsigned __int64 v40; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v42)(_QWORD, __int64, __int64, _QWORD, _BYTE *, int, _DWORD); // [rsp+B0h] [rbp-50h] BYREF
  __int128 v43; // [rsp+B8h] [rbp-48h] BYREF
  char v44; // [rsp+D0h] [rbp-30h] BYREF

  v7 = *(_QWORD *)(a2 + 8);
  v39 = a1;
  v8 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _BYTE *, int, _DWORD))(a1 + 88);
  v38 = a3;
  v32 = 0;
  v31 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD))(v7 + 104);
  v10 = *(__int64 (__fastcall **)(__int64, const wchar_t *, int *, __int64, int *, _DWORD))(v7 + 64);
  v42 = v8;
  v11 = *(_QWORD *)(a2 + 16);
  v35 = v9;
  v37 = a4;
  v34 = v11;
  v12 = v10(v11, L"BlockLength", &v32, 4, &v31, 0);
  v13 = v12;
  v14 = 16;
  if ( v12 < 0 )
  {
    v15 = (unsigned int)v12;
LABEL_31:
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c");
    goto LABEL_32;
  }
  if ( v31 != 4 || v32 != 16 )
  {
    v13 = -1073741816;
    v15 = 3221225480LL;
    goto LABEL_31;
  }
  if ( (Size & 7) != 0 || (unsigned int)Size < 0x10 )
  {
    v13 = -1073741811;
    v15 = 3221225485LL;
    goto LABEL_31;
  }
  if ( (unsigned int)Size > 0x48 )
  {
    v18 = SafeAllocaAllocateFromHeap((unsigned int)Size);
    v16 = v18;
    if ( !v18 )
    {
      v13 = -1073741801;
      v15 = 3221225495LL;
      goto LABEL_31;
    }
    v17 = (char *)v18;
  }
  else
  {
    v16 = 0;
    v17 = &v44;
  }
  memcpy_0(v17, Src, (unsigned int)Size);
  v19 = *(_QWORD *)v17;
  v20 = v17 + 8;
  for ( i = 0; i < 6; ++i )
  {
    v22 = (unsigned int)(Size - 8) >> 3;
    while ( v22 )
    {
      v40 = v19 ^ _byteswap_uint64(v22 + ((unsigned __int64)(unsigned int)(Size - 8) >> 3) * (5 - i));
      v33 = v22 - 1;
      v36 = 8 * (v22 - 1);
      v41 = *(_QWORD *)&v20[v36];
      v43 = 0;
      v23 = v35(v34, &v40, 16, 0, &v43, 16, &v40, 16, &v31, 0);
      v13 = v23;
      if ( v23 < 0 )
        goto LABEL_19;
      v20 = v17 + 8;
      v19 = v40;
      v22 = v33;
      *(_QWORD *)&v17[v36 + 8] = v41;
    }
  }
  if ( v19 == 0xA6A6A6A6A6A6A6A6uLL )
  {
    v23 = v42(*(_QWORD *)(v39 + 24), v38, v37, a5, v20, (int)Size - 8, 0);
    v13 = v23;
    if ( v23 < 0 )
LABEL_19:
      DebugTraceError(
        (unsigned int)v23,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c");
    else
      v13 = 0;
  }
  else
  {
    v13 = -1073700862;
  }
  if ( v17 )
  {
    v24 = (unsigned int)Size;
    do
    {
      *v17++ = 0;
      --v24;
    }
    while ( v24 );
  }
  if ( v16 )
    BCryptFree(v16);
LABEL_32:
  v25 = 16;
  v26 = &v43;
  do
  {
    *(_BYTE *)v26 = 0;
    v26 = (__int128 *)((char *)v26 + 1);
    --v25;
  }
  while ( v25 );
  v27 = &v40;
  do
  {
    *(_BYTE *)v27 = 0;
    v27 = (unsigned __int64 *)((char *)v27 + 1);
    --v14;
  }
  while ( v14 );
  v28 = 8;
  v29 = &v42;
  do
  {
    *v29++ = 0;
    --v28;
  }
  while ( v28 );
  return v13;
}

```

## disassembly

```asm
0x180015a7c  push    rbp
0x180015a7e  push    rbx
0x180015a7f  push    rsi
0x180015a80  push    rdi
0x180015a81  push    r12
0x180015a83  push    r13
0x180015a85  push    r14
0x180015a87  push    r15
0x180015a89  lea     rbp, [rsp-38h]
0x180015a8e  sub     rsp, 138h
0x180015a95  mov     rax, cs:__security_cookie
0x180015a9c  xor     rax, rsp
0x180015a9f  mov     [rbp+70h+var_50], rax
0x180015aa3  mov     rax, [rdx+8]
0x180015aa7  mov     r13, [rbp+70h+Src]
0x180015aae  mov     [rbp+70h+var_D8], rcx
0x180015ab2  mov     rcx, [rcx+58h]
0x180015ab6  mov     [rbp+70h+var_E0], r8
0x180015aba  mov     [rsp+170h+var_10C], 0
0x180015ac2  mov     [rsp+170h+var_110], 0
0x180015aca  mov     r8, [rax+68h]
0x180015ace  mov     rax, [rax+40h]
0x180015ad2  mov     [rbp+70h+var_C0], rcx
0x180015ad6  mov     rcx, [rdx+10h]
0x180015ada  lea     rdx, [rsp+170h+var_110]
0x180015adf  mov     [rsp+170h+var_F8], r8
0x180015ae4  lea     r8, [rsp+170h+var_10C]
0x180015ae9  mov     [rbp+70h+var_E8], r9
0x180015aed  mov     r9d, 4
0x180015af3  mov     [rsp+170h+var_148], 0
0x180015afb  mov     [rsp+170h+var_150], rdx
0x180015b00  lea     rdx, aBlocklength; "BlockLength"
0x180015b07  mov     [rsp+170h+var_100], rcx
0x180015b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b11  mov     ebx, eax
0x180015b13  mov     r15d, 10h
0x180015b19  test    eax, eax
0x180015b1b  jns     short loc_180015B2A
0x180015b1d  mov     r9d, 194h
0x180015b23  mov     ecx, eax
0x180015b25  jmp     loc_180015D3E
0x180015b2a  cmp     [rsp+170h+var_110], 4
0x180015b2f  jnz     loc_180015D2E
0x180015b35  cmp     [rsp+170h+var_10C], r15d
0x180015b3a  jnz     loc_180015D2E
0x180015b40  mov     esi, dword ptr [rbp+70h+Size]
0x180015b46  test    sil, 7
0x180015b4a  jnz     loc_180015D1C
0x180015b50  cmp     esi, r15d
0x180015b53  jb      loc_180015D1C
0x180015b59  mov     ebx, esi
0x180015b5b  cmp     esi, 48h ; 'H'
0x180015b5e  ja      short loc_180015B69
0x180015b60  xor     r14d, r14d
0x180015b63  lea     rdi, [rbp+70h+var_A0]
0x180015b67  jmp     short loc_180015B91
0x180015b69  mov     rcx, rbx
0x180015b6c  call    SafeAllocaAllocateFromHeap
0x180015b71  mov     r14, rax
0x180015b74  test    rax, rax
0x180015b77  jnz     short loc_180015B8E
0x180015b79  mov     ebx, 0C0000017h
0x180015b7e  mov     r9d, 1B8h
0x180015b84  mov     ecx, 0C0000017h
0x180015b89  jmp     loc_180015D3E
0x180015b8e  mov     rdi, rax
0x180015b91  mov     r8, rbx; Size
0x180015b94  lea     r12d, [rsi-8]
0x180015b98  mov     rdx, r13; Src
0x180015b9b  mov     rcx, rdi; void *
0x180015b9e  call    memcpy_0
0x180015ba3  mov     rax, [rdi]
0x180015ba6  lea     r9, [rdi+8]
0x180015baa  mov     r13d, r12d
0x180015bad  shr     r13, 3
0x180015bb1  xor     r12d, r12d
0x180015bb4  cmp     r12d, 6
0x180015bb8  jnb     loc_180015C99
0x180015bbe  mov     r8d, r13d
0x180015bc1  test    r8d, r8d
0x180015bc4  jz      loc_180015C74
0x180015bca  mov     ecx, r8d
0x180015bcd  mov     edx, 5
0x180015bd2  sub     edx, r12d
0x180015bd5  mov     [rsp+170h+var_128], 0
0x180015bdd  imul    rdx, r13
0x180015be1  xorps   xmm0, xmm0
0x180015be4  add     rdx, rcx
0x180015be7  mov     rcx, [rsp+170h+var_100]
0x180015bec  bswap   rdx
0x180015bef  xor     rdx, rax
0x180015bf2  dec     r8d
0x180015bf5  mov     [rbp+70h+var_D0], rdx
0x180015bf9  mov     [rsp+170h+var_108], r8d
0x180015bfe  lea     rdx, [rbp+70h+var_D0]
0x180015c02  lea     eax, ds:0[r8*8]
0x180015c0a  mov     r8d, r15d
0x180015c0d  mov     [rbp+70h+var_F0], rax
0x180015c11  mov     rax, [rax+r9]
0x180015c15  xor     r9d, r9d
0x180015c18  mov     [rbp+70h+var_C8], rax
0x180015c1c  lea     rax, [rsp+170h+var_110]
0x180015c21  mov     [rsp+170h+var_130], rax
0x180015c26  lea     rax, [rbp+70h+var_D0]
0x180015c2a  mov     [rsp+170h+var_138], r15d
0x180015c2f  mov     [rsp+170h+var_140], rax
0x180015c34  lea     rax, [rbp+70h+var_B8]
0x180015c38  mov     [rsp+170h+var_148], r15d
0x180015c3d  mov     [rsp+170h+var_150], rax
0x180015c42  mov     rax, [rsp+170h+var_F8]
0x180015c47  movups  [rbp+70h+var_B8], xmm0
0x180015c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c50  mov     ebx, eax
0x180015c52  test    eax, eax
0x180015c54  js      short loc_180015C7C
0x180015c56  mov     rdx, [rbp+70h+var_F0]
0x180015c5a  lea     r9, [rdi+8]
0x180015c5e  mov     rcx, [rbp+70h+var_C8]
0x180015c62  mov     rax, [rbp+70h+var_D0]
0x180015c66  mov     r8d, [rsp+170h+var_108]
0x180015c6b  mov     [rdx+r9], rcx
0x180015c6f  jmp     loc_180015BC1
0x180015c74  inc     r12d
0x180015c77  jmp     loc_180015BB4
0x180015c7c  mov     r9d, 1E5h
0x180015c82  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015c89  mov     ecx, eax
0x180015c8b  lea     rdx, aStatus; "Status"
0x180015c92  call    DebugTraceError
0x180015c97  jmp     short loc_180015CF5
0x180015c99  mov     rcx, 0A6A6A6A6A6A6A6A6h
0x180015ca3  cmp     rax, rcx
0x180015ca6  jz      short loc_180015CAF
0x180015ca8  mov     ebx, 0C000A002h
0x180015cad  jmp     short loc_180015CF5
0x180015caf  mov     rcx, [rbp+70h+var_D8]
0x180015cb3  lea     r10d, [rsi-8]
0x180015cb7  mov     r8, [rbp+70h+var_E8]
0x180015cbb  mov     rdx, [rbp+70h+var_E0]
0x180015cbf  mov     rax, [rbp+70h+var_C0]
0x180015cc3  mov     rcx, [rcx+18h]
0x180015cc7  mov     dword ptr [rsp+170h+var_140], 0
0x180015ccf  mov     [rsp+170h+var_148], r10d
0x180015cd4  mov     [rsp+170h+var_150], r9
0x180015cd9  mov     r9d, [rbp+70h+arg_20]
0x180015ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ce5  mov     ebx, eax
0x180015ce7  test    eax, eax
0x180015ce9  jns     short loc_180015CF3
0x180015ceb  mov     r9d, 1FFh
0x180015cf1  jmp     short loc_180015C82
0x180015cf3  xor     ebx, ebx
0x180015cf5  test    rdi, rdi
0x180015cf8  jz      short loc_180015D0D
0x180015cfa  mov     rax, rsi
0x180015cfd  test    esi, esi
0x180015cff  jz      short loc_180015D0D
0x180015d01  mov     byte ptr [rdi], 0
0x180015d04  inc     rdi
0x180015d07  sub     rax, 1
0x180015d0b  jnz     short loc_180015D01
0x180015d0d  test    r14, r14
0x180015d10  jz      short loc_180015D51
0x180015d12  mov     rcx, r14
0x180015d15  call    BCryptFree
0x180015d1a  jmp     short loc_180015D51
0x180015d1c  mov     ebx, 0C000000Dh
0x180015d21  mov     r9d, 1A4h
0x180015d27  mov     ecx, 0C000000Dh
0x180015d2c  jmp     short loc_180015D3E
0x180015d2e  mov     ebx, 0C0000008h
0x180015d33  mov     r9d, 19Ch
0x180015d39  mov     ecx, 0C0000008h
0x180015d3e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015d45  lea     rdx, aStatus; "Status"
0x180015d4c  call    DebugTraceError
0x180015d51  mov     rcx, r15
0x180015d54  lea     rax, [rbp+70h+var_B8]
0x180015d58  mov     byte ptr [rax], 0
0x180015d5b  inc     rax
0x180015d5e  sub     rcx, 1
0x180015d62  jnz     short loc_180015D58
0x180015d64  lea     rax, [rbp+70h+var_D0]
0x180015d68  mov     byte ptr [rax], 0
0x180015d6b  inc     rax
0x180015d6e  sub     r15, 1
0x180015d72  jnz     short loc_180015D68
0x180015d74  lea     ecx, [r15+8]
0x180015d78  lea     rax, [rbp+70h+var_C0]
0x180015d7c  mov     byte ptr [rax], 0
0x180015d7f  inc     rax
0x180015d82  sub     rcx, 1
0x180015d86  jnz     short loc_180015D7C
0x180015d88  mov     eax, ebx
0x180015d8a  mov     rcx, [rbp+70h+var_50]
0x180015d8e  xor     rcx, rsp; StackCookie
0x180015d91  call    __security_check_cookie
0x180015d96  add     rsp, 138h
0x180015d9d  pop     r15
0x180015d9f  pop     r14
0x180015da1  pop     r13
0x180015da3  pop     r12
0x180015da5  pop     rdi
0x180015da6  pop     rsi
0x180015da7  pop     rbx
0x180015da8  pop     rbp
0x180015da9  retn
```
