# DcaMgr::DeviceCredentialMgr::CheckProvisionedDevice(ushort const *,bool *)

- ea: `0x180097f2c`
- end: `0x180098303`
- name: `?CheckProvisionedDevice@DeviceCredentialMgr@DcaMgr@@QEAAJPEBGPEA_N@Z`
- size: `983`
- prototype: `__int64 __fastcall(DcaMgr::DeviceCredentialMgr *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800853a0`
- `0x18009e960`

## callees

- `0x18000782c`
- `0x1800281e0`
- `0x180028200`
- `0x180032c20`
- `0x180048304`
- `0x18005bce8`
- `0x180097c6c`
- `0x180097cb4`
- `0x180097f2c`
- `0x18009982c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097f87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800980e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097f87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800980e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009812e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009812e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009816a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009816a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800980ac`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800980ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18009801b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18009801b`

## string_xrefs

- `0x180097fbe`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180098029`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009822b`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180098265`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180098296`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800982b5`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800982d1`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180098189`: `UserSid`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialMgr::CheckProvisionedDevice(
        DcaMgr::DeviceCredentialMgr *this,
        char *a2,
        bool *a3)
{
  int v5; // ebx
  bool v6; // sf
  unsigned int v7; // eax
  const char *v8; // r9
  WCHAR *v9; // rbx
  DWORD v10; // edi
  unsigned int v11; // eax
  unsigned int v12; // esi
  unsigned int v13; // eax
  int RegStringValue; // esi
  unsigned __int16 *v15; // rax
  int v16; // r8d
  int v17; // ecx
  int v19; // eax
  int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  unsigned int phkResultb; // [rsp+20h] [rbp-59h]
  unsigned int phkResultc; // [rsp+20h] [rbp-59h]
  int phkResultd; // [rsp+20h] [rbp-59h]
  DWORD cbData; // [rsp+60h] [rbp-19h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-15h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-11h] BYREF
  LPWSTR lpName; // [rsp+70h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-1h] BYREF
  char *v30; // [rsp+80h] [rbp+7h] BYREF
  HKEY *p_hKey; // [rsp+88h] [rbp+Fh] BYREF
  HKEY v32; // [rsp+90h] [rbp+17h] BYREF
  char v33; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DcaMgr::DeviceCredentialMgr *cbMaxSubKeyLen; // [rsp+E0h] [rbp+67h] BYREF
  DWORD cSubKeys; // [rsp+F0h] [rbp+77h] BYREF
  int Data; // [rsp+F8h] [rbp+7Fh] BYREF

  cbMaxSubKeyLen = this;
  v33 = 1;
  *a3 = 0;
  p_hKey = &hKey;
  hKey = 0;
  v32 = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Devices",
         0,
         0x20019u,
         &v32);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v5 )
  {
    if ( v5 != 2 )
    {
      v6 = v5 < 0;
      if ( v5 > 0 )
      {
        v5 = (unsigned __int16)v5 | 0x80070000;
        v6 = v5 < 0;
      }
      if ( v6 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x361,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
          (const char *)(unsigned int)v5,
          phkResult);
      goto LABEL_37;
    }
LABEL_29:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  cSubKeys = 0;
  LODWORD(cbMaxSubKeyLen) = 0;
  v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, (LPDWORD)&cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( !v7 )
  {
    if ( cSubKeys )
    {
      LODWORD(cbMaxSubKeyLen) = (_DWORD)cbMaxSubKeyLen + 1;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &lpName,
        0,
        (unsigned int)cbMaxSubKeyLen,
        v8);
      v9 = lpName;
      if ( lpName )
      {
        Data = 0;
        v10 = 0;
        cbData = 0;
        while ( 1 )
        {
          if ( v10 >= cSubKeys )
            goto LABEL_28;
          cchName = (unsigned int)cbMaxSubKeyLen;
          v11 = RegEnumKeyExW(hKey, v10, v9, &cchName, 0, 0, 0, 0);
          if ( v11 )
            break;
          p_hKey = &hkey;
          hkey = 0;
          v32 = 0;
          v33 = 1;
          v12 = RegOpenKeyExW(hKey, v9, 0, 0x20019u, &v32);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
          if ( v12 )
          {
            v19 = wil::details::in1diag3::Return_Win32Msg(
                    retaddr,
                    (void *)0x394,
                    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                    (const char *)v12,
                    (unsigned int)"DeviceId=%ws",
                    (const char *)v9);
            goto LABEL_32;
          }
          Data = 0;
          cbData = 4;
          v13 = RegQueryValueExW(hkey, L"State", 0, 0, (LPBYTE)&Data, &cbData);
          if ( v13 )
          {
            v19 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x39E,
                    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                    (const char *)v13,
                    phkResultc);
LABEL_32:
            v5 = v19;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            goto LABEL_36;
          }
          if ( Data == 1 && !RegGetValueW(hkey, 0, L"AuthKey", 8u, 0, 0, &cbData) )
          {
            if ( !a2 )
              goto LABEL_27;
            p_hKey = (HKEY *)&v30;
            v30 = 0;
            v32 = 0;
            v33 = 1;
            RegStringValue = ReadRegStringValue(hkey, 0, L"UserSid");
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
            if ( RegStringValue < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3B8,
                (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                (const char *)(unsigned int)RegStringValue,
                phkResultd);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v30);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
              v5 = RegStringValue;
              goto LABEL_37;
            }
            v15 = (unsigned __int16 *)v30;
            do
            {
              v16 = *(unsigned __int16 *)((char *)v15 + a2 - v30);
              v17 = *v15 - v16;
              if ( v17 )
                break;
              ++v15;
            }
            while ( v16 );
            if ( !v17 )
            {
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v30);
LABEL_27:
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
              *a3 = 1;
LABEL_28:
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
              goto LABEL_29;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v30);
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          ++v10;
        }
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x38A,
               (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
               (const char *)v11,
               phkResultb);
      }
      else
      {
        v5 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37A,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
          (const char *)0x8007000ELL,
          phkResulta);
      }
