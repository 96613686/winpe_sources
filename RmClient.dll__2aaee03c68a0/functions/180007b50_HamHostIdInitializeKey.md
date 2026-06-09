# HamHostIdInitializeKey

- ea: `0x180007b50`
- end: `0x180007ce0`
- name: `HamHostIdInitializeKey`
- size: `400`
- prototype: `__int64 __fastcall(_WORD *, void *, int, int, unsigned __int16 *, _WORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001030`
- `0x180007b50`
- `0x18001ae8e`

## import_xrefs

- `api-ms-win-core-psm-key-l1-1-0!PsmIsValidKey` at `0x180007b6d`
- `api-ms-win-core-psm-key-l1-1-0!PsmIsValidKey` at `0x180007b6d`
- `ntdll!RtlValidSid` at `0x180007b7e`
- `ntdll!RtlValidSid` at `0x180007b7e`
- `ntdll!RtlCopySid` at `0x180007c18`
- `ntdll!RtlCopySid` at `0x180007c18`

## pseudocode

```c
__int64 __fastcall HamHostIdInitializeKey(_WORD *a1, void *a2, int a3, int a4, unsigned __int16 *a5, _WORD *a6)
{
  __int64 v6; // r14
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // r9
  __int64 v13; // rcx
  _WORD *v14; // rdx
  _WORD *v15; // rcx
  _WORD *v16; // r9
  wchar_t *v17; // rcx
  _WORD *v18; // rcx
  __int64 result; // rax
  __int64 v20; // rcx
  unsigned __int16 *i; // rax

  v6 = a4;
  if ( !(unsigned __int8)PsmIsValidKey() )
    return 3221225711LL;
  if ( !RtlValidSid(a2) )
    return 3221225712LL;
  if ( (unsigned int)v6 > 3 )
    return 3221225714LL;
  v10 = 256;
  if ( a5 )
  {
    v20 = 256;
    for ( i = a5; *i; ++i )
    {
      if ( !--v20 )
        return 3221225715LL;
    }
  }
  memset_0(a6, 0, 0x418u);
  v11 = 2147483646;
  v12 = 232;
  v13 = 2147483646;
  v14 = a6;
  do
  {
    if ( !v13 )
      break;
    if ( !*a1 )
      break;
    *v14++ = *a1++;
    --v13;
    --v12;
  }
  while ( v12 );
  v15 = v14 - 1;
  if ( v12 )
    v15 = v14;
  *v15 = 0;
  RtlCopySid(0x44u, a6 + 232, a2);
  v16 = a6 + 268;
  if ( a5 )
  {
    StringCchCopyW(a6 + 268, 0x100u, a5);
  }
  else
  {
    v17 = off_18001D578[v6];
    do
    {
      if ( !v11 )
        break;
      if ( !*v17 )
        break;
      *v16++ = *v17++;
      --v11;
      --v10;
    }
    while ( v10 );
    v18 = v16 - 1;
    if ( v10 )
      v18 = v16;
    *v18 = 0;
  }
  result = 0;
  *((_DWORD *)a6 + 133) = a3;
  return result;
}

```

## disassembly

