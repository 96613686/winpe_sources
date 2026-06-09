# GenerateSecretAgreementPubKey(ushort *,uchar *,ulong,void * *)

- ea: `0x18000e540`
- end: `0x18000e63e`
- name: `?GenerateSecretAgreementPubKey@@YAJPEAGPEAEKPEAPEAX@Z`
- size: `254`
- prototype: `int(unsigned __int16 *, unsigned __int8 *, unsigned int, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e8a0`
- `0x1800189b8`
- `0x1800190b4`

## callees

- `0x18000e540`
- `0x180010f9c`
- `0x18001a450`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18000e5c6`
- `bcrypt!BCryptImportKeyPair` at `0x18000e5c6`
- `bcrypt!BCryptDestroyKey` at `0x18000e62c`
- `bcrypt!BCryptDestroyKey` at `0x18000e62c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000e61c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000e61c`

## string_xrefs

- `0x18000e58b`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`
- `0x18000e5d8`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`

## pseudocode

```c
__int64 __fastcall GenerateSecretAgreementPubKey(unsigned __int16 *a1, unsigned __int8 *a2, ULONG a3, void **a4)
{
  signed int CachedBCryptHandle; // eax
  unsigned int v8; // ebx
  NTSTATUS v9; // eax
  NTSTATUS v10; // esi
  int v12; // [rsp+40h] [rbp-48h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+48h] [rbp-40h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-38h] BYREF

  hAlgorithm = 0;
  phKey = 0;
  v12 = 1;
  CachedBCryptHandle = GetCachedBCryptHandle(a1, &hAlgorithm, 4u, &v12);
  v8 = CachedBCryptHandle;
  if ( CachedBCryptHandle >= 0 )
  {
    v9 = BCryptImportKeyPair(hAlgorithm, 0, L"PUBLICBLOB", &phKey, a2, a3, 0);
    v10 = v9;
    if ( v9 >= 0 )
    {
      *a4 = phKey;
      phKey = 0;
    }
    else
    {
      SidKeyDebugTraceError(v9, "status", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx", 0x241u);
      v8 = v10 | 0x10000000;
    }
  }
  else
  {
    SidKeyDebugTraceError(
      CachedBCryptHandle,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx",
      0x233u);
  }
  if ( !v12 && hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  if ( phKey )
    BCryptDestroyKey(phKey);
  return v8;
}

```

## disassembly

```asm
0x18000e540  mov     rax, rsp
0x18000e543  push    rbx
0x18000e544  push    rbp
0x18000e545  push    rsi
0x18000e546  push    r14
0x18000e548  sub     rsp, 68h
0x18000e54c  mov     r14, r9
0x18000e54f  mov     qword ptr [rax-40h], 0
0x18000e557  mov     esi, r8d
0x18000e55a  mov     qword ptr [rax-38h], 0
0x18000e562  mov     rbp, rdx
0x18000e565  mov     dword ptr [rax-48h], 1
0x18000e56c  lea     r9, [rax-48h]; int *
0x18000e570  mov     r8d, 4; unsigned int
0x18000e576  lea     rdx, [rax-40h]; void **
0x18000e57a  call    ?GetCachedBCryptHandle@@YAJPEBGPEAPEAXKPEAH@Z; GetCachedBCryptHandle(ushort const *,void * *,ulong,int *)
0x18000e57f  mov     ebx, eax
0x18000e581  test    eax, eax
0x18000e583  jns     short loc_18000E5A2
0x18000e585  mov     r9d, 233h; unsigned int
0x18000e58b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000e592  lea     rdx, aHr; "hr"
0x18000e599  mov     ecx, eax; unsigned int
0x18000e59b  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000e5a0  jmp     short loc_18000E606
0x18000e5a2  mov     rcx, [rsp+88h+hAlgorithm]; hAlgorithm
0x18000e5a7  lea     r9, [rsp+88h+phKey]; phKey
0x18000e5ac  mov     [rsp+88h+dwFlags], 0; dwFlags
0x18000e5b4  lea     r8, pszBlobType; "PUBLICBLOB"
0x18000e5bb  mov     [rsp+88h+cbInput], esi; cbInput
0x18000e5bf  xor     edx, edx; hImportKey
0x18000e5c1  mov     [rsp+88h+pbInput], rbp; pbInput
0x18000e5c6  call    cs:__imp_BCryptImportKeyPair
0x18000e5cc  mov     esi, eax
0x18000e5ce  test    eax, eax
0x18000e5d0  jns     short loc_18000E5F5
0x18000e5d2  mov     r9d, 241h; unsigned int
0x18000e5d8  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000e5df  lea     rdx, aStatus; "status"
0x18000e5e6  mov     ecx, eax; unsigned int
0x18000e5e8  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000e5ed  mov     ebx, esi
0x18000e5ef  bts     ebx, 1Ch
0x18000e5f3  jmp     short loc_18000E606
0x18000e5f5  mov     rax, [rsp+88h+phKey]
0x18000e5fa  mov     [r14], rax
0x18000e5fd  mov     [rsp+88h+phKey], 0
0x18000e606  cmp     [rsp+88h+var_48], 0
0x18000e60b  jnz     short loc_18000E622
0x18000e60d  cmp     [rsp+88h+hAlgorithm], 0
0x18000e613  jz      short loc_18000E622
0x18000e615  mov     rcx, [rsp+88h+hAlgorithm]; hAlgorithm
0x18000e61a  xor     edx, edx; dwFlags
0x18000e61c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000e622  mov     rcx, [rsp+88h+phKey]; hKey
0x18000e627  test    rcx, rcx
0x18000e62a  jz      short loc_18000E632
0x18000e62c  call    cs:__imp_BCryptDestroyKey
0x18000e632  mov     eax, ebx
0x18000e634  add     rsp, 68h
0x18000e638  pop     r14
0x18000e63a  pop     rsi
0x18000e63b  pop     rbp
0x18000e63c  pop     rbx
0x18000e63d  retn
```
