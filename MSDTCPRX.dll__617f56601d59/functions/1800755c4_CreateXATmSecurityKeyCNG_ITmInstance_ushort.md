# CreateXATmSecurityKeyCNG(ITmInstance *,ushort *)

- ea: `0x1800755c4`
- end: `0x180075b06`
- name: `?CreateXATmSecurityKeyCNG@@YAJPEAUITmInstance@@PEAG@Z`
- size: `1346`
- prototype: `__int64 __fastcall(struct ITmInstance *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000fe94`

## callees

- `0x180003cf0`
- `0x18001d178`
- `0x18001d184`
- `0x1800755c4`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x180075757`
- `bcrypt!BCryptSetProperty` at `0x180075757`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007566b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007571c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007566b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007571c`
- `bcrypt!BCryptGetProperty` at `0x1800757b0`
- `bcrypt!BCryptGetProperty` at `0x1800757b0`
- `bcrypt!BCryptDestroyKey` at `0x180075a91`
- `bcrypt!BCryptDestroyKey` at `0x180075a91`
- `bcrypt!BCryptExportKey` at `0x180075895`
- `bcrypt!BCryptExportKey` at `0x180075925`
- `bcrypt!BCryptExportKey` at `0x180075895`
- `bcrypt!BCryptExportKey` at `0x180075925`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180075a71`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180075a82`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180075a71`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180075a82`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180075840`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180075840`
- `bcrypt!BCryptGenRandom` at `0x1800756d5`
- `bcrypt!BCryptGenRandom` at `0x1800756d5`

## string_xrefs

- `0x1800755fd`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x1800756a8`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x1800759fd`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x180075a4d`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x1800755f1`: `Entering CreateXATmSecurityKeyCNG`
- `0x18007561c`: `CreateXATmSecurityKeyCNG`
- `0x18007569d`: `CreateXATmSecurityKeyCNG`
- `0x1800756f1`: `CreateXATmSecurityKeyCNG`
- `0x180075773`: `CreateXATmSecurityKeyCNG`
- `0x1800757cc`: `CreateXATmSecurityKeyCNG`
- `0x180075803`: `CreateXATmSecurityKeyCNG`
- `0x18007585c`: `CreateXATmSecurityKeyCNG`
- `0x1800758b1`: `CreateXATmSecurityKeyCNG`
- `0x1800758e8`: `CreateXATmSecurityKeyCNG`
- `0x180075941`: `CreateXATmSecurityKeyCNG`
- `0x1800759e4`: `CreateXATmSecurityKeyCNG`
- `0x180075691`: `Error from BCryptOpenAlgorithmProvider(%s)`
- `0x18007595a`: `Security\XAKeyCNGKeyDataBlob`
- `0x18007597e`: `Security\XAKeyCNGKeyDataBlob`
- `0x1800759d8`: `Security\XAKeyCNGKeyDataBlob`
- `0x180075a1d`: `Security\XAKeyCNGKeyDataBlob`
- `0x1800759eb`: `Error from ITmInstance::SetRegistryValue : KeyName = %s, ValueName = %s`
- `0x180075990`: `Error from ITmInstance::CreateRegistryKey : KeyName = %s`
- `0x180075a37`: `DeleteRegistryKey(XAKeyCNG) call failed`

## pseudocode