```asm
0x180007b50  mov     [rsp+arg_10], rbp
0x180007b55  push    rsi
0x180007b56  push    rdi
0x180007b57  push    r12
0x180007b59  push    r14
0x180007b5b  push    r15
0x180007b5d  sub     rsp, 20h
0x180007b61  movsxd  r14, r9d
0x180007b64  mov     r12d, r8d
0x180007b67  mov     r15, rdx
0x180007b6a  mov     rsi, rcx
0x180007b6d  call    cs:__imp_PsmIsValidKey
0x180007b73  test    al, al
0x180007b75  jz      loc_180007CC2
0x180007b7b  mov     rcx, r15; Sid
0x180007b7e  call    cs:__imp_RtlValidSid
0x180007b84  test    al, al
0x180007b86  jz      loc_180007CC9
0x180007b8c  cmp     r14d, 3
0x180007b90  ja      loc_180007CBB
0x180007b96  mov     rbp, [rsp+48h+arg_20]
0x180007b9b  mov     edi, 100h
0x180007ba0  test    rbp, rbp
0x180007ba3  jnz     loc_180007C97
0x180007ba9  mov     [rsp+48h+arg_0], rbx
0x180007bae  xor     edx, edx; Val
0x180007bb0  mov     [rsp+48h+arg_8], r13
0x180007bb5  mov     r8d, 418h; Size
0x180007bbb  mov     r13, [rsp+48h+arg_28]
0x180007bc0  mov     rcx, r13; void *
0x180007bc3  call    memset_0
0x180007bc8  mov     ebx, 7FFFFFFEh
0x180007bcd  mov     r9d, 0E8h
0x180007bd3  mov     ecx, ebx
0x180007bd5  mov     rdx, r13
0x180007bd8  test    rcx, rcx
0x180007bdb  jz      short loc_180007BF9
0x180007bdd  movzx   eax, word ptr [rsi]
0x180007be0  test    ax, ax
0x180007be3  jz      short loc_180007BF9
0x180007be5  mov     [rdx], ax
0x180007be8  add     rsi, 2
0x180007bec  add     rdx, 2
0x180007bf0  dec     rcx
0x180007bf3  sub     r9, 1
0x180007bf7  jnz     short loc_180007BD8
0x180007bf9  lea     rcx, [rdx-2]
0x180007bfd  test    r9, r9
0x180007c00  mov     r8, r15; SourceSid
0x180007c03  cmovnz  rcx, rdx
0x180007c07  xor     eax, eax
0x180007c09  lea     rdx, [r13+1D0h]; DestinationSid
0x180007c10  mov     [rcx], ax
0x180007c13  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180007c18  call    cs:__imp_RtlCopySid
0x180007c1e  lea     r9, [r13+218h]
0x180007c25  test    rbp, rbp
0x180007c28  jnz     loc_180007CD0
0x180007c2e  lea     rcx, off_18001D578; "$MIX"
0x180007c35  mov     rcx, [rcx+r14*8]
0x180007c39  nop     dword ptr [rax+00000000h]
0x180007c40  test    rbx, rbx
0x180007c43  jz      short loc_180007C62
0x180007c45  movzx   eax, word ptr [rcx]
0x180007c48  test    ax, ax
0x180007c4b  jz      short loc_180007C62
0x180007c4d  mov     [r9], ax
0x180007c51  add     rcx, 2
0x180007c55  add     r9, 2
0x180007c59  dec     rbx
0x180007c5c  sub     rdi, 1
0x180007c60  jnz     short loc_180007C40
0x180007c62  test    rdi, rdi
0x180007c65  lea     rcx, [r9-2]
0x180007c69  cmovnz  rcx, r9
0x180007c6d  xor     eax, eax
0x180007c6f  mov     [rcx], ax
0x180007c72  mov     rbx, [rsp+48h+arg_0]
0x180007c77  xor     eax, eax
0x180007c79  mov     [r13+214h], r12d
0x180007c80  mov     r13, [rsp+48h+arg_8]
0x180007c85  mov     rbp, [rsp+48h+arg_10]
0x180007c8a  add     rsp, 20h
0x180007c8e  pop     r15
0x180007c90  pop     r14
0x180007c92  pop     r12
0x180007c94  pop     rdi
0x180007c95  pop     rsi
0x180007c96  retn
0x180007c97  mov     rcx, rdi
0x180007c9a  mov     rax, rbp
0x180007c9d  nop     dword ptr [rax]
0x180007ca0  cmp     word ptr [rax], 0
0x180007ca4  jz      loc_180007BA9
0x180007caa  add     rax, 2
0x180007cae  sub     rcx, 1
0x180007cb2  jnz     short loc_180007CA0
0x180007cb4  mov     eax, 0C00000F3h
0x180007cb9  jmp     short loc_180007C85
0x180007cbb  mov     eax, 0C00000F2h
0x180007cc0  jmp     short loc_180007C85
0x180007cc2  mov     eax, 0C00000EFh
0x180007cc7  jmp     short loc_180007C85
0x180007cc9  mov     eax, 0C00000F0h
0x180007cce  jmp     short loc_180007C85
0x180007cd0  mov     r8, rbp; unsigned __int16 *
0x180007cd3  mov     rdx, rdi; unsigned __int64
0x180007cd6  mov     rcx, r9; unsigned __int16 *
0x180007cd9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007cde  jmp     short loc_180007C72
```
