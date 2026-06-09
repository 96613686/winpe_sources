# ImportMachineKey

- ea: `0x140003e58`
- end: `0x140004133`
- name: `ImportMachineKey`
- size: `731`
- prototype: `__int64 __fastcall(const void *, unsigned int, BCRYPT_KEY_HANDLE *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400044d0`
- `0x140004b70`

## callees

- `0x140003e58`
- `0x140004ca8`
- `0x140004d1c`
- `0x140005280`
- `0x1400066f0`
- `0x140006720`

## import_xrefs

- `iumcrypt!iumCryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x140003fc2`
- `iumcrypt!iumCryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x14000407a`
- `iumcrypt!iumCryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x140003fc2`
- `iumcrypt!iumCryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x14000407a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000408e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000408e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040c0`
- `bcrypt!BCryptDestroyKey` at `0x1400040e4`
- `bcrypt!BCryptDestroyKey` at `0x1400040e4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140003f0e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140003f0e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1400040f5`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1400040f5`
- `bcrypt!BCryptImportKeyPair` at `0x140003f6a`
- `bcrypt!BCryptImportKeyPair` at `0x140003f6a`

## pseudocode

```c
__int64 __fastcall ImportMachineKey(const void *a1, unsigned int a2, BCRYPT_KEY_HANDLE *a3, void **a4)
{
  int LastError; // ebx
  _QWORD *v7; // rcx
  int v8; // edx
  char v9; // al
  int v10; // r8d
  int v11; // edx
  struct _CERT_PUBLIC_KEY_INFO *v12; // rax
  struct _LSA_ISO_ASYMMETRIC_KEY_BLOB *v14; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-8h] BYREF
  size_t size; // [rsp+80h] [rbp+30h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+88h] [rbp+38h] BYREF

  *a3 = 0;
  *a4 = 0;
  LODWORD(size) = 0;
  v14 = 0;
  phAlgorithm = 0;
  phKey = 0;
  LastError = LsaIsoDecryptAsymmetricKeyBlob(a1, a2, &v14, 0, 0);
  if ( LastError < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 11;
LABEL_5:
      WPP_SF_sd(
        v7[2],
        v8,
        (unsigned int)&WPP_51646ada86fc316e06b18fa5421f3daa_Traceguids,
        (unsigned int)"ImportMachineKey",
        LastError);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  if ( *((_DWORD *)v14 + 8) != 1 )
  {
    LastError = -1073741811;
    goto LABEL_34;
  }
  LastError = BCryptOpenAlgorithmProvider(&phAlgorithm, *(LPCWSTR *)v14, 0, 0);
  if ( LastError < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 12;
      goto LABEL_5;
    }
    goto LABEL_34;
  }
  LastError = BCryptImportKeyPair(
                phAlgorithm,
                0,
                *((LPCWSTR *)v14 + 1),
                &phKey,
                *((PUCHAR *)v14 + 3),
                *((_DWORD *)v14 + 4),
                0);
  if ( LastError < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 13;
      goto LABEL_5;
    }
    goto LABEL_34;
  }
  if ( !iumCryptExportPublicKeyInfoFromBCryptKeyHandle(phKey, 1u, 0, 0, 0, 0, (unsigned int *)&size) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_34;
    v9 = GetLastError();
    v11 = 14;
LABEL_23:
    WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v10, (unsigned int)"ImportMachineKey", v9, LastError);
    goto LABEL_34;
  }
  v12 = (struct _CERT_PUBLIC_KEY_INFO *)MIDL_user_allocate((unsigned int)size);
  *a4 = v12;
  if ( !v12 )
  {
    LastError = -1073741801;
    goto LABEL_34;
  }
  if ( iumCryptExportPublicKeyInfoFromBCryptKeyHandle(phKey, 1u, 0, 0, 0, v12, (unsigned int *)&size) )
  {
    *a3 = phKey;
    phKey = 0;
    goto LABEL_34;
  }
  if ( (int)GetLastError() > 0 )
    LastError = (unsigned __int16)GetLastError() | 0xC0070000;
  else
    LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = GetLastError();
    v11 = 15;
    goto LABEL_23;
  }