```c
__int64 __fastcall CreateXATmSecurityKeyCNG(struct ITmInstance *a1, unsigned __int16 *a2)
{
  UCHAR *v5; // rsi
  UCHAR *v6; // rdi
  NTSTATUS v7; // ebx
  const WCHAR *v8; // rax
  __int64 v9; // r9
  int v10; // ebx
  const wchar_t *v11; // rax
  NTSTATUS v12; // ebx
  NTSTATUS v13; // ebx
  NTSTATUS Property; // ebx
  NTSTATUS v15; // ebx
  NTSTATUS v16; // ebx
  UCHAR *v17; // rax
  NTSTATUS v18; // ebx
  int v19; // eax
  __int64 v20; // rax
  UCHAR *v21; // rcx
  __int64 v22; // rax
  UCHAR *v23; // rcx
  ULONG cbSecret[2]; // [rsp+28h] [rbp-41h]
  ULONG cbSecreta[2]; // [rsp+28h] [rbp-41h]
  ULONG cbSecretb[2]; // [rsp+28h] [rbp-41h]
  ULONG cbSecretc[2]; // [rsp+28h] [rbp-41h]
  ULONG cbSecretd[2]; // [rsp+28h] [rbp-41h]
  ULONG cbSecrete[2]; // [rsp+28h] [rbp-41h]
  const wchar_t *v30; // [rsp+38h] [rbp-31h]
  ULONG cbOutput; // [rsp+50h] [rbp-19h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-15h] BYREF
  BCRYPT_ALG_HANDLE hObject; // [rsp+58h] [rbp-11h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-9h] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp-1h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+70h] [rbp+7h] BYREF
  UCHAR pbBuffer[16]; // [rsp+78h] [rbp+Fh] BYREF

  phAlgorithm = 0;
  hObject = 0;
  *(_DWORD *)pbOutput = 0;
  phKey = 0;
  cbOutput = 0;
  TraceStringInline(
    7,
    5,
    L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
    99,
    L"CreateXATmSecurityKeyCNG",
    0,
    L"Entering CreateXATmSecurityKeyCNG");
  if ( !a2 )
    return 2147942487LL;
  v5 = 0;
  v6 = 0;
  v7 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", L"Microsoft Primitive Provider", 0);
  if ( v7 )
  {
    v8 = L"RNG";
    v9 = 116;
  }
  else
  {
    v12 = BCryptGenRandom(phAlgorithm, pbBuffer, 0x10u, 0);
    if ( v12 )
    {
      v10 = v12 | 0x10000000;
      cbSecret[0] = v10;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
        128,
        L"CreateXATmSecurityKeyCNG",
        *(_QWORD *)cbSecret,
        L"Error from BCryptGenRandom");
      goto LABEL_30;
    }
    v7 = BCryptOpenAlgorithmProvider(&hObject, L"AES", L"Microsoft Primitive Provider", 0);
    if ( !v7 )
    {
      v13 = BCryptSetProperty(hObject, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
      if ( v13 )
      {
        v10 = v13 | 0x10000000;
        cbSecret[0] = v10;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
          154,
          L"CreateXATmSecurityKeyCNG",
          *(_QWORD *)cbSecret,
          L"Error from BCryptSetProperty(BCRYPT_CHAINING_MODE)");
        goto LABEL_30;
      }
      pcbResult = 4;
      Property = BCryptGetProperty(hObject, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
      if ( Property )
      {
        v10 = Property | 0x10000000;
        cbSecreta[0] = v10;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
          170,
          L"CreateXATmSecurityKeyCNG",
          *(_QWORD *)cbSecreta,
          L"Error from BCryptGetProperty(BCRYPT_OBJECT_LENGTH)");
        goto LABEL_30;
      }
      v5 = (UCHAR *)operator new[](*(unsigned int *)pbOutput);
      if ( !v5 )
      {
        cbSecreta[0] = -2147024882;
        v10 = -2147024882;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
          179,
          L"CreateXATmSecurityKeyCNG",
          *(_QWORD *)cbSecreta,
          L"Couldn't allocate memory for CNG Key object");
        goto LABEL_30;
      }
      v15 = BCryptGenerateSymmetricKey(hObject, &phKey, v5, *(ULONG *)pbOutput, pbBuffer, 0x10u, 0);
      if ( v15 )
      {
        v10 = v15 | 0x10000000;
        cbSecretb[0] = v10;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
          195,
          L"CreateXATmSecurityKeyCNG",
          *(_QWORD *)cbSecretb,
          L"Error from BCryptGenerateSymmetricKey");
        goto LABEL_30;
      }
      v16 = BCryptExportKey(phKey, 0, L"KeyDataBlob", 0, 0, &cbOutput, 0);
      if ( v16 )
      {
        v10 = v16 | 0x10000000;
        cbSecretc[0] = v10;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
          213,
          L"CreateXATmSecurityKeyCNG",
          *(_QWORD *)cbSecretc,
          L"Error from BCryptExportKey to get buffer size");
        goto LABEL_30;
      }
      v17 = (UCHAR *)operator new[](cbOutput);
      v6 = v17;
      if ( !v17 )
      {
        cbSecretc[0] = -2147024882;
        v10 = -2147024882;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
          221,
          L"CreateXATmSecurityKeyCNG",
          *(_QWORD *)cbSecretc,
          L"Couldn't allocate memory for exported CNG key.");
        goto LABEL_30;
      }
      v18 = BCryptExportKey(phKey, 0, L"KeyDataBlob", v17, cbOutput, &cbOutput, 0);
      if ( v18 )
      {
        v10 = v18 | 0x10000000;
        cbSecret[0] = v10;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
          237,
          L"CreateXATmSecurityKeyCNG",
          *(_QWORD *)cbSecret,
          L"Error from BCryptExportKey");
        goto LABEL_30;
      }
      v10 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, _QWORD, __int64, _QWORD))(*(_QWORD *)a1 + 416LL))(
              a1,
              L"Security\\XAKeyCNGKeyDataBlob",
              0,
              983103,
              0);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, unsigned __int16 *, __int64, UCHAR *, ULONG))(*(_QWORD *)a1 + 384LL))(
                a1,
                L"Security\\XAKeyCNGKeyDataBlob",
                a2,
                3,
                v6,
                cbOutput);
        if ( v10 < 0 )
        {
          cbSecretd[0] = v10;
          TraceStringInline(
            7,
            1,
            L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
            262,
            L"CreateXATmSecurityKeyCNG",
            *(_QWORD *)cbSecretd,
            L"Error from ITmInstance::SetRegistryValue : KeyName = %s, ValueName = %s",
            L"Security\\XAKeyCNGKeyDataBlob",
            a2);
          v19 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *))(*(_QWORD *)a1 + 424LL))(
                  a1,
                  L"Security\\XAKeyCNGKeyDataBlob");
          if ( v19 < 0 )
          {
            cbSecrete[0] = v19;
            TraceStringInline(
              7,
              1,
              L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
              266,
              L"CreateXATmSecurityKeyCNG",
              *(_QWORD *)cbSecrete,
              L"DeleteRegistryKey(XAKeyCNG) call failed");
          }
        }
        goto LABEL_30;
      }
      v30 = L"Security\\XAKeyCNGKeyDataBlob";
      v11 = L"Error from ITmInstance::CreateRegistryKey : KeyName = %s";
      v9 = 249;
      goto LABEL_6;
    }
    v8 = L"AES";
    v9 = 140;
  }
  v30 = v8;
  v10 = v7 | 0x10000000;
  v11 = L"Error from BCryptOpenAlgorithmProvider(%s)";
LABEL_6:
  cbSecret[0] = v10;
  TraceStringInline(
    7,
    1,
    L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
    v9,
    L"CreateXATmSecurityKeyCNG",
    *(_QWORD *)cbSecret,
    v11,
    v30);
LABEL_30:
  if ( hObject )
    BCryptCloseAlgorithmProvider(hObject, 0);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phKey )
    BCryptDestroyKey(phKey);
  v20 = *(unsigned int *)pbOutput;
  v21 = v5;
  if ( *(_DWORD *)pbOutput )
  {
    do
    {
      *v21++ = 0;
      --v20;
    }
    while ( v20 );
  }
  if ( v5 )
    operator delete(v5);
  v22 = cbOutput;
  v23 = v6;
  if ( cbOutput )
  {
    do
    {
      *v23++ = 0;
      --v22;
    }
    while ( v22 );
  }
  if ( v6 )
    operator delete(v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800755c4  mov     [rsp-8+arg_10], rbx
0x1800755c9  push    rbp
0x1800755ca  push    rsi
0x1800755cb  push    rdi
0x1800755cc  push    r12
0x1800755ce  push    r13
0x1800755d0  push    r14
0x1800755d2  push    r15
0x1800755d4  lea     rbp, [rsp-27h]
0x1800755d9  sub     rsp, 90h
0x1800755e0  mov     rax, cs:__security_cookie
0x1800755e7  xor     rax, rsp
0x1800755ea  mov     [rbp+57h+var_38], rax
0x1800755ee  xor     r12d, r12d
0x1800755f1  lea     rax, aEnteringCreate; "Entering CreateXATmSecurityKeyCNG"
0x1800755f8  mov     qword ptr [rsp+0C0h+var_90], rax
0x1800755fd  lea     r8, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x180075604  mov     r15, rdx
0x180075607  mov     qword ptr [rsp+0C0h+cbSecret], r12
0x18007560c  mov     r14, rcx
0x18007560f  mov     [rbp+57h+phAlgorithm], r12
0x180075613  lea     edx, [r12+5]
0x180075618  mov     [rbp+57h+hObject], r12
0x18007561c  lea     rax, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x180075623  mov     dword ptr [rbp+57h+pbOutput], r12d
0x180075627  lea     ecx, [rdx+2]
0x18007562a  mov     [rbp+57h+phKey], r12
0x18007562e  lea     r9d, [r12+63h]
0x180075633  mov     [rbp+57h+cbOutput], r12d
0x180075637  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18007563c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180075641  test    r15, r15
0x180075644  jnz     short loc_180075650
0x180075646  mov     eax, 80070057h
0x18007564b  jmp     loc_180075ADF
0x180075650  xor     r9d, r9d; dwFlags
0x180075653  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18007565a  lea     rdx, pszAlgId; "RNG"
0x180075661  mov     rsi, r12
0x180075664  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180075668  mov     rdi, r12
0x18007566b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180075671  mov     ebx, eax
0x180075673  mov     r13d, 1
0x180075679  test    eax, eax
0x18007567b  jz      short loc_1800756C6
0x18007567d  lea     rax, pszAlgId; "RNG"
0x180075684  lea     r9d, [r13+73h]
0x180075688  mov     [rsp+0C0h+var_88], rax
0x18007568d  bts     ebx, 1Ch
0x180075691  lea     rax, aErrorFromBcryp; "Error from BCryptOpenAlgorithmProvider("...
0x180075698  mov     qword ptr [rsp+0C0h+var_90], rax
0x18007569d  lea     r15, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x1800756a4  mov     [rsp+0C0h+cbSecret], ebx
0x1800756a8  lea     r8, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x1800756af  mov     edx, r13d
0x1800756b2  mov     qword ptr [rsp+0C0h+dwFlags], r15
0x1800756b7  mov     ecx, 7
0x1800756bc  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800756c1  jmp     loc_180075A66
0x1800756c6  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800756ca  lea     rdx, [rbp+57h+pbBuffer]; pbBuffer
0x1800756ce  xor     r9d, r9d; dwFlags
0x1800756d1  lea     r8d, [r9+10h]; cbBuffer
0x1800756d5  call    cs:__imp_BCryptGenRandom
0x1800756db  mov     ebx, eax
0x1800756dd  test    eax, eax
0x1800756df  jz      short loc_180075707
0x1800756e1  lea     rax, aErrorFromBcryp_5; "Error from BCryptGenRandom"
0x1800756e8  bts     ebx, 1Ch
0x1800756ec  mov     qword ptr [rsp+0C0h+var_90], rax
0x1800756f1  lea     r15, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x1800756f8  mov     [rsp+0C0h+cbSecret], ebx
0x1800756fc  mov     r9d, 80h
0x180075702  jmp     loc_180075A4D
0x180075707  xor     r9d, r9d; dwFlags
0x18007570a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180075711  lea     rdx, aAes; "AES"
0x180075718  lea     rcx, [rbp+57h+hObject]; phAlgorithm
0x18007571c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180075722  mov     ebx, eax
0x180075724  test    eax, eax
0x180075726  jz      short loc_18007573A
0x180075728  lea     rax, aAes; "AES"
0x18007572f  mov     r9d, 8Ch
0x180075735  jmp     loc_180075688
0x18007573a  mov     rcx, [rbp+57h+hObject]; hObject
0x18007573e  lea     r8, pbInput; "ChainingModeCBC"
0x180075745  mov     r9d, 20h ; ' '; cbInput
0x18007574b  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x180075750  lea     rdx, pszProperty; "ChainingMode"
0x180075757  call    cs:__imp_BCryptSetProperty
0x18007575d  mov     ebx, eax
0x18007575f  test    eax, eax
0x180075761  jz      short loc_180075789
0x180075763  lea     rax, aErrorFromBcryp_2; "Error from BCryptSetProperty(BCRYPT_CHA"...
0x18007576a  bts     ebx, 1Ch
0x18007576e  mov     qword ptr [rsp+0C0h+var_90], rax
0x180075773  lea     r15, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x18007577a  mov     [rsp+0C0h+cbSecret], ebx
0x18007577e  mov     r9d, 9Ah
0x180075784  jmp     loc_180075A4D
0x180075789  mov     rcx, [rbp+57h+hObject]; hObject
0x18007578d  lea     rax, [rbp+57h+pcbResult]
0x180075791  mov     r9d, 4; cbOutput
0x180075797  mov     [rsp+0C0h+cbSecret], r12d; dwFlags
0x18007579c  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x1800757a0  mov     [rbp+57h+pcbResult], r9d
0x1800757a4  lea     rdx, aObjectlength; "ObjectLength"
0x1800757ab  mov     qword ptr [rsp+0C0h+dwFlags], rax; pcbResult
0x1800757b0  call    cs:__imp_BCryptGetProperty
0x1800757b6  mov     ebx, eax
0x1800757b8  test    eax, eax
0x1800757ba  jz      short loc_1800757E2
0x1800757bc  lea     rax, aErrorFromBcryp_0; "Error from BCryptGetProperty(BCRYPT_OBJ"...
0x1800757c3  bts     ebx, 1Ch
0x1800757c7  mov     qword ptr [rsp+0C0h+var_90], rax
0x1800757cc  lea     r15, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x1800757d3  mov     [rsp+0C0h+cbSecret], ebx
0x1800757d7  mov     r9d, 0AAh
0x1800757dd  jmp     loc_180075A4D
0x1800757e2  mov     ecx, dword ptr [rbp+57h+pbOutput]; unsigned __int64
0x1800757e5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800757ea  mov     rsi, rax
0x1800757ed  test    rax, rax
0x1800757f0  jnz     short loc_18007581B
0x1800757f2  mov     ecx, 8007000Eh
0x1800757f7  lea     rax, aCouldnTAllocat; "Couldn't allocate memory for CNG Key ob"...
0x1800757fe  mov     qword ptr [rsp+0C0h+var_90], rax
0x180075803  lea     r15, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x18007580a  mov     [rsp+0C0h+cbSecret], ecx
0x18007580e  mov     ebx, ecx
0x180075810  mov     r9d, 0B3h
0x180075816  jmp     loc_180075A4D
0x18007581b  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbKeyObject
0x18007581f  lea     rax, [rbp+57h+pbBuffer]
0x180075823  mov     rcx, [rbp+57h+hObject]; hAlgorithm
0x180075827  lea     rdx, [rbp+57h+phKey]; phKey
0x18007582b  mov     [rsp+0C0h+var_90], r12d; dwFlags
0x180075830  mov     r8, rsi; pbKeyObject
0x180075833  mov     [rsp+0C0h+cbSecret], 10h; cbSecret
0x18007583b  mov     qword ptr [rsp+0C0h+dwFlags], rax; pbSecret
0x180075840  call    cs:__imp_BCryptGenerateSymmetricKey
0x180075846  mov     ebx, eax
0x180075848  test    eax, eax
0x18007584a  jz      short loc_180075872
0x18007584c  lea     rax, aErrorFromBcryp_4; "Error from BCryptGenerateSymmetricKey"
0x180075853  bts     ebx, 1Ch
0x180075857  mov     qword ptr [rsp+0C0h+var_90], rax
0x18007585c  lea     r15, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x180075863  mov     [rsp+0C0h+cbSecret], ebx
0x180075867  mov     r9d, 0C3h
0x18007586d  jmp     loc_180075A4D
0x180075872  mov     rcx, [rbp+57h+phKey]; hKey
0x180075876  lea     rax, [rbp+57h+cbOutput]
0x18007587a  mov     [rsp+0C0h+var_90], r12d; dwFlags
0x18007587f  lea     r8, pszBlobType; "KeyDataBlob"
0x180075886  mov     qword ptr [rsp+0C0h+cbSecret], rax; pcbResult
0x18007588b  xor     r9d, r9d; pbOutput
0x18007588e  xor     edx, edx; hExportKey
0x180075890  mov     [rsp+0C0h+dwFlags], r12d; cbOutput
0x180075895  call    cs:__imp_BCryptExportKey
0x18007589b  mov     ebx, eax
0x18007589d  test    eax, eax
0x18007589f  jz      short loc_1800758C7
0x1800758a1  lea     rax, aErrorFromBcryp_3; "Error from BCryptExportKey to get buffe"...
0x1800758a8  bts     ebx, 1Ch
0x1800758ac  mov     qword ptr [rsp+0C0h+var_90], rax
0x1800758b1  lea     r15, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x1800758b8  mov     [rsp+0C0h+cbSecret], ebx
0x1800758bc  mov     r9d, 0D5h
0x1800758c2  jmp     loc_180075A4D
0x1800758c7  mov     ecx, [rbp+57h+cbOutput]; unsigned __int64
0x1800758ca  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800758cf  mov     rdi, rax
0x1800758d2  test    rax, rax
0x1800758d5  jnz     short loc_180075900
0x1800758d7  mov     ecx, 8007000Eh
0x1800758dc  lea     rax, aCouldnTAllocat_0; "Couldn't allocate memory for exported C"...
0x1800758e3  mov     qword ptr [rsp+0C0h+var_90], rax
0x1800758e8  lea     r15, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x1800758ef  mov     [rsp+0C0h+cbSecret], ecx
0x1800758f3  mov     ebx, ecx
0x1800758f5  mov     r9d, 0DDh
0x1800758fb  jmp     loc_180075A4D
0x180075900  mov     rcx, [rbp+57h+phKey]; hKey
0x180075904  lea     rax, [rbp+57h+cbOutput]
0x180075908  mov     [rsp+0C0h+var_90], r12d; dwFlags
0x18007590d  lea     r8, pszBlobType; "KeyDataBlob"
0x180075914  mov     qword ptr [rsp+0C0h+cbSecret], rax; pcbResult
0x180075919  mov     r9, rdi; pbOutput
0x18007591c  mov     eax, [rbp+57h+cbOutput]
0x18007591f  xor     edx, edx; hExportKey
0x180075921  mov     [rsp+0C0h+dwFlags], eax; cbOutput
0x180075925  call    cs:__imp_BCryptExportKey
0x18007592b  mov     ebx, eax
0x18007592d  test    eax, eax
0x18007592f  jz      short loc_180075957
0x180075931  lea     rax, aErrorFromBcryp_1; "Error from BCryptExportKey"
0x180075938  bts     ebx, 1Ch
0x18007593c  mov     qword ptr [rsp+0C0h+var_90], rax
0x180075941  lea     r15, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x180075948  mov     [rsp+0C0h+cbSecret], ebx
0x18007594c  mov     r9d, 0EDh
0x180075952  jmp     loc_180075A4D
0x180075957  mov     rax, [r14]
0x18007595a  lea     rdx, aSecurityXakeyc_0; "Security\\XAKeyCNGKeyDataBlob"
0x180075961  mov     r9d, 0F003Fh
0x180075967  mov     qword ptr [rsp+0C0h+dwFlags], r12
0x18007596c  xor     r8d, r8d
0x18007596f  mov     rcx, r14
0x180075972  mov     rax, [rax+1A0h]
0x180075979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007597e  lea     rdx, aSecurityXakeyc_0; "Security\\XAKeyCNGKeyDataBlob"
0x180075985  mov     ebx, eax
0x180075987  test    eax, eax
0x180075989  jns     short loc_1800759A2
0x18007598b  mov     [rsp+0C0h+var_88], rdx
0x180075990  lea     rax, aErrorFromItmin; "Error from ITmInstance::CreateRegistryK"...
0x180075997  mov     r9d, 0F9h
0x18007599d  jmp     loc_180075698
0x1800759a2  mov     ecx, [rbp+57h+cbOutput]
0x1800759a5  mov     r9d, 3
0x1800759ab  mov     rax, [r14]
0x1800759ae  mov     r8, r15
0x1800759b1  mov     [rsp+0C0h+cbSecret], ecx
0x1800759b5  mov     rcx, r14
0x1800759b8  mov     qword ptr [rsp+0C0h+dwFlags], rdi
0x1800759bd  mov     rax, [rax+180h]
0x1800759c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800759c9  mov     ebx, eax
0x1800759cb  test    eax, eax
0x1800759cd  jns     loc_180075A66
0x1800759d3  mov     [rsp+0C0h+var_80], r15
0x1800759d8  lea     rax, aSecurityXakeyc_0; "Security\\XAKeyCNGKeyDataBlob"
0x1800759df  mov     [rsp+0C0h+var_88], rax
0x1800759e4  lea     r15, aCreatexatmsecu; "CreateXATmSecurityKeyCNG"
0x1800759eb  lea     rax, aErrorFromItmin_3; "Error from ITmInstance::SetRegistryValu"...
0x1800759f2  mov     r9d, 106h
0x1800759f8  mov     qword ptr [rsp+0C0h+var_90], rax
0x1800759fd  lea     r8, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x180075a04  mov     [rsp+0C0h+cbSecret], ebx
0x180075a08  mov     edx, r13d
0x180075a0b  mov     ecx, 7
0x180075a10  mov     qword ptr [rsp+0C0h+dwFlags], r15
0x180075a15  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180075a1a  mov     rax, [r14]
0x180075a1d  lea     rdx, aSecurityXakeyc_0; "Security\\XAKeyCNGKeyDataBlob"
0x180075a24  mov     rcx, r14
0x180075a27  mov     rax, [rax+1A8h]
0x180075a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a33  test    eax, eax
0x180075a35  jns     short loc_180075A66
0x180075a37  lea     rcx, aDeleteregistry; "DeleteRegistryKey(XAKeyCNG) call failed"
0x180075a3e  mov     r9d, 10Ah
0x180075a44  mov     qword ptr [rsp+0C0h+var_90], rcx
0x180075a49  mov     [rsp+0C0h+cbSecret], eax
0x180075a4d  lea     r8, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x180075a54  mov     qword ptr [rsp+0C0h+dwFlags], r15
0x180075a59  mov     edx, r13d
0x180075a5c  mov     ecx, 7
0x180075a61  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180075a66  mov     rcx, [rbp+57h+hObject]; hAlgorithm
0x180075a6a  test    rcx, rcx
0x180075a6d  jz      short loc_180075A77
0x180075a6f  xor     edx, edx; dwFlags
0x180075a71  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180075a77  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180075a7b  test    rcx, rcx
0x180075a7e  jz      short loc_180075A88
0x180075a80  xor     edx, edx; dwFlags
0x180075a82  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180075a88  mov     rcx, [rbp+57h+phKey]; hKey
0x180075a8c  test    rcx, rcx
0x180075a8f  jz      short loc_180075A97
0x180075a91  call    cs:__imp_BCryptDestroyKey
0x180075a97  mov     eax, dword ptr [rbp+57h+pbOutput]
0x180075a9a  mov     rcx, rsi
0x180075a9d  test    rax, rax
0x180075aa0  jz      short loc_180075AAD
0x180075aa2  mov     [rcx], r12b
0x180075aa5  add     rcx, r13
0x180075aa8  sub     rax, r13
0x180075aab  jnz     short loc_180075AA2
0x180075aad  test    rsi, rsi
0x180075ab0  jz      short loc_180075ABA
0x180075ab2  mov     rcx, rsi; Block
0x180075ab5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180075aba  mov     eax, [rbp+57h+cbOutput]
0x180075abd  mov     rcx, rdi
0x180075ac0  test    rax, rax
0x180075ac3  jz      short loc_180075AD0
0x180075ac5  mov     [rcx], r12b
0x180075ac8  add     rcx, r13
0x180075acb  sub     rax, r13
0x180075ace  jnz     short loc_180075AC5
0x180075ad0  test    rdi, rdi
0x180075ad3  jz      short loc_180075ADD
0x180075ad5  mov     rcx, rdi; Block
0x180075ad8  call    ??3@YAXPEAX@Z; operator delete(void *)
  ... truncated ...
```
