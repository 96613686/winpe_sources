# GetCachedCommonRecoAttributes(_GUID *,tagRECO_ATTRS *,int,int)

- ea: `0x18007e92c`
- end: `0x18007ec46`
- name: `?GetCachedCommonRecoAttributes@@YAJPEAU_GUID@@PEAUtagRECO_ATTRS@@HH@Z`
- size: `794`
- prototype: `__int64 __fastcall(IID *rclsid, struct tagRECO_ATTRS *, int, int)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180068b50`
- `0x18006a260`
- `0x18007e640`
- `0x18007ec4c`
- `0x18007ec98`

## callees

- `0x18002e378`
- `0x18007aabc`
- `0x18007b048`
- `0x18007b270`
- `0x18007e92c`
- `0x18007f40c`
- `0x180104ece`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e9f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ea7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e9f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ea7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ea8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ea9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007eaaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ebed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ec13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ea8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ea9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007eaaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ebed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ec13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007eae4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007eb34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007eb93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ebda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007eae4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007eb34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007eb93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ebda`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007ea11`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007ea11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ea55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ea55`

## pseudocode

```c
__int64 __fastcall GetCachedCommonRecoAttributes(IID *rclsid, struct tagRECO_ATTRS *a2, int a3, int a4)
{
  int v7; // r8d
  HRESULT RecoAttributes; // edi
  const WCHAR *v9; // rdx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // rdi
  DWORD cbData; // [rsp+30h] [rbp-49h] BYREF
  DWORD Type; // [rsp+34h] [rbp-45h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-39h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-31h] BYREF
  HRECOGNIZER hrec; // [rsp+50h] [rbp-29h] BYREF
  WCHAR SubKey[48]; // [rsp+60h] [rbp-19h] BYREF

  if ( !a2 || !rclsid )
    return 2147500035LL;
  v7 = 0;
  hKey = 0;
  phkResult = 0;
  lpsz = 0;
  Type = 0;
  cbData = 0;
  if ( a4 )
  {
    hrec = 0;
    LOBYTE(v7) = a3 != 0;
    RecoAttributes = CreateCommonRecognizer(rclsid, &hrec, v7);
    if ( RecoAttributes >= 0 )
      RecoAttributes = GetRecoAttributes(hrec, a2);
    DestroyRecognizer(hrec);
    return (unsigned int)RecoAttributes;
  }
  v9 = L"Software\\Microsoft\\TPG\\System Recognizers";
  if ( !a3 )
    v9 = L"Software\\Microsoft\\TPG\\Recognizers";
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hKey) )
  {
    v10 = hKey;
    goto LABEL_15;
  }
  if ( StringFromCLSID(rclsid, &lpsz) >= 0 )
  {
    v11 = lpsz;
    if ( lpsz )
    {
      memset_0(SubKey, 0, 0x52u);
      StringCchCopyNW(SubKey, 0x29u, v11, 0x28u);
      CoTaskMemFree(lpsz);
      lpsz = 0;
      if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult) )
      {
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        cbData = 4;
        if ( !RegQueryValueExW(phkResult, L"Recognizer Capability Flags", 0, &Type, (LPBYTE)a2, &cbData)
          && Type == 4
          && cbData == 4 )
        {
          cbData = 128;
          if ( !RegQueryValueExW(phkResult, L"Recognized Languages", 0, &Type, (LPBYTE)a2->awLanguageId, &cbData)
            && Type == 3
            && cbData == 128 )
          {
            memset_0(a2->awcFriendlyName, 0, sizeof(a2->awcFriendlyName));
            cbData = 128;
            if ( RegQueryValueExW(phkResult, L"Recognizer Name", 0, 0, (LPBYTE)a2->awcFriendlyName, &cbData) )
              a2->awcFriendlyName[0] = 0;
            memset_0(a2->awcVendorName, 0, sizeof(a2->awcVendorName));
            cbData = 64;
            if ( RegQueryValueExW(phkResult, L"Vendor Name", 0, 0, (LPBYTE)a2->awcVendorName, &cbData) )
              a2->awcVendorName[0] = 0;
            RegCloseKey(phkResult);
            return (unsigned int)ValidateRecoAttrs(a2);
          }
        }
        v10 = phkResult;
        goto LABEL_16;
      }
      RegCloseKey(hKey);
      v10 = phkResult;
