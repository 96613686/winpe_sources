# pDrvRecoveryWriteInfo(_DRVRECOVERY_INFO *)

- ea: `0x18003b988`
- end: `0x18003bd88`
- name: `?pDrvRecoveryWriteInfo@@YAHPEAU_DRVRECOVERY_INFO@@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(struct _DRVRECOVERY_INFO *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003a0e8`
- `0x18003a2ac`

## callees

- `0x180038fe0`
- `0x18003b1bc`
- `0x18003b6ec`
- `0x18003b988`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bd5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bd5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b9c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b9c3`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003bd27`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003bd27`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ba01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003bd18`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ba01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003bd18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ba3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ba71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bab6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003baf8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bb2a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bb5c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bb8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bbc0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bbf6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bc28`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bc5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bc8c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bccb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ba3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ba71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bab6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003baf8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bb2a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bb5c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bb8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bbc0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bbf6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bc28`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bc5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bc8c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bccb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bd36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bd45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bd53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bd36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bd45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bd53`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003bd76`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003bd76`

## string_xrefs

- `0x18003ba8f`: `CreateTime`
- `0x18003bb18`: `ReplacementFlags`

## pseudocode

```c
_BOOL8 __fastcall pDrvRecoveryWriteInfo(struct _DRVRECOVERY_INFO *a1)
{
  struct HDRIVERSTORE__ *v2; // rcx
  HKEY RecordRoot; // rsi
  DWORD LastError; // ebx
  LSTATUS v5; // eax
  HKEY phkResult; // [rsp+50h] [rbp-18h] BYREF
  unsigned int Data; // [rsp+A0h] [rbp+38h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+48h] BYREF
  __int64 v11; // [rsp+B8h] [rbp+50h] BYREF

  v2 = (struct HDRIVERSTORE__ *)*((_QWORD *)a1 + 1);
  hKey = 0;
  phkResult = 0;
  Data = 0;
  v11 = 0;
  dwDisposition = 0;
  RecordRoot = pDrvRecoveryGetRecordRoot(v2);
  if ( !RecordRoot )
  {
    LastError = GetLastError();
    goto LABEL_23;
  }
  LastError = RegCreateKeyExW(RecordRoot, (LPCWSTR)a1 + 8, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  if ( !LastError )
  {
    Data = pDrvRecoveryCalculateInfoHash(a1);
    LastError = RegSetValueExW(hKey, L"Hash", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !LastError )
    {
      LastError = RegSetValueExW(hKey, L"State", 0, 4u, (const BYTE *)a1 + 568, 4u);
      if ( !LastError )
      {
        v11 = *((_QWORD *)a1 + 72);
        LastError = RegSetValueExW(hKey, L"CreateTime", 0, 0xBu, (const BYTE *)&v11, 8u);
        if ( !LastError
          && (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::GetImpl'::`2'::impl)
           || (LastError = RegSetValueExW(hKey, L"RebootCount", 0, 4u, (const BYTE *)a1 + 584, 4u)) == 0
           && (LastError = RegSetValueExW(hKey, L"ReplacementFlags", 0, 4u, (const BYTE *)a1 + 588, 4u)) == 0) )
        {
          LastError = RegSetValueExW(hKey, L"DeviceMethodId", 0, 4u, (const BYTE *)a1 + 600, 4u);
          if ( !LastError )
          {
            LastError = RegSetValueExW(hKey, L"DriverMethodId", 0, 4u, (const BYTE *)a1 + 604, 4u);
            if ( !LastError )
            {
              LastError = RegSetValueExW(hKey, L"ActionResult", 0, 4u, (const BYTE *)a1 + 608, 4u);
              if ( !LastError )
              {
                LastError = RegSetValueExW(hKey, L"InstanceId", 0, 1u, (const BYTE *)a1 + 612, 0x4Eu);
                if ( !LastError )
                {
                  LastError = RegSetValueExW(hKey, L"Type", 0, 4u, (const BYTE *)a1 + 572, 4u);
                  if ( !LastError )
                  {
                    LastError = RegSetValueExW(hKey, L"DataState", 0, 4u, (const BYTE *)a1 + 596, 4u);
                    if ( !LastError )
                    {
                      LastError = RegSetValueExW(hKey, L"BehaviorFlags", 0, 4u, (const BYTE *)a1 + 592, 4u);
                      if ( !LastError
                        && (!*((_WORD *)a1 + 345)
                         || (LastError = RegSetValueExW(
                                           hKey,
                                           L"DriverPackageIds",
                                           0,
                                           7u,
                                           (const BYTE *)a1 + 690,
                                           *(_DWORD *)a1 - 696)) == 0) )
                      {
                        if ( *((_DWORD *)a1 + 138) )
                        {
                          v5 = RegCreateKeyExW(hKey, L"InProgress", 0, 0, 1u, 0x2001Fu, 0, &phkResult, 0);
                          LastError = v5;
                        }
                        else
                        {
                          v5 = RegDeleteKeyW(hKey, L"InProgress");
                          LastError = v5;
                          if ( v5 == 2 )
                          {
                            LastError = 0;
LABEL_22:
                            RegFlushKey(RecordRoot);
                            goto LABEL_23;
                          }
                        }
                        if ( v5 )
                          goto LABEL_23;
                        goto LABEL_22;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_23:
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
0x18003b988  push    rbp
0x18003b98a  push    rbx
0x18003b98b  push    rsi
0x18003b98c  push    rdi
0x18003b98d  push    r14
0x18003b98f  push    r15
0x18003b991  mov     rbp, rsp
0x18003b994  sub     rsp, 68h
0x18003b998  xor     r14d, r14d
0x18003b99b  mov     rdi, rcx
0x18003b99e  mov     rcx, [rcx+8]; struct HDRIVERSTORE__ *
0x18003b9a2  mov     [rbp+hKey], r14
0x18003b9a6  mov     [rbp+var_18], r14
0x18003b9aa  mov     [rbp+Data], r14d
0x18003b9ae  mov     [rbp+arg_18], r14
0x18003b9b2  mov     [rbp+dwDisposition], r14d
0x18003b9b6  call    ?pDrvRecoveryGetRecordRoot@@YAPEAUHKEY__@@PEAUHDRIVERSTORE__@@@Z; pDrvRecoveryGetRecordRoot(HDRIVERSTORE__ *)
0x18003b9bb  mov     rsi, rax
0x18003b9be  test    rax, rax
0x18003b9c1  jnz     short loc_18003B9D0
0x18003b9c3  call    cs:__imp_GetLastError
0x18003b9c9  mov     ebx, eax
0x18003b9cb  jmp     loc_18003BD2D
0x18003b9d0  lea     rax, [rbp+dwDisposition]
0x18003b9d4  xor     r9d, r9d; lpClass
0x18003b9d7  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18003b9dc  lea     rdx, [rdi+10h]; lpSubKey
0x18003b9e0  lea     rax, [rbp+hKey]
0x18003b9e4  xor     r8d, r8d; Reserved
0x18003b9e7  mov     [rsp+68h+phkResult], rax; phkResult
0x18003b9ec  mov     rcx, rsi; hKey
0x18003b9ef  mov     [rsp+68h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003b9f4  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x18003b9fc  mov     [rsp+68h+dwOptions], r14d; dwOptions
0x18003ba01  call    cs:__imp_RegCreateKeyExW
0x18003ba07  mov     ebx, eax
0x18003ba09  test    eax, eax
0x18003ba0b  jnz     loc_18003BD2D
0x18003ba11  mov     rcx, rdi; struct _DRVRECOVERY_INFO *
0x18003ba14  call    ?pDrvRecoveryCalculateInfoHash@@YAKPEAU_DRVRECOVERY_INFO@@@Z; pDrvRecoveryCalculateInfoHash(_DRVRECOVERY_INFO *)
0x18003ba19  mov     rcx, [rbp+hKey]; hKey
0x18003ba1d  lea     r15d, [rbx+4]
0x18003ba21  mov     [rbp+Data], eax
0x18003ba24  lea     rdx, aHash; "Hash"
0x18003ba2b  lea     rax, [rbp+Data]
0x18003ba2f  mov     [rsp+68h+samDesired], r15d; cbData
0x18003ba34  mov     r9d, r15d; dwType
0x18003ba37  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003ba3c  xor     r8d, r8d; Reserved
0x18003ba3f  call    cs:__imp_RegSetValueExW
0x18003ba45  mov     ebx, eax
0x18003ba47  test    eax, eax
0x18003ba49  jnz     loc_18003BD2D
0x18003ba4f  mov     rcx, [rbp+hKey]; hKey
0x18003ba53  lea     rax, [rdi+238h]
0x18003ba5a  mov     [rsp+68h+samDesired], r15d; cbData
0x18003ba5f  lea     rdx, aState; "State"
0x18003ba66  mov     r9d, r15d; dwType
0x18003ba69  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003ba6e  xor     r8d, r8d; Reserved
0x18003ba71  call    cs:__imp_RegSetValueExW
0x18003ba77  mov     ebx, eax
0x18003ba79  test    eax, eax
0x18003ba7b  jnz     loc_18003BD2D
0x18003ba81  mov     eax, [rdi+240h]
0x18003ba87  lea     r9d, [r15+7]; dwType
0x18003ba8b  mov     rcx, [rbp+hKey]; hKey
0x18003ba8f  lea     rdx, aCreatetime; "CreateTime"
0x18003ba96  mov     dword ptr [rbp+arg_18], eax
0x18003ba99  xor     r8d, r8d; Reserved
0x18003ba9c  mov     eax, [rdi+244h]
0x18003baa2  mov     dword ptr [rbp+arg_18+4], eax
0x18003baa5  lea     rax, [rbp+arg_18]
0x18003baa9  mov     [rsp+68h+samDesired], 8; cbData
0x18003bab1  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003bab6  call    cs:__imp_RegSetValueExW
0x18003babc  mov     ebx, eax
0x18003babe  test    eax, eax
0x18003bac0  jnz     loc_18003BD2D
0x18003bac6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DriverRecovery_DataFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DriverRecovery_DataFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverRecovery_DataFix> `wil::Feature<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::GetImpl(void)'::`2'::impl
0x18003bacd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DriverRecovery_DataFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::__private_IsEnabled(void)
0x18003bad2  test    al, al
0x18003bad4  jz      short loc_18003BB3A
0x18003bad6  mov     rcx, [rbp+hKey]; hKey
0x18003bada  lea     rax, [rdi+248h]
0x18003bae1  mov     [rsp+68h+samDesired], r15d; cbData
0x18003bae6  lea     rdx, aRebootcount; "RebootCount"
0x18003baed  mov     r9d, r15d; dwType
0x18003baf0  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003baf5  xor     r8d, r8d; Reserved
0x18003baf8  call    cs:__imp_RegSetValueExW
0x18003bafe  mov     ebx, eax
0x18003bb00  test    eax, eax
0x18003bb02  jnz     loc_18003BD2D
0x18003bb08  mov     rcx, [rbp+hKey]; hKey
0x18003bb0c  lea     rax, [rdi+24Ch]
0x18003bb13  mov     [rsp+68h+samDesired], r15d; cbData
0x18003bb18  lea     rdx, aReplacementfla; "ReplacementFlags"
0x18003bb1f  mov     r9d, r15d; dwType
0x18003bb22  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003bb27  xor     r8d, r8d; Reserved
0x18003bb2a  call    cs:__imp_RegSetValueExW
0x18003bb30  mov     ebx, eax
0x18003bb32  test    eax, eax
0x18003bb34  jnz     loc_18003BD2D
0x18003bb3a  mov     rcx, [rbp+hKey]; hKey
0x18003bb3e  lea     rax, [rdi+258h]
0x18003bb45  mov     [rsp+68h+samDesired], r15d; cbData
0x18003bb4a  lea     rdx, aDevicemethodid; "DeviceMethodId"
0x18003bb51  mov     r9d, r15d; dwType
0x18003bb54  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003bb59  xor     r8d, r8d; Reserved
0x18003bb5c  call    cs:__imp_RegSetValueExW
0x18003bb62  mov     ebx, eax
0x18003bb64  test    eax, eax
0x18003bb66  jnz     loc_18003BD2D
0x18003bb6c  mov     rcx, [rbp+hKey]; hKey
0x18003bb70  lea     rax, [rdi+25Ch]
0x18003bb77  mov     [rsp+68h+samDesired], r15d; cbData
0x18003bb7c  lea     rdx, aDrivermethodid; "DriverMethodId"
0x18003bb83  mov     r9d, r15d; dwType
0x18003bb86  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003bb8b  xor     r8d, r8d; Reserved
0x18003bb8e  call    cs:__imp_RegSetValueExW
0x18003bb94  mov     ebx, eax
0x18003bb96  test    eax, eax
0x18003bb98  jnz     loc_18003BD2D
0x18003bb9e  mov     rcx, [rbp+hKey]; hKey
0x18003bba2  lea     rax, [rdi+260h]
0x18003bba9  mov     [rsp+68h+samDesired], r15d; cbData
0x18003bbae  lea     rdx, aActionresult; "ActionResult"
0x18003bbb5  mov     r9d, r15d; dwType
0x18003bbb8  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003bbbd  xor     r8d, r8d; Reserved
0x18003bbc0  call    cs:__imp_RegSetValueExW
0x18003bbc6  mov     ebx, eax
0x18003bbc8  test    eax, eax
0x18003bbca  jnz     loc_18003BD2D
0x18003bbd0  mov     rcx, [rbp+hKey]; hKey
0x18003bbd4  lea     rax, [rdi+264h]
0x18003bbdb  mov     [rsp+68h+samDesired], 4Eh ; 'N'; cbData
0x18003bbe3  lea     r9d, [rbx+1]; dwType
0x18003bbe7  xor     r8d, r8d; Reserved
0x18003bbea  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003bbef  lea     rdx, aInstanceid; "InstanceId"
0x18003bbf6  call    cs:__imp_RegSetValueExW
0x18003bbfc  mov     ebx, eax
0x18003bbfe  test    eax, eax
0x18003bc00  jnz     loc_18003BD2D
0x18003bc06  mov     rcx, [rbp+hKey]; hKey
0x18003bc0a  lea     rax, [rdi+23Ch]
0x18003bc11  mov     [rsp+68h+samDesired], r15d; cbData
0x18003bc16  lea     rdx, aType; "Type"
0x18003bc1d  mov     r9d, r15d; dwType
0x18003bc20  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003bc25  xor     r8d, r8d; Reserved
0x18003bc28  call    cs:__imp_RegSetValueExW
0x18003bc2e  mov     ebx, eax
0x18003bc30  test    eax, eax
0x18003bc32  jnz     loc_18003BD2D
0x18003bc38  mov     rcx, [rbp+hKey]; hKey
0x18003bc3c  lea     rax, [rdi+254h]
0x18003bc43  mov     [rsp+68h+samDesired], r15d; cbData
0x18003bc48  lea     rdx, aDatastate; "DataState"
0x18003bc4f  mov     r9d, r15d; dwType
0x18003bc52  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003bc57  xor     r8d, r8d; Reserved
0x18003bc5a  call    cs:__imp_RegSetValueExW
0x18003bc60  mov     ebx, eax
0x18003bc62  test    eax, eax
0x18003bc64  jnz     loc_18003BD2D
0x18003bc6a  mov     rcx, [rbp+hKey]; hKey
0x18003bc6e  lea     rax, [rdi+250h]
0x18003bc75  mov     [rsp+68h+samDesired], r15d; cbData
0x18003bc7a  lea     rdx, aBehaviorflags; "BehaviorFlags"
0x18003bc81  mov     r9d, r15d; dwType
0x18003bc84  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003bc89  xor     r8d, r8d; Reserved
0x18003bc8c  call    cs:__imp_RegSetValueExW
0x18003bc92  mov     ebx, eax
0x18003bc94  test    eax, eax
0x18003bc96  jnz     loc_18003BD2D
0x18003bc9c  lea     rcx, [rdi+2B2h]
0x18003bca3  cmp     [rcx], r14w
0x18003bca7  jz      short loc_18003BCD7
0x18003bca9  mov     eax, [rdi]
0x18003bcab  lea     r9d, [rbx+7]; dwType
0x18003bcaf  sub     eax, 2B8h
0x18003bcb4  lea     rdx, aDriverpackagei; "DriverPackageIds"
0x18003bcbb  mov     [rsp+68h+samDesired], eax; cbData
0x18003bcbf  xor     r8d, r8d; Reserved
0x18003bcc2  mov     qword ptr [rsp+68h+dwOptions], rcx; lpData
0x18003bcc7  mov     rcx, [rbp+hKey]; hKey
0x18003bccb  call    cs:__imp_RegSetValueExW
0x18003bcd1  mov     ebx, eax
0x18003bcd3  test    eax, eax
0x18003bcd5  jnz     short loc_18003BD2D
0x18003bcd7  lea     rdx, aInprogress; "InProgress"
0x18003bcde  mov     rcx, [rbp+hKey]; hKey
0x18003bce2  cmp     [rdi+228h], r14d
0x18003bce9  jz      loc_18003BD76
0x18003bcef  mov     [rsp+68h+lpdwDisposition], r14; lpdwDisposition
0x18003bcf4  lea     rax, [rbp+var_18]
0x18003bcf8  mov     [rsp+68h+phkResult], rax; phkResult
0x18003bcfd  xor     r9d, r9d; lpClass
0x18003bd00  mov     [rsp+68h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003bd05  xor     r8d, r8d; Reserved
0x18003bd08  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x18003bd10  mov     [rsp+68h+dwOptions], 1; dwOptions
0x18003bd18  call    cs:__imp_RegCreateKeyExW
0x18003bd1e  mov     ebx, eax
0x18003bd20  test    eax, eax
0x18003bd22  jnz     short loc_18003BD2D
0x18003bd24  mov     rcx, rsi; hKey
0x18003bd27  call    cs:__imp_RegFlushKey
0x18003bd2d  mov     rcx, [rbp+var_18]; hKey
0x18003bd31  test    rcx, rcx
0x18003bd34  jz      short loc_18003BD3C
0x18003bd36  call    cs:__imp_RegCloseKey
0x18003bd3c  mov     rcx, [rbp+hKey]; hKey
0x18003bd40  test    rcx, rcx
0x18003bd43  jz      short loc_18003BD4B
0x18003bd45  call    cs:__imp_RegCloseKey
0x18003bd4b  test    rsi, rsi
0x18003bd4e  jz      short loc_18003BD59
0x18003bd50  mov     rcx, rsi; hKey
0x18003bd53  call    cs:__imp_RegCloseKey
0x18003bd59  mov     ecx, ebx; dwErrCode
0x18003bd5b  call    cs:__imp_SetLastError
0x18003bd61  test    ebx, ebx
0x18003bd63  mov     eax, r14d
0x18003bd66  setz    al
0x18003bd69  add     rsp, 68h
0x18003bd6d  pop     r15
0x18003bd6f  pop     r14
0x18003bd71  pop     rdi
0x18003bd72  pop     rsi
0x18003bd73  pop     rbx
0x18003bd74  pop     rbp
0x18003bd75  retn
0x18003bd76  call    cs:__imp_RegDeleteKeyW
0x18003bd7c  mov     ebx, eax
0x18003bd7e  cmp     eax, 2
0x18003bd81  jnz     short loc_18003BD20
0x18003bd83  mov     ebx, r14d
0x18003bd86  jmp     short loc_18003BD24
```
