# DrvRecoveryLoadInfo(HDRIVERSTORE__ *,ushort const *,_DRVRECOVERY_INFO * *)

- ea: `0x18003abbc`
- end: `0x18003b1b5`
- name: `?DrvRecoveryLoadInfo@@YAHPEAUHDRIVERSTORE__@@PEBGPEAPEAU_DRVRECOVERY_INFO@@@Z`
- size: `1529`
- prototype: `__int64 __fastcall(struct HDRIVERSTORE__ *, const unsigned __int16 *, struct _DRVRECOVERY_INFO **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180029104`

## callees

- `0x180038fe0`
- `0x18003a960`
- `0x18003abbc`
- `0x18003b1bc`
- `0x18003b3f4`
- `0x18003b6ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003acce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003acce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ac2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b189`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ac2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b189`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ac5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ad82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003adda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ae1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ae82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aecf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003af25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003af72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003afbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b008`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b057`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b0a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b0f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b13b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ac5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ad82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003adda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ae1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ae82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aecf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003af25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003af72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003afbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b008`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b057`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b0a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b0f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b13b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003aca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003acb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003acc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003aca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003acb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003acc6`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003ad4f`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003ad4f`

## string_xrefs

- `0x18003ae17`: `CreateTime`
- `0x18003aec8`: `ReplacementFlags`

## pseudocode

```c
_BOOL8 __fastcall DrvRecoveryLoadInfo(
        struct HDRIVERSTORE__ *a1,
        const unsigned __int16 *a2,
        struct _DRVRECOVERY_INFO **a3)
{
  struct _DRVRECOVERY_INFO *v3; // rdi
  HKEY RecordRoot; // r15
  DWORD LastError; // ebx
  LSTATUS v9; // eax
  DWORD v10; // r8d
  DWORD v12; // eax
  BYTE *v13; // rsi
  int v14; // ebx
  unsigned int v15; // eax
  LSTATUS v16; // eax
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  struct _DRVRECOVERY_INFO *v20; // [rsp+40h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  hKey = 0;
  v20 = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  phkResult = 0;
  RecordRoot = pDrvRecoveryGetRecordRoot(a1);
  if ( !RecordRoot )
  {
    LastError = GetLastError();
    goto LABEL_13;
  }
  LastError = RegOpenKeyExW(RecordRoot, a2, 0, 0x20019u, &hKey);
  if ( !LastError )
  {
    v9 = RegQueryValueExW(hKey, L"DriverPackageIds", 0, &Type, 0, &cbData);
    LastError = v9;
    if ( v9 == 122 )
    {
      v10 = cbData;
    }
    else if ( v9 == 2 )
    {
      v10 = 0;
      cbData = 0;
    }
    else
    {
      if ( v9 )
        goto LABEL_13;
      if ( Type != 7 )
        goto LABEL_10;
      v10 = cbData;
      if ( cbData < 2 )
        goto LABEL_10;
    }
    if ( !pDrvRecoveryCreateInfo(a1, a2, v10 + 696, &v20) )
    {
      v12 = GetLastError();
      v3 = v20;
      LastError = v12;
LABEL_11:
      if ( v3 )
        DrvRecoveryDestroyInfo(v3);
      goto LABEL_13;
    }
    v3 = v20;
    v13 = (BYTE *)v20 + 612;
    DevRtlWriteTextLog(*((_QWORD *)v20 + 70), 512, 4, "Instance ID: %ws", (char *)v20 + 612);
    if ( cbData
      && (RegQueryValueExW(hKey, L"DriverPackageIds", 0, &Type, (LPBYTE)v3 + 690, &cbData)
       || Type != 7
       || cbData + 696LL != *(_DWORD *)v3)
      || (cbData = 4, RegQueryValueExW(hKey, L"State", 0, &Type, (LPBYTE)v3 + 568, &cbData))
      || Type != 4
      || cbData != 4
      || (cbData = 8, RegQueryValueExW(hKey, L"CreateTime", 0, &Type, (LPBYTE)v3 + 576, &cbData))
      || Type != 11
      || (v14 = 0, cbData != 8) )
    {
      v14 = 1;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::GetImpl'::`2'::impl) )
    {
      if ( v14 )
        goto LABEL_10;
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"RebootCount", 0, &Type, (LPBYTE)v3 + 584, &cbData) )
        goto LABEL_10;
      if ( Type != 4 )
        goto LABEL_10;
      if ( cbData != 4 )
        goto LABEL_10;
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"ReplacementFlags", 0, &Type, (LPBYTE)v3 + 588, &cbData) || Type != 4 || cbData != 4 )
        goto LABEL_10;
    }
    else if ( v14 )
    {
      goto LABEL_10;
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"DeviceMethodId", 0, &Type, (LPBYTE)v3 + 600, &cbData) )
      goto LABEL_10;
    if ( Type != 4 )
      goto LABEL_10;
    if ( cbData != 4 )
      goto LABEL_10;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"DriverMethodId", 0, &Type, (LPBYTE)v3 + 604, &cbData) )
      goto LABEL_10;
    if ( Type != 4 )
      goto LABEL_10;
    if ( cbData != 4 )
      goto LABEL_10;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"ActionResult", 0, &Type, (LPBYTE)v3 + 608, &cbData) )
      goto LABEL_10;
    if ( Type != 4 )
      goto LABEL_10;
    if ( cbData != 4 )
      goto LABEL_10;
    cbData = 78;
    if ( RegQueryValueExW(hKey, L"InstanceId", 0, &Type, v13, &cbData) )
      goto LABEL_10;
    if ( Type != 1 )
      goto LABEL_10;
    if ( cbData < 0x4E )
      goto LABEL_10;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Type", 0, &Type, (LPBYTE)v3 + 572, &cbData) )
      goto LABEL_10;
    if ( Type != 4 )
      goto LABEL_10;
    if ( cbData != 4 )
      goto LABEL_10;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"DataState", 0, &Type, (LPBYTE)v3 + 596, &cbData) )
      goto LABEL_10;
    if ( Type != 4 )
      goto LABEL_10;
    if ( cbData != 4 )
      goto LABEL_10;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"BehaviorFlags", 0, &Type, (LPBYTE)v3 + 592, &cbData) || Type != 4 || cbData != 4 )
      goto LABEL_10;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Hash", 0, &Type, Data, &cbData) || Type != 4 || cbData != 4 )
      v14 = 1;
    v15 = pDrvRecoveryCalculateInfoHash(v3);
    if ( *(_DWORD *)Data != v15 || v14 )
      goto LABEL_10;
    v16 = RegOpenKeyExW(hKey, L"InProgress", 0, 0x20019u, &phkResult);
    if ( v16 == 2 )
    {
      *((_DWORD *)v3 + 138) = 0;
LABEL_75:
      *a3 = v3;
      LastError = 0;
      goto LABEL_13;
    }
    if ( !v16 )
    {
      *((_DWORD *)v3 + 138) = 1;
      goto LABEL_75;
    }