LABEL_15:
      if ( !v10 )
        return 2147746357LL;
LABEL_16:
      RegCloseKey(v10);
      return 2147746357LL;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18007e92c  mov     [rsp-8+arg_10], rbx
0x18007e931  mov     [rsp-8+arg_18], rdi
0x18007e936  push    rbp
0x18007e937  lea     rbp, [rsp-57h]
0x18007e93c  sub     rsp, 0D0h
0x18007e943  mov     rax, cs:__security_cookie
0x18007e94a  xor     rax, rsp
0x18007e94d  mov     [rbp+57h+var_10], rax
0x18007e951  mov     eax, r8d
0x18007e954  mov     rbx, rdx
0x18007e957  mov     rdi, rcx
0x18007e95a  test    rdx, rdx
0x18007e95d  jz      loc_18007EC20
0x18007e963  test    rcx, rcx
0x18007e966  jz      loc_18007EC20
0x18007e96c  xor     r8d, r8d; ulOptions
0x18007e96f  mov     [rbp+57h+hKey], 0
0x18007e977  mov     [rbp+57h+var_98], 0
0x18007e97f  mov     [rbp+57h+lpsz], 0
0x18007e987  mov     [rbp+57h+Type], 0
0x18007e98e  mov     [rbp+57h+cbData], 0
0x18007e995  test    r9d, r9d
0x18007e998  jz      short loc_18007E9CF
0x18007e99a  test    eax, eax
0x18007e99c  mov     [rbp+57h+hrec], r8
0x18007e9a0  lea     rdx, [rbp+57h+hrec]; HRECOGNIZER *
0x18007e9a4  setnz   r8b; int
0x18007e9a8  call    ?CreateCommonRecognizer@@YAJPEAU_GUID@@PEAPEAUHRECOGNIZER__@@H@Z; CreateCommonRecognizer(_GUID *,HRECOGNIZER__ * *,int)
0x18007e9ad  mov     edi, eax
0x18007e9af  test    eax, eax
0x18007e9b1  js      short loc_18007E9C1
0x18007e9b3  mov     rcx, [rbp+57h+hrec]; hrec
0x18007e9b7  mov     rdx, rbx; pRecoAttrs
0x18007e9ba  call    GetRecoAttributes
0x18007e9bf  mov     edi, eax
0x18007e9c1  mov     rcx, [rbp+57h+hrec]; hrec
0x18007e9c5  call    DestroyRecognizer
0x18007e9ca  jmp     loc_18007EBFD
0x18007e9cf  test    eax, eax
0x18007e9d1  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\TPG\\System Recogn"...
0x18007e9d8  lea     rax, [rbp+57h+hKey]
0x18007e9dc  mov     r9d, 20019h; samDesired
0x18007e9e2  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18007e9e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007e9ee  jnz     short loc_18007E9F7
0x18007e9f0  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\TPG\\Recognizers"
0x18007e9f7  call    cs:__imp_RegOpenKeyExW
0x18007e9fd  test    eax, eax
0x18007e9ff  jz      short loc_18007EA0A
0x18007ea01  mov     rcx, [rbp+57h+hKey]
0x18007ea05  jmp     loc_18007EA95
0x18007ea0a  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x18007ea0e  mov     rcx, rdi; rclsid
0x18007ea11  call    cs:__imp_StringFromCLSID
0x18007ea17  test    eax, eax
0x18007ea19  js      loc_18007EC0A
0x18007ea1f  mov     rdi, [rbp+57h+lpsz]
0x18007ea23  test    rdi, rdi
0x18007ea26  jz      loc_18007EC0A
0x18007ea2c  xor     edx, edx; Val
0x18007ea2e  lea     rcx, [rbp+57h+SubKey]; void *
0x18007ea32  lea     r8d, [rdx+52h]; Size
0x18007ea36  call    memset_0
0x18007ea3b  mov     r9d, 28h ; '('; unsigned __int64
0x18007ea41  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x18007ea45  mov     r8, rdi; unsigned __int16 *
0x18007ea48  lea     edx, [r9+1]; unsigned __int64
0x18007ea4c  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18007ea51  mov     rcx, [rbp+57h+lpsz]; pv
0x18007ea55  call    cs:__imp_CoTaskMemFree
0x18007ea5b  mov     rcx, [rbp+57h+hKey]; hKey
0x18007ea5f  lea     rax, [rbp+57h+var_98]
0x18007ea63  mov     r9d, 20019h; samDesired
0x18007ea69  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18007ea6e  xor     r8d, r8d; ulOptions
0x18007ea71  mov     [rbp+57h+lpsz], 0
0x18007ea79  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18007ea7d  call    cs:__imp_RegOpenKeyExW
0x18007ea83  mov     rcx, [rbp+57h+hKey]; hKey
0x18007ea87  test    eax, eax
0x18007ea89  jz      short loc_18007EAAA
0x18007ea8b  call    cs:__imp_RegCloseKey
0x18007ea91  mov     rcx, [rbp+57h+var_98]; hKey
0x18007ea95  test    rcx, rcx
0x18007ea98  jz      short loc_18007EAA0
0x18007ea9a  call    cs:__imp_RegCloseKey
0x18007eaa0  mov     eax, 80040235h
0x18007eaa5  jmp     loc_18007EC25
0x18007eaaa  test    rcx, rcx
0x18007eaad  jz      short loc_18007EABD
0x18007eaaf  call    cs:__imp_RegCloseKey
0x18007eab5  mov     [rbp+57h+hKey], 0
0x18007eabd  mov     rcx, [rbp+57h+var_98]; hKey
0x18007eac1  lea     rax, [rbp+57h+cbData]
0x18007eac5  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18007eaca  lea     r9, [rbp+57h+Type]; lpType
0x18007eace  xor     r8d, r8d; lpReserved
0x18007ead1  mov     [rsp+0D0h+phkResult], rbx; lpData
0x18007ead6  lea     rdx, aRecognizerCapa; "Recognizer Capability Flags"
0x18007eadd  mov     [rbp+57h+cbData], 4
0x18007eae4  call    cs:__imp_RegQueryValueExW
0x18007eaea  test    eax, eax
0x18007eaec  jnz     loc_18007EC01
0x18007eaf2  cmp     [rbp+57h+Type], 4
0x18007eaf6  jnz     loc_18007EC01
0x18007eafc  cmp     [rbp+57h+cbData], 4
0x18007eb00  jnz     loc_18007EC01
0x18007eb06  lea     rcx, [rbp+57h+cbData]
0x18007eb0a  mov     [rbp+57h+cbData], 80h
0x18007eb11  mov     [rsp+0D0h+lpcbData], rcx; lpcbData
0x18007eb16  lea     rax, [rbx+0C4h]
0x18007eb1d  mov     rcx, [rbp+57h+var_98]; hKey
0x18007eb21  lea     r9, [rbp+57h+Type]; lpType
0x18007eb25  xor     r8d, r8d; lpReserved
0x18007eb28  mov     [rsp+0D0h+phkResult], rax; lpData
0x18007eb2d  lea     rdx, aRecognizedLang; "Recognized Languages"
0x18007eb34  call    cs:__imp_RegQueryValueExW
0x18007eb3a  test    eax, eax
0x18007eb3c  jnz     loc_18007EC01
0x18007eb42  cmp     [rbp+57h+Type], 3
0x18007eb46  jnz     loc_18007EC01
0x18007eb4c  cmp     [rbp+57h+cbData], 80h
0x18007eb53  jnz     loc_18007EC01
0x18007eb59  lea     rdi, [rbx+44h]
0x18007eb5d  xor     edx, edx; Val
0x18007eb5f  mov     rcx, rdi; void *
0x18007eb62  mov     r8d, 80h; Size
0x18007eb68  call    memset_0
0x18007eb6d  mov     rcx, [rbp+57h+var_98]; hKey
0x18007eb71  lea     rax, [rbp+57h+cbData]
0x18007eb75  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18007eb7a  lea     rdx, aRecognizerName; "Recognizer Name"
0x18007eb81  xor     r9d, r9d; lpType
0x18007eb84  mov     [rsp+0D0h+phkResult], rdi; lpData
0x18007eb89  xor     r8d, r8d; lpReserved
0x18007eb8c  mov     [rbp+57h+cbData], 80h
0x18007eb93  call    cs:__imp_RegQueryValueExW
0x18007eb99  test    eax, eax
0x18007eb9b  jz      short loc_18007EBA2
0x18007eb9d  xor     eax, eax
0x18007eb9f  mov     [rdi], ax
0x18007eba2  xor     edx, edx; Val
0x18007eba4  lea     rdi, [rbx+4]
0x18007eba8  mov     rcx, rdi; void *
0x18007ebab  lea     r8d, [rdx+40h]; Size
0x18007ebaf  call    memset_0
0x18007ebb4  mov     rcx, [rbp+57h+var_98]; hKey
0x18007ebb8  lea     rax, [rbp+57h+cbData]
0x18007ebbc  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18007ebc1  lea     rdx, aVendorName; "Vendor Name"
0x18007ebc8  xor     r9d, r9d; lpType
0x18007ebcb  mov     [rsp+0D0h+phkResult], rdi; lpData
0x18007ebd0  xor     r8d, r8d; lpReserved
0x18007ebd3  mov     [rbp+57h+cbData], 40h ; '@'
0x18007ebda  call    cs:__imp_RegQueryValueExW
0x18007ebe0  test    eax, eax
0x18007ebe2  jz      short loc_18007EBE9
0x18007ebe4  xor     eax, eax
0x18007ebe6  mov     [rdi], ax
0x18007ebe9  mov     rcx, [rbp+57h+var_98]; hKey
0x18007ebed  call    cs:__imp_RegCloseKey
0x18007ebf3  mov     rcx, rbx; struct tagRECO_ATTRS *
0x18007ebf6  call    ?ValidateRecoAttrs@@YAJPEAUtagRECO_ATTRS@@@Z; ValidateRecoAttrs(tagRECO_ATTRS *)
0x18007ebfb  mov     edi, eax
0x18007ebfd  mov     eax, edi
0x18007ebff  jmp     short loc_18007EC25
0x18007ec01  mov     rcx, [rbp+57h+var_98]
0x18007ec05  jmp     loc_18007EA9A
0x18007ec0a  mov     rcx, [rbp+57h+hKey]; hKey
0x18007ec0e  test    rcx, rcx
0x18007ec11  jz      short loc_18007EC19
0x18007ec13  call    cs:__imp_RegCloseKey
0x18007ec19  mov     eax, 8007000Eh
0x18007ec1e  jmp     short loc_18007EC25
0x18007ec20  mov     eax, 80004003h
0x18007ec25  mov     rcx, [rbp+57h+var_10]
0x18007ec29  xor     rcx, rsp; StackCookie
0x18007ec2c  call    __security_check_cookie
0x18007ec31  lea     r11, [rsp+0D0h+var_s0]
0x18007ec39  mov     rbx, [r11+20h]
0x18007ec3d  mov     rdi, [r11+28h]
0x18007ec41  mov     rsp, r11
0x18007ec44  pop     rbp
0x18007ec45  retn
```