LABEL_36:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
      goto LABEL_37;
    }
    goto LABEL_29;
  }
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x375,
         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
         (const char *)v7,
         phkResulta);
LABEL_37:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180097f2c  mov     [rsp-8+cbMaxSubKeyLen], rcx
0x180097f31  push    rbp
0x180097f32  push    rbx
0x180097f33  push    rsi
0x180097f34  push    rdi
0x180097f35  push    r12
0x180097f37  push    r14
0x180097f39  push    r15
0x180097f3b  lea     rbp, [rsp-27h]
0x180097f40  sub     rsp, 0A0h
0x180097f47  xor     r12d, r12d
0x180097f4a  mov     [rbp+57h+var_38], 1
0x180097f4e  lea     rax, [rbp+57h+hKey]
0x180097f52  mov     [r8], r12b
0x180097f55  mov     [rbp+57h+var_48], rax
0x180097f59  mov     r15, r8
0x180097f5c  lea     rax, [rbp+57h+var_40]
0x180097f60  mov     [rbp+57h+hKey], r12
0x180097f64  mov     r14, rdx
0x180097f67  mov     [rsp+0D0h+phkResult], rax; int
0x180097f6c  mov     r9d, 20019h; samDesired
0x180097f72  mov     [rbp+57h+var_40], r12
0x180097f76  xor     r8d, r8d; ulOptions
0x180097f79  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180097f80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180097f87  call    cs:__imp_RegOpenKeyExW
0x180097f8d  lea     rcx, [rbp+57h+var_48]
0x180097f91  mov     ebx, eax
0x180097f93  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180097f98  test    ebx, ebx
0x180097f9a  jz      short loc_180097FD7
0x180097f9c  cmp     ebx, 2
0x180097f9f  jz      loc_18009820A
0x180097fa5  test    ebx, ebx
0x180097fa7  jle     short loc_180097FB4
0x180097fa9  movzx   ebx, bx
0x180097fac  or      ebx, 80070000h
0x180097fb2  test    ebx, ebx
0x180097fb4  jns     loc_1800982F3
0x180097fba  mov     rcx, [rbp+5Fh]; this
0x180097fbe  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180097fc5  mov     r9d, ebx; char *
0x180097fc8  mov     edx, 361h; void *
0x180097fcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097fd2  jmp     loc_1800982F3
0x180097fd7  mov     rcx, [rbp+57h+hKey]; hKey
0x180097fdb  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180097fdf  mov     [rsp+0D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180097fe4  xor     r9d, r9d; lpReserved
0x180097fe7  mov     [rsp+0D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180097fec  xor     r8d, r8d; lpcchClass
0x180097fef  mov     [rsp+0D0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180097ff4  xor     edx, edx; lpClass
0x180097ff6  mov     [rsp+0D0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180097ffb  mov     [rsp+0D0h+lpcValues], r12; lpcValues
0x180098000  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180098005  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18009800a  lea     rax, [rbp+57h+cSubKeys]
0x18009800e  mov     [rsp+0D0h+phkResult], rax; int
0x180098013  mov     [rbp+57h+cSubKeys], r12d
0x180098017  mov     dword ptr [rbp+57h+cbMaxSubKeyLen], r12d
0x18009801b  call    cs:__imp_RegQueryInfoKeyW
0x180098021  test    eax, eax
0x180098023  jz      short loc_180098044
0x180098025  mov     rcx, [rbp+5Fh]; this
0x180098029  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180098030  mov     r9d, eax; char *
0x180098033  mov     edx, 375h; void *
0x180098038  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009803d  mov     ebx, eax
0x18009803f  jmp     loc_1800982F3
0x180098044  cmp     [rbp+57h+cSubKeys], r12d
0x180098048  jz      loc_18009820A
0x18009804e  mov     eax, dword ptr [rbp+57h+cbMaxSubKeyLen]
0x180098051  lea     rcx, [rbp+57h+lpName]
0x180098055  inc     eax
0x180098057  xor     edx, edx
0x180098059  mov     r8d, eax
0x18009805c  mov     dword ptr [rbp+57h+cbMaxSubKeyLen], eax
0x18009805f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180098064  mov     rbx, [rbp+57h+lpName]
0x180098068  test    rbx, rbx
0x18009806b  jz      loc_1800982CD
0x180098071  mov     [rbp+57h+Data], r12d
0x180098075  mov     edi, r12d
0x180098078  mov     [rbp+57h+cbData], r12d
0x18009807c  cmp     edi, [rbp+57h+cSubKeys]
0x18009807f  jnb     loc_180098201
0x180098085  mov     eax, dword ptr [rbp+57h+cbMaxSubKeyLen]
0x180098088  lea     r9, [rbp+57h+cchName]; lpcchName
0x18009808c  mov     rcx, [rbp+57h+hKey]; hKey
0x180098090  mov     r8, rbx; lpName
0x180098093  mov     [rsp+0D0h+lpcValues], r12; lpftLastWriteTime
0x180098098  mov     edx, edi; dwIndex
0x18009809a  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcchClass
0x18009809f  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r12; lpClass
0x1800980a4  mov     [rsp+0D0h+phkResult], r12; unsigned int
0x1800980a9  mov     [rbp+57h+cchName], eax
0x1800980ac  call    cs:__imp_RegEnumKeyExW
0x1800980b2  test    eax, eax
0x1800980b4  jnz     loc_1800982B1
0x1800980ba  mov     rcx, [rbp+57h+hKey]; hKey
0x1800980be  lea     rax, [rbp+57h+hkey]
0x1800980c2  mov     [rbp+57h+var_48], rax
0x1800980c6  mov     r9d, 20019h; samDesired
0x1800980cc  lea     rax, [rbp+57h+var_40]
0x1800980d0  mov     [rbp+57h+hkey], r12
0x1800980d4  xor     r8d, r8d; ulOptions
0x1800980d7  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800980dc  mov     rdx, rbx; lpSubKey
0x1800980df  mov     [rbp+57h+var_40], r12
0x1800980e3  mov     [rbp+57h+var_38], 1
0x1800980e7  call    cs:__imp_RegOpenKeyExW
0x1800980ed  lea     rcx, [rbp+57h+var_48]
0x1800980f1  mov     esi, eax
0x1800980f3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800980f8  test    esi, esi
0x1800980fa  jnz     loc_180098286
0x180098100  mov     rcx, [rbp+57h+hkey]; hKey
0x180098104  lea     rax, [rbp+57h+cbData]
0x180098108  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18009810d  lea     rdx, aState; "State"
0x180098114  lea     rax, [rbp+57h+Data]
0x180098118  mov     [rbp+57h+Data], r12d
0x18009811c  xor     r9d, r9d; lpType
0x18009811f  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x180098124  xor     r8d, r8d; lpReserved
0x180098127  mov     [rbp+57h+cbData], 4
0x18009812e  call    cs:__imp_RegQueryValueExW
0x180098134  test    eax, eax
0x180098136  jnz     loc_180098261
0x18009813c  cmp     [rbp+57h+Data], 1
0x180098140  jnz     loc_1800981DF
0x180098146  mov     rcx, [rbp+57h+hkey]; hkey
0x18009814a  lea     rax, [rbp+57h+cbData]
0x18009814e  mov     [rsp+0D0h+lpcbMaxClassLen], rax; pcbData
0x180098153  lea     r9d, [rsi+8]; dwFlags
0x180098157  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r12; pvData
0x18009815c  lea     r8, aAuthkey; "AuthKey"
0x180098163  xor     edx, edx; lpSubKey
0x180098165  mov     [rsp+0D0h+phkResult], r12; int
0x18009816a  call    cs:__imp_RegGetValueW
0x180098170  test    eax, eax
0x180098172  jnz     short loc_1800981DF
0x180098174  test    r14, r14
0x180098177  jz      short loc_1800981F4
0x180098179  mov     rcx, [rbp+57h+hkey]; hkey
0x18009817d  lea     rax, [rbp+57h+var_50]
0x180098181  lea     r9, [rbp+57h+var_40]
0x180098185  mov     [rbp+57h+var_48], rax
0x180098189  lea     r8, aUsersid; "UserSid"
0x180098190  mov     [rbp+57h+var_50], r12
0x180098194  xor     edx, edx; lpSubKey
0x180098196  mov     [rbp+57h+var_40], r12
0x18009819a  mov     [rbp+57h+var_38], 1
0x18009819e  call    ReadRegStringValue
0x1800981a3  lea     rcx, [rbp+57h+var_48]
0x1800981a7  mov     esi, eax
0x1800981a9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800981ae  test    esi, esi
0x1800981b0  js      short loc_180098227
0x1800981b2  mov     rax, [rbp+57h+var_50]
0x1800981b6  mov     rdx, r14
0x1800981b9  sub     rdx, rax
0x1800981bc  movzx   ecx, word ptr [rax]
0x1800981bf  movzx   r8d, word ptr [rax+rdx]
0x1800981c4  sub     ecx, r8d
0x1800981c7  jnz     short loc_1800981D2
0x1800981c9  add     rax, 2
0x1800981cd  test    r8d, r8d
0x1800981d0  jnz     short loc_1800981BC
0x1800981d2  test    ecx, ecx
0x1800981d4  lea     rcx, [rbp+57h+var_50]; void *
0x1800981d8  jz      short loc_1800981EF
0x1800981da  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800981df  lea     rcx, [rbp+57h+hkey]
0x1800981e3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800981e8  inc     edi
0x1800981ea  jmp     loc_18009807C
0x1800981ef  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800981f4  lea     rcx, [rbp+57h+hkey]
0x1800981f8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800981fd  mov     byte ptr [r15], 1
0x180098201  lea     rcx, [rbp+57h+lpName]; void *
0x180098205  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18009820a  lea     rcx, [rbp+57h+hKey]
0x18009820e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098213  xor     eax, eax
0x180098215  add     rsp, 0A0h
0x18009821c  pop     r15
0x18009821e  pop     r14
0x180098220  pop     r12
0x180098222  pop     rdi
0x180098223  pop     rsi
0x180098224  pop     rbx
0x180098225  pop     rbp
0x180098226  retn
0x180098227  mov     rcx, [rbp+5Fh]; this
0x18009822b  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180098232  mov     r9d, esi; char *
0x180098235  mov     edx, 3B8h; void *
0x18009823a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009823f  lea     rcx, [rbp+57h+var_50]; void *
0x180098243  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180098248  lea     rcx, [rbp+57h+hkey]
0x18009824c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098251  lea     rcx, [rbp+57h+lpName]; void *
0x180098255  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18009825a  mov     ebx, esi
0x18009825c  jmp     loc_1800982F3
0x180098261  mov     rcx, [rbp+5Fh]; this
0x180098265  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009826c  mov     r9d, eax; char *
0x18009826f  mov     edx, 39Eh; void *
0x180098274  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180098279  lea     rcx, [rbp+57h+hkey]
0x18009827d  mov     ebx, eax
0x18009827f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098284  jmp     short loc_1800982EA
0x180098286  mov     rcx, [rbp+5Fh]; this
0x18009828a  lea     rax, aDeviceidWs; "DeviceId=%ws"
0x180098291  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rbx; char *
0x180098296  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009829d  mov     r9d, esi; char *
0x1800982a0  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x1800982a5  mov     edx, 394h; void *
0x1800982aa  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800982af  jmp     short loc_180098279
0x1800982b1  mov     rcx, [rbp+5Fh]; this
0x1800982b5  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800982bc  mov     r9d, eax; char *
0x1800982bf  mov     edx, 38Ah; void *
0x1800982c4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800982c9  mov     ebx, eax
0x1800982cb  jmp     short loc_1800982EA
0x1800982cd  mov     rcx, [rbp+5Fh]; this
0x1800982d1  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800982d8  mov     ebx, 8007000Eh
0x1800982dd  mov     edx, 37Ah; void *
0x1800982e2  mov     r9d, ebx; char *
0x1800982e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800982ea  lea     rcx, [rbp+57h+lpName]; void *
0x1800982ee  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800982f3  lea     rcx, [rbp+57h+hKey]
0x1800982f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800982fc  mov     eax, ebx
0x1800982fe  jmp     loc_180098215
```