LABEL_10:
    LastError = 13;
    goto LABEL_11;
  }
LABEL_13:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( RecordRoot )
    RegCloseKey(RecordRoot);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18003abbc  mov     [rsp-28h+arg_0], rbx
0x18003abc1  mov     [rsp-28h+arg_8], rsi
0x18003abc6  push    rbp
0x18003abc7  push    rdi
0x18003abc8  push    r12
0x18003abca  push    r14
0x18003abcc  push    r15
0x18003abce  mov     rbp, rsp
0x18003abd1  sub     rsp, 50h
0x18003abd5  xor     edi, edi
0x18003abd7  mov     [rbp+hKey], 0
0x18003abdf  mov     [rbp+var_10], rdi
0x18003abe3  mov     r12, r8
0x18003abe6  mov     [rbp+Type], edi
0x18003abe9  mov     r14, rdx
0x18003abec  mov     [rbp+cbData], edi
0x18003abef  mov     rsi, rcx
0x18003abf2  mov     dword ptr [rbp+Data], edi
0x18003abf5  mov     [rbp+var_8], 0
0x18003abfd  call    ?pDrvRecoveryGetRecordRoot@@YAPEAUHKEY__@@PEAUHDRIVERSTORE__@@@Z; pDrvRecoveryGetRecordRoot(HDRIVERSTORE__ *)
0x18003ac02  mov     r15, rax
0x18003ac05  test    rax, rax
0x18003ac08  jnz     short loc_18003AC17
0x18003ac0a  call    cs:__imp_GetLastError
0x18003ac10  mov     ebx, eax
0x18003ac12  jmp     loc_18003ACA0
0x18003ac17  lea     rax, [rbp+hKey]
0x18003ac1b  mov     r9d, 20019h; samDesired
0x18003ac21  xor     r8d, r8d; ulOptions
0x18003ac24  mov     [rsp+50h+phkResult], rax; phkResult
0x18003ac29  mov     rdx, r14; lpSubKey
0x18003ac2c  mov     rcx, r15; hKey
0x18003ac2f  call    cs:__imp_RegOpenKeyExW
0x18003ac35  mov     ebx, eax
0x18003ac37  test    eax, eax
0x18003ac39  jnz     short loc_18003ACA0
0x18003ac3b  mov     rcx, [rbp+hKey]; hKey
0x18003ac3f  lea     rax, [rbp+cbData]
0x18003ac43  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003ac48  lea     r9, [rbp+Type]; lpType
0x18003ac4c  xor     r8d, r8d; lpReserved
0x18003ac4f  mov     [rsp+50h+phkResult], rdi; lpData
0x18003ac54  lea     rdx, aDriverpackagei; "DriverPackageIds"
0x18003ac5b  call    cs:__imp_RegQueryValueExW
0x18003ac61  mov     ebx, eax
0x18003ac63  cmp     eax, 7Ah ; 'z'
0x18003ac66  jz      loc_18003ACF4
0x18003ac6c  cmp     eax, 2
0x18003ac6f  jnz     short loc_18003AC7A
0x18003ac71  xor     r8d, r8d
0x18003ac74  mov     [rbp+cbData], r8d
0x18003ac78  jmp     short loc_18003ACF8
0x18003ac7a  test    eax, eax
0x18003ac7c  jnz     short loc_18003ACA0
0x18003ac7e  cmp     [rbp+Type], 7
0x18003ac82  jnz     short loc_18003AC8E
0x18003ac84  mov     r8d, [rbp+cbData]
0x18003ac88  cmp     r8d, 2
0x18003ac8c  jnb     short loc_18003ACF8
0x18003ac8e  mov     ebx, 0Dh
0x18003ac93  test    rdi, rdi
0x18003ac96  jz      short loc_18003ACA0
0x18003ac98  mov     rcx, rdi; struct _DRVRECOVERY_INFO *
0x18003ac9b  call    ?DrvRecoveryDestroyInfo@@YAXPEAU_DRVRECOVERY_INFO@@@Z; DrvRecoveryDestroyInfo(_DRVRECOVERY_INFO *)
0x18003aca0  mov     rcx, [rbp+var_8]; hKey
0x18003aca4  test    rcx, rcx
0x18003aca7  jz      short loc_18003ACAF
0x18003aca9  call    cs:__imp_RegCloseKey
0x18003acaf  mov     rcx, [rbp+hKey]; hKey
0x18003acb3  test    rcx, rcx
0x18003acb6  jz      short loc_18003ACBE
0x18003acb8  call    cs:__imp_RegCloseKey
0x18003acbe  test    r15, r15
0x18003acc1  jz      short loc_18003ACCC
0x18003acc3  mov     rcx, r15; hKey
0x18003acc6  call    cs:__imp_RegCloseKey
0x18003accc  mov     ecx, ebx; dwErrCode
0x18003acce  call    cs:__imp_SetLastError
0x18003acd4  xor     eax, eax
0x18003acd6  lea     r11, [rsp+50h+var_s0]
0x18003acdb  mov     rsi, [r11+38h]
0x18003acdf  test    ebx, ebx
0x18003ace1  mov     rbx, [r11+30h]
0x18003ace5  setz    al
0x18003ace8  mov     rsp, r11
0x18003aceb  pop     r15
0x18003aced  pop     r14
0x18003acef  pop     r12
0x18003acf1  pop     rdi
0x18003acf2  pop     rbp
0x18003acf3  retn
0x18003acf4  mov     r8d, [rbp+cbData]
0x18003acf8  add     r8d, 2B8h; unsigned int
0x18003acff  lea     r9, [rbp+var_10]; struct _DRVRECOVERY_INFO **
0x18003ad03  mov     rdx, r14; unsigned __int16 *
0x18003ad06  mov     rcx, rsi; struct HDRIVERSTORE__ *
0x18003ad09  call    ?pDrvRecoveryCreateInfo@@YAHPEAUHDRIVERSTORE__@@PEBGKPEAPEAU_DRVRECOVERY_INFO@@@Z; pDrvRecoveryCreateInfo(HDRIVERSTORE__ *,ushort const *,ulong,_DRVRECOVERY_INFO * *)
0x18003ad0e  test    eax, eax
0x18003ad10  jnz     short loc_18003AD23
0x18003ad12  call    cs:__imp_GetLastError
0x18003ad18  mov     rdi, [rbp+var_10]
0x18003ad1c  mov     ebx, eax
0x18003ad1e  jmp     loc_18003AC93
0x18003ad23  mov     rdi, [rbp+var_10]
0x18003ad27  lea     r9, aInstanceIdWs; "Instance ID: %ws"
0x18003ad2e  mov     r14d, 4
0x18003ad34  mov     edx, 200h
0x18003ad39  mov     r8d, r14d
0x18003ad3c  mov     rcx, [rdi+230h]
0x18003ad43  lea     rsi, [rdi+264h]
0x18003ad4a  mov     [rsp+50h+phkResult], rsi
0x18003ad4f  call    cs:__imp_DevRtlWriteTextLog
0x18003ad55  cmp     [rbp+cbData], 0
0x18003ad59  jz      short loc_18003ADAF
0x18003ad5b  lea     rcx, [rbp+cbData]
0x18003ad5f  xor     r8d, r8d; lpReserved
0x18003ad62  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18003ad67  lea     rax, [rdi+2B2h]
0x18003ad6e  mov     rcx, [rbp+hKey]; hKey
0x18003ad72  lea     r9, [rbp+Type]; lpType
0x18003ad76  lea     rdx, aDriverpackagei; "DriverPackageIds"
0x18003ad7d  mov     [rsp+50h+phkResult], rax; lpData
0x18003ad82  call    cs:__imp_RegQueryValueExW
0x18003ad88  test    eax, eax
0x18003ad8a  jnz     loc_18003AE36
0x18003ad90  cmp     [rbp+Type], 7
0x18003ad94  jnz     loc_18003AE36
0x18003ad9a  mov     ecx, [rbp+cbData]
0x18003ad9d  mov     eax, [rdi]
0x18003ad9f  add     rcx, 2B8h
0x18003ada6  cmp     rcx, rax
0x18003ada9  jnz     loc_18003AE36
0x18003adaf  lea     rcx, [rbp+cbData]
0x18003adb3  mov     [rbp+cbData], r14d
0x18003adb7  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18003adbc  lea     rax, [rdi+238h]
0x18003adc3  mov     rcx, [rbp+hKey]; hKey
0x18003adc7  lea     r9, [rbp+Type]; lpType
0x18003adcb  xor     r8d, r8d; lpReserved
0x18003adce  mov     [rsp+50h+phkResult], rax; lpData
0x18003add3  lea     rdx, aState; "State"
0x18003adda  call    cs:__imp_RegQueryValueExW
0x18003ade0  test    eax, eax
0x18003ade2  jnz     short loc_18003AE36
0x18003ade4  cmp     [rbp+Type], r14d
0x18003ade8  jnz     short loc_18003AE36
0x18003adea  cmp     [rbp+cbData], r14d
0x18003adee  jnz     short loc_18003AE36
0x18003adf0  lea     rcx, [rbp+cbData]
0x18003adf4  mov     [rbp+cbData], 8
0x18003adfb  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18003ae00  lea     rax, [rdi+240h]
0x18003ae07  mov     rcx, [rbp+hKey]; hKey
0x18003ae0b  lea     r9, [rbp+Type]; lpType
0x18003ae0f  xor     r8d, r8d; lpReserved
0x18003ae12  mov     [rsp+50h+phkResult], rax; lpData
0x18003ae17  lea     rdx, aCreatetime; "CreateTime"
0x18003ae1e  call    cs:__imp_RegQueryValueExW
0x18003ae24  test    eax, eax
0x18003ae26  jnz     short loc_18003AE36
0x18003ae28  cmp     [rbp+Type], 0Bh
0x18003ae2c  jnz     short loc_18003AE36
0x18003ae2e  xor     ebx, ebx
0x18003ae30  cmp     [rbp+cbData], 8
0x18003ae34  jz      short loc_18003AE3B
0x18003ae36  mov     ebx, 1
0x18003ae3b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DriverRecovery_DataFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DriverRecovery_DataFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverRecovery_DataFix> `wil::Feature<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::GetImpl(void)'::`2'::impl
0x18003ae42  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DriverRecovery_DataFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::__private_IsEnabled(void)
0x18003ae47  test    al, al
0x18003ae49  jz      loc_18003AEF2
0x18003ae4f  test    ebx, ebx
0x18003ae51  jnz     loc_18003AC8E
0x18003ae57  lea     rcx, [rbp+cbData]
0x18003ae5b  mov     [rbp+cbData], r14d
0x18003ae5f  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18003ae64  lea     rax, [rdi+248h]
0x18003ae6b  mov     rcx, [rbp+hKey]; hKey
0x18003ae6f  lea     r9, [rbp+Type]; lpType
0x18003ae73  xor     r8d, r8d; lpReserved
0x18003ae76  mov     [rsp+50h+phkResult], rax; lpData
0x18003ae7b  lea     rdx, aRebootcount; "RebootCount"
0x18003ae82  call    cs:__imp_RegQueryValueExW
0x18003ae88  test    eax, eax
0x18003ae8a  jnz     loc_18003AC8E
0x18003ae90  cmp     [rbp+Type], r14d
0x18003ae94  jnz     loc_18003AC8E
0x18003ae9a  cmp     [rbp+cbData], r14d
0x18003ae9e  jnz     loc_18003AC8E
0x18003aea4  lea     rcx, [rbp+cbData]
0x18003aea8  mov     [rbp+cbData], r14d
0x18003aeac  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18003aeb1  lea     rax, [rdi+24Ch]
0x18003aeb8  mov     rcx, [rbp+hKey]; hKey
0x18003aebc  lea     r9, [rbp+Type]; lpType
0x18003aec0  xor     r8d, r8d; lpReserved
0x18003aec3  mov     [rsp+50h+phkResult], rax; lpData
0x18003aec8  lea     rdx, aReplacementfla; "ReplacementFlags"
0x18003aecf  call    cs:__imp_RegQueryValueExW
0x18003aed5  test    eax, eax
0x18003aed7  jnz     loc_18003AC8E
0x18003aedd  cmp     [rbp+Type], r14d
0x18003aee1  jnz     loc_18003AC8E
0x18003aee7  cmp     [rbp+cbData], r14d
0x18003aeeb  jz      short loc_18003AEFA
0x18003aeed  jmp     loc_18003AC8E
0x18003aef2  test    ebx, ebx
0x18003aef4  jnz     loc_18003AC8E
0x18003aefa  lea     rcx, [rbp+cbData]
0x18003aefe  mov     [rbp+cbData], r14d
0x18003af02  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18003af07  lea     rax, [rdi+258h]
0x18003af0e  mov     rcx, [rbp+hKey]; hKey
0x18003af12  lea     r9, [rbp+Type]; lpType
0x18003af16  xor     r8d, r8d; lpReserved
0x18003af19  mov     [rsp+50h+phkResult], rax; lpData
0x18003af1e  lea     rdx, aDevicemethodid; "DeviceMethodId"
0x18003af25  call    cs:__imp_RegQueryValueExW
0x18003af2b  test    eax, eax
0x18003af2d  jnz     loc_18003AC8E
0x18003af33  cmp     [rbp+Type], r14d
0x18003af37  jnz     loc_18003AC8E
0x18003af3d  cmp     [rbp+cbData], r14d
0x18003af41  jnz     loc_18003AC8E
0x18003af47  lea     rcx, [rbp+cbData]
0x18003af4b  mov     [rbp+cbData], r14d
0x18003af4f  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18003af54  lea     rax, [rdi+25Ch]
0x18003af5b  mov     rcx, [rbp+hKey]; hKey
0x18003af5f  lea     r9, [rbp+Type]; lpType
0x18003af63  xor     r8d, r8d; lpReserved
0x18003af66  mov     [rsp+50h+phkResult], rax; lpData
0x18003af6b  lea     rdx, aDrivermethodid; "DriverMethodId"
0x18003af72  call    cs:__imp_RegQueryValueExW
0x18003af78  test    eax, eax
0x18003af7a  jnz     loc_18003AC8E
0x18003af80  cmp     [rbp+Type], r14d
0x18003af84  jnz     loc_18003AC8E
0x18003af8a  cmp     [rbp+cbData], r14d
0x18003af8e  jnz     loc_18003AC8E
0x18003af94  lea     rcx, [rbp+cbData]
0x18003af98  mov     [rbp+cbData], r14d
0x18003af9c  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18003afa1  lea     rax, [rdi+260h]
0x18003afa8  mov     rcx, [rbp+hKey]; hKey
0x18003afac  lea     r9, [rbp+Type]; lpType
0x18003afb0  xor     r8d, r8d; lpReserved
0x18003afb3  mov     [rsp+50h+phkResult], rax; lpData
0x18003afb8  lea     rdx, aActionresult; "ActionResult"
0x18003afbf  call    cs:__imp_RegQueryValueExW
0x18003afc5  test    eax, eax
0x18003afc7  jnz     loc_18003AC8E
0x18003afcd  cmp     [rbp+Type], r14d
0x18003afd1  jnz     loc_18003AC8E
0x18003afd7  cmp     [rbp+cbData], r14d
0x18003afdb  jnz     loc_18003AC8E
0x18003afe1  mov     rcx, [rbp+hKey]; hKey
0x18003afe5  lea     rax, [rbp+cbData]
0x18003afe9  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003afee  lea     r9, [rbp+Type]; lpType
0x18003aff2  xor     r8d, r8d; lpReserved
0x18003aff5  mov     [rsp+50h+phkResult], rsi; lpData
0x18003affa  lea     rdx, aInstanceid; "InstanceId"
0x18003b001  mov     [rbp+cbData], 4Eh ; 'N'
0x18003b008  call    cs:__imp_RegQueryValueExW
0x18003b00e  test    eax, eax
0x18003b010  jnz     loc_18003AC8E
0x18003b016  lea     esi, [rax+1]
0x18003b019  cmp     [rbp+Type], esi
0x18003b01c  jnz     loc_18003AC8E
0x18003b022  cmp     [rbp+cbData], 4Eh ; 'N'
0x18003b026  jb      loc_18003AC8E
0x18003b02c  lea     rcx, [rbp+cbData]
0x18003b030  mov     [rbp+cbData], r14d
0x18003b034  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18003b039  lea     rax, [rdi+23Ch]
0x18003b040  mov     rcx, [rbp+hKey]; hKey
0x18003b044  lea     r9, [rbp+Type]; lpType
0x18003b048  xor     r8d, r8d; lpReserved
0x18003b04b  mov     [rsp+50h+phkResult], rax; lpData
0x18003b050  lea     rdx, aType; "Type"
0x18003b057  call    cs:__imp_RegQueryValueExW
0x18003b05d  test    eax, eax
0x18003b05f  jnz     loc_18003AC8E
0x18003b065  cmp     [rbp+Type], r14d
0x18003b069  jnz     loc_18003AC8E
0x18003b06f  cmp     [rbp+cbData], r14d
0x18003b073  jnz     loc_18003AC8E
0x18003b079  lea     rcx, [rbp+cbData]
0x18003b07d  mov     [rbp+cbData], r14d
0x18003b081  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18003b086  lea     rax, [rdi+254h]
0x18003b08d  mov     rcx, [rbp+hKey]; hKey
0x18003b091  lea     r9, [rbp+Type]; lpType
0x18003b095  xor     r8d, r8d; lpReserved
0x18003b098  mov     [rsp+50h+phkResult], rax; lpData
0x18003b09d  lea     rdx, aDatastate; "DataState"
0x18003b0a4  call    cs:__imp_RegQueryValueExW
0x18003b0aa  test    eax, eax
0x18003b0ac  jnz     loc_18003AC8E
0x18003b0b2  cmp     [rbp+Type], r14d
  ... truncated ...
```
