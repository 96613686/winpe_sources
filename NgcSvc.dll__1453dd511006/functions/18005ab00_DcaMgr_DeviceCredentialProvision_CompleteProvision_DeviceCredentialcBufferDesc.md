# DcaMgr::DeviceCredentialProvision::CompleteProvision(_DeviceCredentialcBufferDesc *)

- ea: `0x18005ab00`
- end: `0x18005aef0`
- name: `?CompleteProvision@DeviceCredentialProvision@DcaMgr@@UEAAJPEAU_DeviceCredentialcBufferDesc@@@Z`
- size: `1008`
- prototype: `__int64 __fastcall(DcaMgr::DeviceCredentialProvision *this, struct _DeviceCredentialcBufferDesc *, HKEY *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000782c`
- `0x1800281e0`
- `0x180032c20`
- `0x180047228`
- `0x180048304`
- `0x18004b7c4`
- `0x180050b30`
- `0x18005ab00`
- `0x18005b028`
- `0x18005bce8`
- `0x180069c28`
- `0x180097c6c`
- `0x180097cb4`
- `0x180098cfc`
- `0x180099258`
- `0x18009fec4`
- `0x1800a6408`
- `0x1800a7bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005ad17`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005ad17`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ac5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005acea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ac5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005acea`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005ae01`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005ae01`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18005ae84`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18005ae84`

## string_xrefs

