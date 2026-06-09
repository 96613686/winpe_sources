# GenerateLatestSecretFromSidKey

- ea: `0x180018b88`
- end: `0x180018c75`
- name: `GenerateLatestSecretFromSidKey`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180018c7c`

## callees

- `0x18000d6a0`
- `0x180018b88`
- `0x18001a450`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180018bc8`
- `bcrypt!BCryptGenRandom` at `0x180018bc8`

## string_xrefs

- `0x180018c58`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall GenerateLatestSecretFromSidKey(
        __int64 a1,
        struct _INFORMATIONCARD_CRYPTO_HANDLE *a2,
        DWORD a3,
        __int64 a4,
        __int64 a5,
        UCHAR *pbBuffer)
{
  unsigned int v6; // edi
  DWORD v7; // ebx
  NTSTATUS DerivedKey; // eax
  const char *v11; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // r9d
  BYTE *pNonce; // [rsp+20h] [rbp-88h]
  PBYTE *ppKey; // [rsp+48h] [rbp-60h]

  v6 = *(_DWORD *)(a1 + 44);
  v7 = 0;
  if ( v6 )
    v7 = a1 + *(_DWORD *)(a1 + 40) + 80;
  DerivedKey = BCryptGenRandom(0, pbBuffer, 0x20u, 2u);
  if ( DerivedKey < 0 )
  {
    v11 = "status";
    v12 = DerivedKey | 0x10000000;
    v13 = 822;
LABEL_7:
    SidKeyDebugTraceError(
      DerivedKey,
      v11,
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      v13);
    return v12;
  }
  LODWORD(ppKey) = 0;
  LODWORD(pNonce) = 64;
  DerivedKey = GenerateDerivedKey(a2, v7, (PBYTE)v6, a3, pNonce, (DWORD)pbBuffer, 0x20u, 0, 0, ppKey);
  v12 = DerivedKey;
  if ( DerivedKey < 0 )
  {
    v13 = 844;
    v11 = "hr";
    goto LABEL_7;
  }
  return v12;
}

```

## disassembly

```asm
0x180018b88  push    rbx
0x180018b8a  push    rbp
0x180018b8b  push    rsi
0x180018b8c  push    rdi
0x180018b8d  push    r14
0x180018b8f  push    r15
0x180018b91  sub     rsp, 78h
0x180018b95  mov     edi, [rcx+2Ch]
0x180018b98  xor     ebx, ebx
0x180018b9a  mov     rbp, r9
0x180018b9d  mov     r14, r8
0x180018ba0  mov     r15, rdx
0x180018ba3  test    edi, edi
0x180018ba5  jz      short loc_180018BB1
0x180018ba7  mov     ebx, [rcx+28h]
0x180018baa  add     rbx, 50h ; 'P'
0x180018bae  add     rbx, rcx
0x180018bb1  mov     rsi, [rsp+0A8h+pbBuffer]
0x180018bb9  mov     r9d, 2; dwFlags
0x180018bbf  mov     rdx, rsi; pbBuffer
0x180018bc2  xor     ecx, ecx; hAlgorithm
0x180018bc4  lea     r8d, [r9+1Eh]; cbBuffer
0x180018bc8  call    cs:__imp_BCryptGenRandom
0x180018bce  test    eax, eax
0x180018bd0  jns     short loc_180018BE7
0x180018bd2  mov     ebx, eax
0x180018bd4  lea     rdx, aStatus; "status"
0x180018bdb  bts     ebx, 1Ch
0x180018bdf  mov     r9d, 336h
0x180018be5  jmp     short loc_180018C58
0x180018be7  mov     [rsp+0A8h+var_40], 0
0x180018bf0  mov     r9, r14; cbNonce
0x180018bf3  mov     [rsp+0A8h+var_48], 20h ; ' '
0x180018bfb  mov     r8d, edi; pLabel
0x180018bfe  mov     [rsp+0A8h+var_50], rbp
0x180018c03  mov     rdx, rbx; cbLabel
0x180018c06  mov     [rsp+0A8h+var_58], 1
0x180018c0e  mov     rcx, r15; hCrypto
0x180018c11  mov     dword ptr [rsp+0A8h+ppKey], 0; ppKey
0x180018c19  mov     [rsp+0A8h+pcbKey], 0; pcbKey
0x180018c22  mov     [rsp+0A8h+algId], 0; algId
0x180018c2b  mov     [rsp+0A8h+offset], 20h ; ' '; offset
0x180018c33  mov     qword ptr [rsp+0A8h+derivedKeyLength], rsi; derivedKeyLength
0x180018c38  mov     dword ptr [rsp+0A8h+pNonce], 40h ; '@'; pNonce
0x180018c40  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x180018c45  mov     ebx, eax
0x180018c47  test    eax, eax
0x180018c49  jns     short loc_180018C66
0x180018c4b  mov     r9d, 34Ch; unsigned int
0x180018c51  lea     rdx, aHr; "hr"
0x180018c58  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018c5f  mov     ecx, eax; unsigned int
0x180018c61  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018c66  mov     eax, ebx
0x180018c68  add     rsp, 78h
0x180018c6c  pop     r15
0x180018c6e  pop     r14
0x180018c70  pop     rdi
0x180018c71  pop     rsi
0x180018c72  pop     rbp
0x180018c73  pop     rbx
0x180018c74  retn
```
