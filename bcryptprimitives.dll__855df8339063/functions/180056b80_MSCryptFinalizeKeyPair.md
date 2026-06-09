# MSCryptFinalizeKeyPair

- ea: `0x180056b80`
- end: `0x180056ce7`
- name: `MSCryptFinalizeKeyPair`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180056b70`
- `0x18006cb00`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18003cfd4`
- `0x180043050`
- `0x18004ae08`
- `0x180054350`
- `0x180056b80`
- `0x180056cf0`

## string_xrefs

- `0x180056bc4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180056c11`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180056cb6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptFinalizeKeyPair(__int64 a1, int a2, int a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // r9
  __int64 v8; // rcx
  int SymcryptRsakey; // eax
  __int64 v10; // r9
  unsigned int v11; // eax
  int v12; // edx
  int v13; // r8d

  if ( a2 )
  {
    v4 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        227);
    return v4;
  }
  v5 = validateMSCryptRsaKey(a1);
  v6 = v5;
  if ( !v5 )
  {
    v7 = 1003;
LABEL_8:
    v4 = -1073741816;
    v8 = 3221225480LL;
LABEL_9:
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v7);
    return v4;
  }
  if ( *(_DWORD *)(v5 + 16) )
  {
    v7 = 1010;
    goto LABEL_8;
  }
  SymcryptRsakey = AllocateSymcryptRsakey(v5);
  v4 = SymcryptRsakey;
  if ( SymcryptRsakey < 0 )
  {
    v7 = 1017;
    v8 = (unsigned int)SymcryptRsakey;
    goto LABEL_9;
  }
  v10 = a3 != 0 ? 4096 : 12288;
  LODWORD(v10) = v10 | 0x100;
  if ( *(_DWORD *)(v6 + 12) >= 0x400u )
    v10 = a3 != 0 ? 4096 : 12288;
  v11 = SymCryptRsakeyGenerate(*(_QWORD *)(v6 + 32), 0, 0, v10);
  if ( v11 )
  {
    v4 = SymcryptErrorCodeToNtStatus(v11);
    SymCryptRsakeyFree(*(_QWORD *)(v6 + 32));
    *(_QWORD *)(v6 + 32) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        v13,
        (unsigned int)"Status",
        v4,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        15);
  }
  else
  {
    *(_DWORD *)(v6 + 16) = 1;
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180056b80  mov     [rsp+arg_0], rbx
0x180056b85  mov     [rsp+arg_8], rsi
0x180056b8a  push    rdi
0x180056b8b  sub     rsp, 40h
0x180056b8f  mov     esi, r8d
0x180056b92  test    edx, edx
0x180056b94  jz      short loc_180056BED
0x180056b96  mov     ebx, 0C000000Dh
0x180056b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ba2  lea     rax, WPP_GLOBAL_Control
0x180056ba9  cmp     rcx, rax
0x180056bac  jz      loc_180056CD4
0x180056bb2  test    byte ptr [rcx+1Ch], 1
0x180056bb6  jz      loc_180056CD4
0x180056bbc  mov     [rsp+48h+var_18], 3E3h
0x180056bc4  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180056bcb  mov     [rsp+48h+var_20], rax
0x180056bd0  mov     [rsp+48h+var_28], 0C000000Dh
0x180056bd8  mov     rcx, [rcx+10h]
0x180056bdc  lea     r9, aStatus; "Status"
0x180056be3  call    WPP_SF_sDsd
0x180056be8  jmp     loc_180056CD4
0x180056bed  call    validateMSCryptRsaKey
0x180056bf2  mov     rdi, rax
0x180056bf5  test    rax, rax
0x180056bf8  jnz     short loc_180056C22
0x180056bfa  mov     r9d, 3EBh
0x180056c00  mov     ebx, 0C0000008h
0x180056c05  mov     ecx, 0C0000008h
0x180056c0a  lea     rdx, aStatus; "Status"
0x180056c11  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180056c18  call    DebugTraceError
0x180056c1d  jmp     loc_180056CD4
0x180056c22  cmp     dword ptr [rax+10h], 0
0x180056c26  jz      short loc_180056C30
0x180056c28  mov     r9d, 3F2h
0x180056c2e  jmp     short loc_180056C00
0x180056c30  mov     rcx, rdi
0x180056c33  call    AllocateSymcryptRsakey
0x180056c38  mov     ebx, eax
0x180056c3a  test    eax, eax
0x180056c3c  jns     short loc_180056C48
0x180056c3e  mov     r9d, 3F9h
0x180056c44  mov     ecx, eax
0x180056c46  jmp     short loc_180056C0A
0x180056c48  mov     rcx, [rdi+20h]
0x180056c4c  neg     esi
0x180056c4e  sbb     eax, eax
0x180056c50  and     eax, 0FFFFE000h
0x180056c55  add     eax, 3000h
0x180056c5a  mov     r9d, eax
0x180056c5d  bts     r9d, 8
0x180056c62  cmp     dword ptr [rdi+0Ch], 400h
0x180056c69  cmovnb  r9d, eax
0x180056c6d  xor     r8d, r8d
0x180056c70  xor     edx, edx
0x180056c72  call    SymCryptRsakeyGenerate
0x180056c77  test    eax, eax
0x180056c79  jz      short loc_180056CCB
0x180056c7b  mov     ecx, eax
0x180056c7d  call    SymcryptErrorCodeToNtStatus
0x180056c82  mov     rcx, [rdi+20h]
0x180056c86  mov     ebx, eax
0x180056c88  call    SymCryptRsakeyFree
0x180056c8d  mov     qword ptr [rdi+20h], 0
0x180056c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c9c  lea     rax, WPP_GLOBAL_Control
0x180056ca3  cmp     rcx, rax
0x180056ca6  jz      short loc_180056CD4
0x180056ca8  test    byte ptr [rcx+1Ch], 1
0x180056cac  jz      short loc_180056CD4
0x180056cae  mov     [rsp+48h+var_18], 40Fh
0x180056cb6  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180056cbd  mov     [rsp+48h+var_20], rax
0x180056cc2  mov     [rsp+48h+var_28], ebx
0x180056cc6  jmp     loc_180056BD8
0x180056ccb  mov     dword ptr [rdi+10h], 1
0x180056cd2  xor     ebx, ebx
0x180056cd4  mov     rsi, [rsp+48h+arg_8]
0x180056cd9  mov     eax, ebx
0x180056cdb  mov     rbx, [rsp+48h+arg_0]
0x180056ce0  add     rsp, 40h
0x180056ce4  pop     rdi
0x180056ce5  retn
```