- `0x18005ac17`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005ac6b`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005acac`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005acfb`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005ad9c`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005ae45`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005ae95`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005aed3`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialProvision::CompleteProvision(
        DcaMgr::DeviceCredentialProvision *this,
        struct _DeviceCredentialcBufferDesc *a2,
        HKEY *a3)
{
  __int64 v4; // rdi
  int v5; // esi
  unsigned int i; // ecx
  __int64 v7; // rsi
  __int64 v8; // rdx
  HRESULT RegStringValue; // ebx
  int v10; // ecx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // eax
  RTL_SRWLOCK *v14; // rax
  int v15; // eax
  unsigned int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  LSTATUS v23; // eax
  unsigned int lpData; // [rsp+20h] [rbp-40h]
  int lpDataa; // [rsp+20h] [rbp-40h]
  unsigned int lpDatab; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  BYTE *v29; // [rsp+38h] [rbp-28h] BYREF
  LPCVOID v30; // [rsp+40h] [rbp-20h] BYREF
  __int64 *p_hKey; // [rsp+48h] [rbp-18h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-10h] BYREF
  char v33; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF
  int Data; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v37; // [rsp+A8h] [rbp+48h] BYREF

  if ( *((_DWORD *)a2 + 1) > 1u || *((_DWORD *)a2 + 1) == 1 && !*((_QWORD *)a2 + 1) )
  {
    v8 = 557;
    goto LABEL_47;
  }
  v4 = 0;
  v5 = 0;
  for ( i = 0; i < *((_DWORD *)a2 + 1); ++i )
  {
    v7 = *((_QWORD *)a2 + 1);
    if ( *(_DWORD *)(v7 + 16LL * i) != 9 )
    {
      v8 = 572;
      goto LABEL_47;
    }
    v4 = *(_QWORD *)(v7 + 16LL * i + 8);
    v5 = *(_DWORD *)(v7 + 16LL * i + 4);
  }
  if ( v4 )
  {
    if ( (unsigned int)(v5 - 1) > 0xFFF )
      goto LABEL_11;
  }
  else if ( v5 )
  {
LABEL_11:
    v8 = 579;
LABEL_47:
    RegStringValue = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)0x80070057LL,
      lpData);
    return (unsigned int)RegStringValue;
  }
  hKey = 0;
  p_hKey = (__int64 *)&hKey;
  lpsz = 0;
  v33 = 1;
  RegStringValue = DcaMgr::OpenDeviceRegKey(*((LPCWSTR *)this + 1), (const unsigned __int16 *)&lpsz, a3);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( RegStringValue < 0 )
  {
    v11 = (unsigned int)RegStringValue;
    v12 = 582;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)v11,
      lpData);
    goto LABEL_42;
  }
  if ( v4 )
  {
    v29 = 0;
    cbData = 0;
    p_hKey = (__int64 *)&v29;
    lpsz = 0;
    v33 = 1;
    LOBYTE(v10) = 1;
    RegStringValue = DpapiProtectUnprotect(v10, v4, v5, (unsigned int)&lpsz, (__int64)&cbData);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hKey);
    if ( RegStringValue < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x252,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)(unsigned int)RegStringValue,
        lpDataa);
LABEL_18:
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v29);
LABEL_42:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return (unsigned int)RegStringValue;
    }
    v13 = RegSetValueExW(hKey, L"OpaqueBlob", 0, 3u, v29, cbData);
    if ( v13 )
    {
      RegStringValue = wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)0x25A,
                         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
                         (const char *)v13,
                         lpData);
      goto LABEL_18;
    }
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v29);
  }
  v14 = (RTL_SRWLOCK *)DcaMgr::DeviceCredentialMgr::Instance();
  v15 = DcaMgr::DeviceCredentialMgr::ProvisionDevice(v14, &hKey, *((const WCHAR **)this + 1));
  RegStringValue = v15;
  if ( v15 < 0 )
  {
    v11 = (unsigned int)v15;
    v12 = 607;
    goto LABEL_24;
  }
  Data = 1;
  v16 = RegSetValueExW(hKey, L"State", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v16 )
  {
    RegStringValue = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0x268,
                       (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
                       (const char *)v16,
                       lpDatab);
    goto LABEL_42;
  }
  RegFlushKey(hKey);
  v37 = 0;
  p_hKey = &v37;
  lpsz = 0;
  v33 = 1;
  RegStringValue = ReadRegStringValue(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
                     L"LastUnlockDeviceId");
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
  if ( RegStringValue < 0 )
  {
    if ( RegStringValue != -2147024894 )
    {
      v19 = (unsigned int)RegStringValue;
      v18 = 639;
      goto LABEL_32;
    }
    v17 = WriteRegStringValue(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
            (char *)L"LastUnlockDeviceId",
            *((LPCVOID *)this + 1));
    RegStringValue = v17;
    if ( v17 < 0 )
    {
      v18 = 635;
LABEL_31:
      v19 = (unsigned int)v17;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)v19,
        lpDatab);
LABEL_41:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v37);
      goto LABEL_42;
    }
  }
  v17 = WriteRegStringValue(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
          (char *)L"LastProvisionedAppId",
          *((LPCVOID *)this + 2));
  RegStringValue = v17;
  if ( v17 < 0 )
  {
    v18 = 647;
    goto LABEL_31;
  }
  v30 = 0;
  p_hKey = (__int64 *)&v30;
  lpsz = 0;
  v33 = 1;
  RegStringValue = StringFromCLSID(&CLSID_DeviceNgcProvider, &lpsz);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
  if ( RegStringValue < 0 )
  {
    v20 = (unsigned int)RegStringValue;
    v21 = 651;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)v20,
      lpDatab);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
    goto LABEL_41;
  }
  v22 = WriteRegStringValue(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\UserTile",
          *((char **)this + 3),
          v30);
  RegStringValue = v22;
  if ( v22 < 0 )
  {
    v20 = (unsigned int)v22;
    v21 = 657;
    goto LABEL_40;
  }
  v23 = RegDeleteKeyValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{48B4E58D-2791-456C-9091-D524C6C706F2}",
          L"Disabled");
  if ( v23 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x297,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)v23,
      lpDatab);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v37);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18005ab00  push    rbp
0x18005ab02  push    rbx
0x18005ab03  push    rsi
0x18005ab04  push    rdi
0x18005ab05  push    r14
0x18005ab07  mov     rbp, rsp
0x18005ab0a  sub     rsp, 60h
0x18005ab0e  mov     r14, rcx
0x18005ab11  cmp     dword ptr [rdx+4], 1
0x18005ab15  ja      loc_18005AEC6
0x18005ab1b  jnz     short loc_18005AB28
0x18005ab1d  cmp     qword ptr [rdx+8], 0
0x18005ab22  jz      loc_18005AEC6
0x18005ab28  xor     edi, edi
0x18005ab2a  xor     esi, esi
0x18005ab2c  xor     ecx, ecx
0x18005ab2e  cmp     ecx, [rdx+4]
0x18005ab31  jnb     short loc_18005AB59
0x18005ab33  mov     eax, ecx
0x18005ab35  add     rax, rax
0x18005ab38  mov     rsi, [rdx+8]
0x18005ab3c  cmp     dword ptr [rsi+rax*8], 9
0x18005ab40  jnz     short loc_18005AB4F
0x18005ab42  mov     rdi, [rsi+rax*8+8]
0x18005ab47  mov     esi, [rsi+rax*8+4]
0x18005ab4b  inc     ecx
0x18005ab4d  jmp     short loc_18005AB2E
0x18005ab4f  mov     edx, 23Ch
0x18005ab54  jmp     loc_18005AECB
0x18005ab59  test    rdi, rdi
0x18005ab5c  jnz     short loc_18005AB6C
0x18005ab5e  test    esi, esi
0x18005ab60  jz      short loc_18005AB76
0x18005ab62  mov     edx, 243h
0x18005ab67  jmp     loc_18005AECB
0x18005ab6c  lea     eax, [rsi-1]
0x18005ab6f  cmp     eax, 0FFFh
0x18005ab74  ja      short loc_18005AB62
0x18005ab76  mov     [rbp+hKey], 0
0x18005ab7e  lea     rax, [rbp+hKey]
0x18005ab82  mov     [rbp+var_18], rax
0x18005ab86  mov     [rbp+lpsz], 0
0x18005ab8e  mov     [rbp+var_8], 1
0x18005ab92  lea     rdx, [rbp+lpsz]; unsigned __int16 *
0x18005ab96  mov     rcx, [r14+8]; lpSubKey
0x18005ab9a  call    ?OpenDeviceRegKey@DcaMgr@@YAJPEBGPEAPEAUHKEY__@@@Z; DcaMgr::OpenDeviceRegKey(ushort const *,HKEY__ * *)
0x18005ab9f  mov     ebx, eax
0x18005aba1  lea     rcx, [rbp+var_18]
0x18005aba5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18005abaa  test    ebx, ebx
0x18005abac  jns     short loc_18005ABBB
0x18005abae  mov     r9d, ebx
0x18005abb1  mov     edx, 246h
0x18005abb6  jmp     loc_18005ACAC
0x18005abbb  test    rdi, rdi
0x18005abbe  jz      loc_18005AC89
0x18005abc4  mov     [rbp+var_28], 0
0x18005abcc  mov     [rbp+arg_8], 0
0x18005abd3  lea     rax, [rbp+var_28]
0x18005abd7  mov     [rbp+var_18], rax
0x18005abdb  mov     [rbp+lpsz], 0
0x18005abe3  mov     [rbp+var_8], 1
0x18005abe7  lea     rax, [rbp+arg_8]
0x18005abeb  mov     [rsp+60h+lpData], rax; int
0x18005abf0  lea     r9, [rbp+lpsz]
0x18005abf4  mov     r8d, esi
0x18005abf7  mov     rdx, rdi
0x18005abfa  mov     cl, 1
0x18005abfc  call    DpapiProtectUnprotect
0x18005ac01  mov     ebx, eax
0x18005ac03  lea     rcx, [rbp+var_18]
0x18005ac07  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x18005ac0c  test    ebx, ebx
0x18005ac0e  jns     short loc_18005AC36
0x18005ac10  mov     rcx, [rbp+28h]; this
0x18005ac14  mov     r9d, ebx; char *
0x18005ac17  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18005ac1e  mov     edx, 252h; void *
0x18005ac23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ac28  lea     rcx, [rbp+var_28]
0x18005ac2c  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18005ac31  jmp     loc_18005AE68
0x18005ac36  mov     rdx, [rbp+var_28]
0x18005ac3a  mov     eax, [rbp+arg_8]
0x18005ac3d  mov     [rsp+60h+cbData], eax; cbData
0x18005ac41  mov     [rsp+60h+lpData], rdx; int
0x18005ac46  mov     r9d, 3; dwType
0x18005ac4c  xor     r8d, r8d; Reserved
0x18005ac4f  lea     rdx, aOpaqueblob; "OpaqueBlob"
0x18005ac56  mov     rcx, [rbp+hKey]; hKey
0x18005ac5a  call    cs:__imp_RegSetValueExW
0x18005ac60  test    eax, eax
0x18005ac62  jz      short loc_18005AC80
0x18005ac64  mov     rcx, [rbp+28h]; this
0x18005ac68  mov     r9d, eax; char *
0x18005ac6b  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18005ac72  mov     edx, 25Ah; void *
0x18005ac77  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005ac7c  mov     ebx, eax
0x18005ac7e  jmp     short loc_18005AC28
0x18005ac80  lea     rcx, [rbp+var_28]
0x18005ac84  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18005ac89  call    ?Instance@DeviceCredentialMgr@DcaMgr@@SAAEAV12@XZ; DcaMgr::DeviceCredentialMgr::Instance(void)
0x18005ac8e  mov     r8, [r14+8]
0x18005ac92  lea     rdx, [rbp+hKey]
0x18005ac96  mov     rcx, rax
0x18005ac99  call    ?ProvisionDevice@DeviceCredentialMgr@DcaMgr@@QEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; DcaMgr::DeviceCredentialMgr::ProvisionDevice(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *)
0x18005ac9e  mov     ebx, eax
0x18005aca0  test    eax, eax
0x18005aca2  jns     short loc_18005ACC1
0x18005aca4  mov     r9d, eax; char *
0x18005aca7  mov     edx, 25Fh; void *
0x18005acac  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18005acb3  mov     rcx, [rbp+28h]; this
0x18005acb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005acbc  jmp     loc_18005AE68
0x18005acc1  mov     [rbp+Data], 1
0x18005acc8  mov     r9d, 4; dwType
0x18005acce  mov     [rsp+60h+cbData], r9d; cbData
0x18005acd3  lea     rax, [rbp+Data]
0x18005acd7  mov     [rsp+60h+lpData], rax; int
0x18005acdc  xor     r8d, r8d; Reserved
0x18005acdf  lea     rdx, aState; "State"
0x18005ace6  mov     rcx, [rbp+hKey]; hKey
0x18005acea  call    cs:__imp_RegSetValueExW
0x18005acf0  test    eax, eax
0x18005acf2  jz      short loc_18005AD13
0x18005acf4  mov     rcx, [rbp+28h]; this
0x18005acf8  mov     r9d, eax; char *
0x18005acfb  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18005ad02  mov     edx, 268h; void *
0x18005ad07  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005ad0c  mov     ebx, eax
0x18005ad0e  jmp     loc_18005AE68
0x18005ad13  mov     rcx, [rbp+hKey]; hKey
0x18005ad17  call    cs:__imp_RegFlushKey
0x18005ad1d  mov     [rbp+arg_18], 0
0x18005ad25  lea     rax, [rbp+arg_18]
0x18005ad29  mov     [rbp+var_18], rax
0x18005ad2d  mov     [rbp+lpsz], 0
0x18005ad35  mov     [rbp+var_8], 1
0x18005ad39  lea     r9, [rbp+lpsz]
0x18005ad3d  lea     r8, aLastunlockdevi; "LastUnlockDeviceId"
0x18005ad44  lea     rsi, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005ad4b  mov     rdx, rsi; lpSubKey
0x18005ad4e  mov     rdi, 0FFFFFFFF80000002h
0x18005ad55  mov     rcx, rdi; hkey
0x18005ad58  call    ReadRegStringValue
0x18005ad5d  mov     ebx, eax
0x18005ad5f  lea     rcx, [rbp+var_18]
0x18005ad63  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005ad68  test    ebx, ebx
0x18005ad6a  jns     short loc_18005ADB7
0x18005ad6c  cmp     ebx, 80070002h
0x18005ad72  jnz     short loc_18005ADAD
0x18005ad74  mov     r9, [r14+8]; lpData
0x18005ad78  lea     r8, aLastunlockdevi; "LastUnlockDeviceId"
0x18005ad7f  mov     rdx, rsi; lpSubKey
0x18005ad82  mov     rcx, rdi; hKey
0x18005ad85  call    WriteRegStringValue
0x18005ad8a  mov     ebx, eax
0x18005ad8c  test    eax, eax
0x18005ad8e  jns     short loc_18005ADB7
0x18005ad90  mov     edx, 27Bh; void *
0x18005ad95  mov     r9d, eax; char *
0x18005ad98  mov     rcx, [rbp+28h]; this
0x18005ad9c  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18005ada3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ada8  jmp     loc_18005AE5E
0x18005adad  mov     r9d, ebx
0x18005adb0  mov     edx, 27Fh
0x18005adb5  jmp     short loc_18005AD98
0x18005adb7  mov     r9, [r14+10h]; lpData
0x18005adbb  lea     r8, ValueName; "LastProvisionedAppId"
0x18005adc2  mov     rdx, rsi; lpSubKey
0x18005adc5  mov     rcx, rdi; hKey
0x18005adc8  call    WriteRegStringValue
0x18005adcd  mov     ebx, eax
0x18005adcf  test    eax, eax
0x18005add1  jns     short loc_18005ADDA
0x18005add3  mov     edx, 287h
0x18005add8  jmp     short loc_18005AD95
0x18005adda  mov     [rbp+var_20], 0
0x18005ade2  lea     rax, [rbp+var_20]
0x18005ade6  mov     [rbp+var_18], rax
0x18005adea  mov     [rbp+lpsz], 0
0x18005adf2  mov     [rbp+var_8], 1
0x18005adf6  lea     rdx, [rbp+lpsz]; lplpsz
0x18005adfa  lea     rcx, CLSID_DeviceNgcProvider; rclsid
0x18005ae01  call    cs:__imp_StringFromCLSID
0x18005ae07  mov     ebx, eax
0x18005ae09  lea     rcx, [rbp+var_18]
0x18005ae0d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005ae12  test    ebx, ebx
0x18005ae14  jns     short loc_18005AE20
0x18005ae16  mov     r9d, ebx
0x18005ae19  mov     edx, 28Bh
0x18005ae1e  jmp     short loc_18005AE45
0x18005ae20  mov     r9, [rbp+var_20]; lpData
0x18005ae24  mov     r8, [r14+18h]; char *
0x18005ae28  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005ae2f  mov     rcx, rdi; hKey
0x18005ae32  call    WriteRegStringValue
0x18005ae37  mov     ebx, eax
0x18005ae39  test    eax, eax
0x18005ae3b  jns     short loc_18005AE73
0x18005ae3d  mov     r9d, eax; char *
0x18005ae40  mov     edx, 291h; void *
0x18005ae45  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18005ae4c  mov     rcx, [rbp+28h]; this
0x18005ae50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ae55  lea     rcx, [rbp+var_20]
0x18005ae59  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005ae5e  lea     rcx, [rbp+arg_18]; void *
0x18005ae62  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005ae67  nop
0x18005ae68  lea     rcx, [rbp+hKey]
0x18005ae6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005ae71  jmp     short loc_18005AEE3
0x18005ae73  lea     r8, aDisabled; "Disabled"
0x18005ae7a  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005ae81  mov     rcx, rdi; hKey
0x18005ae84  call    cs:__imp_RegDeleteKeyValueW
0x18005ae8a  mov     rcx, [rbp+28h]; this
0x18005ae8e  test    eax, eax
0x18005ae90  jns     short loc_18005AEA6
0x18005ae92  mov     r9d, eax; char *
0x18005ae95  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18005ae9c  mov     edx, 297h; void *
0x18005aea1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005aea6  lea     rcx, [rbp+var_20]
0x18005aeaa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005aeaf  lea     rcx, [rbp+arg_18]; void *
0x18005aeb3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005aeb8  nop
0x18005aeb9  lea     rcx, [rbp+hKey]
0x18005aebd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005aec2  xor     eax, eax
0x18005aec4  jmp     short loc_18005AEE5
0x18005aec6  mov     edx, 22Dh; void *
0x18005aecb  mov     ebx, 80070057h
0x18005aed0  mov     r9d, ebx; char *
0x18005aed3  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18005aeda  mov     rcx, [rbp+28h]; this
0x18005aede  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aee3  mov     eax, ebx
0x18005aee5  add     rsp, 60h
0x18005aee9  pop     r14
0x18005aeeb  pop     rdi
0x18005aeec  pop     rsi
0x18005aeed  pop     rbx
0x18005aeee  pop     rbp
0x18005aeef  retn
```