LABEL_34:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v14 )
    SafeAllocaFreeToHeap(v14);
  if ( LastError < 0 && *a4 )
  {
    SafeAllocaFreeToHeap(*a4);
    *a4 = 0;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140003e58  mov     [rsp-18h+arg_0], rbx
0x140003e5d  mov     [rsp-18h+arg_8], rsi
0x140003e62  push    rbp
0x140003e63  push    r14
0x140003e65  push    r15
0x140003e67  mov     rbp, rsp
0x140003e6a  sub     rsp, 50h
0x140003e6e  xor     r15d, r15d
0x140003e71  mov     rsi, r9
0x140003e74  mov     [r8], r15
0x140003e77  mov     r14, r8
0x140003e7a  mov     [r9], r15
0x140003e7d  lea     r8, [rbp+var_10]; struct _LSA_ISO_ASYMMETRIC_KEY_BLOB **
0x140003e81  xor     r9d, r9d; void **
0x140003e84  mov     dword ptr [rbp+size], r15d
0x140003e88  mov     [rbp+var_10], r15
0x140003e8c  mov     [rbp+phAlgorithm], r15
0x140003e90  mov     [rbp+phKey], r15
0x140003e94  mov     [rsp+50h+pbInput], r15; unsigned int *
0x140003e99  call    ?LsaIsoDecryptAsymmetricKeyBlob@@YAJPEBXKPEAPEAU_LSA_ISO_ASYMMETRIC_KEY_BLOB@@PEAPEAXPEAK@Z; LsaIsoDecryptAsymmetricKeyBlob(void const *,ulong,_LSA_ISO_ASYMMETRIC_KEY_BLOB * *,void * *,ulong *)
0x140003e9e  mov     ebx, eax
0x140003ea0  test    eax, eax
0x140003ea2  jns     short loc_140003EE9
0x140003ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x140003eab  lea     rax, WPP_GLOBAL_Control
0x140003eb2  cmp     rcx, rax
0x140003eb5  jz      loc_1400040DB
0x140003ebb  test    byte ptr [rcx+1Ch], 1
0x140003ebf  jz      loc_1400040DB
0x140003ec5  lea     edx, [r15+0Bh]
0x140003ec9  mov     rcx, [rcx+10h]
0x140003ecd  lea     r9, aImportmachinek; "ImportMachineKey"
0x140003ed4  lea     r8, WPP_51646ada86fc316e06b18fa5421f3daa_Traceguids
0x140003edb  mov     dword ptr [rsp+50h+pbInput], ebx
0x140003edf  call    WPP_SF_sd
0x140003ee4  jmp     loc_1400040DB
0x140003ee9  mov     rax, [rbp+var_10]
0x140003eed  cmp     dword ptr [rax+20h], 1
0x140003ef1  jz      short loc_140003EFD
0x140003ef3  mov     ebx, 0C000000Dh
0x140003ef8  jmp     loc_1400040DB
0x140003efd  mov     rdx, [rbp+var_10]
0x140003f01  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140003f05  xor     r9d, r9d; dwFlags
0x140003f08  xor     r8d, r8d; pszImplementation
0x140003f0b  mov     rdx, [rdx]; pszAlgId
0x140003f0e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140003f14  mov     ebx, eax
0x140003f16  test    eax, eax
0x140003f18  jns     short loc_140003F42
0x140003f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f21  lea     rax, WPP_GLOBAL_Control
0x140003f28  cmp     rcx, rax
0x140003f2b  jz      loc_1400040DB
0x140003f31  test    byte ptr [rcx+1Ch], 1
0x140003f35  jz      loc_1400040DB
0x140003f3b  mov     edx, 0Ch
0x140003f40  jmp     short loc_140003EC9
0x140003f42  mov     r8, [rbp+var_10]
0x140003f46  lea     r9, [rbp+phKey]; phKey
0x140003f4a  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140003f4e  xor     edx, edx; hImportKey
0x140003f50  mov     [rsp+50h+dwFlags], r15d; dwFlags
0x140003f55  mov     eax, [r8+10h]
0x140003f59  mov     [rsp+50h+cbInput], eax; cbInput
0x140003f5d  mov     rax, [r8+18h]
0x140003f61  mov     r8, [r8+8]; pszBlobType
0x140003f65  mov     [rsp+50h+pbInput], rax; pbInput
0x140003f6a  call    cs:__imp_BCryptImportKeyPair
0x140003f70  mov     ebx, eax
0x140003f72  test    eax, eax
0x140003f74  jns     short loc_140003FA1
0x140003f76  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f7d  lea     rax, WPP_GLOBAL_Control
0x140003f84  cmp     rcx, rax
0x140003f87  jz      loc_1400040DB
0x140003f8d  test    byte ptr [rcx+1Ch], 1
0x140003f91  jz      loc_1400040DB
0x140003f97  mov     edx, 0Dh
0x140003f9c  jmp     loc_140003EC9
0x140003fa1  mov     rcx, [rbp+phKey]
0x140003fa5  lea     rax, [rbp+size]
0x140003fa9  mov     qword ptr [rsp+50h+dwFlags], rax
0x140003fae  xor     r9d, r9d
0x140003fb1  mov     qword ptr [rsp+50h+cbInput], r15
0x140003fb6  xor     r8d, r8d
0x140003fb9  mov     [rsp+50h+pbInput], r15
0x140003fbe  lea     edx, [r9+1]
0x140003fc2  call    cs:__imp_?iumCryptExportPublicKeyInfoFromBCryptKeyHandle@@YAHPEAXKPEADK0PEAU_CERT_PUBLIC_KEY_INFO@@PEAK@Z; iumCryptExportPublicKeyInfoFromBCryptKeyHandle(void *,ulong,char *,ulong,void *,_CERT_PUBLIC_KEY_INFO *,ulong *)
0x140003fc8  test    eax, eax
0x140003fca  jnz     short loc_14000403F
0x140003fcc  call    cs:__imp_GetLastError
0x140003fd2  test    eax, eax
0x140003fd4  jg      short loc_140003FE0
0x140003fd6  call    cs:__imp_GetLastError
0x140003fdc  mov     ebx, eax
0x140003fde  jmp     short loc_140003FEF
0x140003fe0  call    cs:__imp_GetLastError
0x140003fe6  movzx   ebx, ax
0x140003fe9  or      ebx, 0C0070000h
0x140003fef  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ff6  lea     rax, WPP_GLOBAL_Control
0x140003ffd  cmp     rcx, rax
0x140004000  jz      loc_1400040DB
0x140004006  test    byte ptr [rcx+1Ch], 1
0x14000400a  jz      loc_1400040DB
0x140004010  call    cs:__imp_GetLastError
0x140004016  mov     edx, 0Eh
0x14000401b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004022  lea     r9, aImportmachinek; "ImportMachineKey"
0x140004029  mov     [rsp+50h+cbInput], ebx
0x14000402d  mov     dword ptr [rsp+50h+pbInput], eax
0x140004031  mov     rcx, [rcx+10h]
0x140004035  call    WPP_SF_sdD
0x14000403a  jmp     loc_1400040DB
0x14000403f  mov     ecx, dword ptr [rbp+size]; size
0x140004042  call    MIDL_user_allocate
0x140004047  mov     [rsi], rax
0x14000404a  test    rax, rax
0x14000404d  jnz     short loc_140004059
0x14000404f  mov     ebx, 0C0000017h
0x140004054  jmp     loc_1400040DB
0x140004059  xor     r9d, r9d
0x14000405c  lea     rcx, [rbp+size]
0x140004060  mov     qword ptr [rsp+50h+dwFlags], rcx
0x140004065  xor     r8d, r8d
0x140004068  mov     rcx, [rbp+phKey]
0x14000406c  mov     qword ptr [rsp+50h+cbInput], rax
0x140004071  lea     edx, [r9+1]
0x140004075  mov     [rsp+50h+pbInput], r15
0x14000407a  call    cs:__imp_?iumCryptExportPublicKeyInfoFromBCryptKeyHandle@@YAHPEAXKPEADK0PEAU_CERT_PUBLIC_KEY_INFO@@PEAK@Z; iumCryptExportPublicKeyInfoFromBCryptKeyHandle(void *,ulong,char *,ulong,void *,_CERT_PUBLIC_KEY_INFO *,ulong *)
0x140004080  test    eax, eax
0x140004082  jnz     short loc_1400040D0
0x140004084  call    cs:__imp_GetLastError
0x14000408a  test    eax, eax
0x14000408c  jg      short loc_140004098
0x14000408e  call    cs:__imp_GetLastError
0x140004094  mov     ebx, eax
0x140004096  jmp     short loc_1400040A7
0x140004098  call    cs:__imp_GetLastError
0x14000409e  movzx   ebx, ax
0x1400040a1  or      ebx, 0C0070000h
0x1400040a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040ae  lea     rax, WPP_GLOBAL_Control
0x1400040b5  cmp     rcx, rax
0x1400040b8  jz      short loc_1400040DB
0x1400040ba  test    byte ptr [rcx+1Ch], 1
0x1400040be  jz      short loc_1400040DB
0x1400040c0  call    cs:__imp_GetLastError
0x1400040c6  mov     edx, 0Fh
0x1400040cb  jmp     loc_14000401B
0x1400040d0  mov     rax, [rbp+phKey]
0x1400040d4  mov     [r14], rax
0x1400040d7  mov     [rbp+phKey], r15
0x1400040db  mov     rcx, [rbp+phKey]; hKey
0x1400040df  test    rcx, rcx
0x1400040e2  jz      short loc_1400040EA
0x1400040e4  call    cs:__imp_BCryptDestroyKey
0x1400040ea  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400040ee  test    rcx, rcx
0x1400040f1  jz      short loc_1400040FB
0x1400040f3  xor     edx, edx; dwFlags
0x1400040f5  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400040fb  mov     rcx, [rbp+var_10]; void *
0x1400040ff  test    rcx, rcx
0x140004102  jz      short loc_140004109
0x140004104  call    SafeAllocaFreeToHeap
0x140004109  test    ebx, ebx
0x14000410b  jns     short loc_14000411D
0x14000410d  mov     rcx, [rsi]; void *
0x140004110  test    rcx, rcx
0x140004113  jz      short loc_14000411D
0x140004115  call    SafeAllocaFreeToHeap
0x14000411a  mov     [rsi], r15
0x14000411d  mov     rsi, [rsp+50h+arg_8]
0x140004122  mov     eax, ebx
0x140004124  mov     rbx, [rsp+50h+arg_0]
0x140004129  add     rsp, 50h
0x14000412d  pop     r15
0x14000412f  pop     r14
0x140004131  pop     rbp
0x140004132  retn
```
