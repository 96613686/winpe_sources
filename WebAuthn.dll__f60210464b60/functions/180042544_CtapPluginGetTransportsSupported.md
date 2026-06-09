# CtapPluginGetTransportsSupported

- ea: `0x180042544`
- end: `0x180042734`
- name: `CtapPluginGetTransportsSupported`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a3568`

## callees

- `0x18001687c`
- `0x180036da4`
- `0x180042154`
- `0x180042544`
- `0x180042e40`
- `0x18004349c`
- `0x18010ee78`
- `0x18011c42c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800426b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800426f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800426b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800426f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800425cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800425cb`

## string_xrefs

- `0x180042579`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1800425ee`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18004268d`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CtapPluginGetTransportsSupported(__int64 a1, const WCHAR *a2, _DWORD *a3)
{
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  HKEY *v8; // rax
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 v12; // rcx
  int CtapCborAuthenticatorInfoFromRegistry; // ebx
  HLOCAL v14; // rcx
  HLOCAL v15; // rcx
  int v16; // eax
  int phkResult; // [rsp+20h] [rbp-58h]
  int phkResulta; // [rsp+20h] [rbp-58h]
  HLOCAL hMem; // [rsp+30h] [rbp-48h] BYREF
  __int128 v20; // [rsp+38h] [rbp-40h] BYREF
  __int128 v21; // [rsp+48h] [rbp-30h] BYREF
  HLOCAL *p_hMem; // [rsp+58h] [rbp-20h] BYREF
  __int64 v23; // [rsp+60h] [rbp-18h] BYREF
  char v24; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, (__int64)&hKey);
  v6 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey >= 0 )
  {
    v21 = 0;
    try
    {
      v8 = (HKEY *)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::put(&v21);
      v9 = RegOpenKeyExW(hKey, a2, 0, 0xF003Fu, v8);
      v10 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v10 = (unsigned __int16)v9 | 0x80070000;
        if ( (v10 & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD00,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)v10,
            phkResulta);
        std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v21);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        result = v10;
      }
      else
      {
        hMem = 0;
        p_hMem = &hMem;
        v23 = 0;
        v24 = 1;
        v20 = 0;
        v12 = *((_QWORD *)&v21 + 1);
        if ( *((_QWORD *)&v21 + 1) )
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL));
        *(_QWORD *)&v20 = v21;
        *((_QWORD *)&v20 + 1) = v12;
        CtapCborAuthenticatorInfoFromRegistry = GetCtapCborAuthenticatorInfoFromRegistry(&v20, &v23);
        wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
        if ( CtapCborAuthenticatorInfoFromRegistry >= 0 )
        {
          v15 = hMem;
          v16 = *((_DWORD *)hMem + 26);
          *a3 = v16;
          if ( !v16 )
            *a3 = 16;
          hMem = 0;
          if ( v15 )
            LocalFree(v15);
          std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v21);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD04,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)CtapCborAuthenticatorInfoFromRegistry,
            phkResulta);
          v14 = hMem;
          hMem = 0;
          if ( v14 )
            LocalFree(v14);
          std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v21);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          result = (unsigned int)CtapCborAuthenticatorInfoFromRegistry;
        }
      }
    }
    catch ( ... )
    {
      LODWORD(hKey) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0xD0E,
                        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                        v11);
      return (unsigned int)hKey;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCFA,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180042544  mov     rax, rsp
0x180042547  mov     [rax+8], rbx
0x18004254b  mov     [rax+10h], rsi
0x18004254f  push    rdi
0x180042550  sub     rsp, 70h
0x180042554  mov     rdi, r8
0x180042557  mov     rsi, rdx
0x18004255a  mov     qword ptr [rax+20h], 0
0x180042562  lea     rdx, [rax+20h]
0x180042566  call    GetUserPluginAuthenticatorsRegKey
0x18004256b  mov     ebx, eax
0x18004256d  test    eax, eax
0x18004256f  jns     short loc_18004259F
0x180042571  mov     rcx, [rsp+78h]; this
0x180042576  mov     r9d, eax; char *
0x180042579  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180042580  mov     edx, 0CFAh; void *
0x180042585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004258a  nop
0x18004258b  lea     rcx, [rsp+78h+hKey]
0x180042593  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042598  mov     eax, ebx
0x18004259a  jmp     loc_180042721
0x18004259f  xorps   xmm0, xmm0
0x1800425a2  movdqu  [rsp+78h+var_30], xmm0
0x1800425a8  lea     rcx, [rsp+78h+var_30]
0x1800425ad  call    ?put@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::put(void)
0x1800425b2  mov     qword ptr [rsp+78h+phkResult], rax; int
0x1800425b7  mov     r9d, 0F003Fh; samDesired
0x1800425bd  xor     r8d, r8d; ulOptions
0x1800425c0  mov     rdx, rsi; lpSubKey
0x1800425c3  mov     rcx, [rsp+78h+hKey]; hKey
0x1800425cb  call    cs:__imp_RegOpenKeyExW
0x1800425d1  mov     ebx, eax
0x1800425d3  test    eax, eax
0x1800425d5  jz      short loc_18004261F
0x1800425d7  jle     short loc_1800425E2
0x1800425d9  movzx   ebx, ax
0x1800425dc  or      ebx, 80070000h
0x1800425e2  test    ebx, ebx
0x1800425e4  jns     short loc_180042600
0x1800425e6  mov     rcx, [rsp+78h]; this
0x1800425eb  mov     r9d, ebx; char *
0x1800425ee  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800425f5  mov     edx, 0D00h; void *
0x1800425fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800425ff  nop
0x180042600  lea     rcx, [rsp+78h+var_30]
0x180042605  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18004260a  nop
0x18004260b  lea     rcx, [rsp+78h+hKey]
0x180042613  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042618  mov     eax, ebx
0x18004261a  jmp     loc_180042721
0x18004261f  mov     [rsp+78h+hMem], 0
0x180042628  lea     rax, [rsp+78h+hMem]
0x18004262d  mov     [rsp+78h+var_20], rax
0x180042632  mov     [rsp+78h+var_18], 0
0x18004263b  mov     [rsp+78h+var_10], 1
0x180042640  xorps   xmm0, xmm0
0x180042643  movdqu  [rsp+78h+var_40], xmm0
0x180042649  mov     rcx, qword ptr [rsp+78h+var_30+8]
0x18004264e  test    rcx, rcx
0x180042651  jz      short loc_180042657
0x180042653  lock inc dword ptr [rcx+8]
0x180042657  mov     rax, qword ptr [rsp+78h+var_30]
0x18004265c  mov     qword ptr [rsp+78h+var_40], rax
0x180042661  mov     qword ptr [rsp+78h+var_40+8], rcx
0x180042666  lea     rdx, [rsp+78h+var_18]
0x18004266b  lea     rcx, [rsp+78h+var_40]
0x180042670  call    ?GetCtapCborAuthenticatorInfoFromRegistry@@YAJV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAPEAU_CTAPCBOR_AUTHENTICATOR_INFO@@@Z; GetCtapCborAuthenticatorInfoFromRegistry(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>,_CTAPCBOR_AUTHENTICATOR_INFO * *)
0x180042675  mov     ebx, eax
0x180042677  lea     rcx, [rsp+78h+var_20]
0x18004267c  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180042681  test    ebx, ebx
0x180042683  jns     short loc_1800426D5
0x180042685  mov     rcx, [rsp+78h]; this
0x18004268a  mov     r9d, ebx; char *
0x18004268d  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180042694  mov     edx, 0D04h; void *
0x180042699  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004269e  nop
0x18004269f  mov     rcx, [rsp+78h+hMem]; hMem
0x1800426a4  mov     [rsp+78h+hMem], 0
0x1800426ad  test    rcx, rcx
0x1800426b0  jz      short loc_1800426B9
0x1800426b2  call    cs:__imp_LocalFree
0x1800426b8  nop
0x1800426b9  lea     rcx, [rsp+78h+var_30]
0x1800426be  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x1800426c3  nop
0x1800426c4  lea     rcx, [rsp+78h+hKey]
0x1800426cc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800426d1  mov     eax, ebx
0x1800426d3  jmp     short loc_180042721
0x1800426d5  mov     rcx, [rsp+78h+hMem]; hMem
0x1800426da  mov     eax, [rcx+68h]
0x1800426dd  mov     [rdi], eax
0x1800426df  test    eax, eax
0x1800426e1  jnz     short loc_1800426E9
0x1800426e3  mov     dword ptr [rdi], 10h
0x1800426e9  mov     [rsp+78h+hMem], 0
0x1800426f2  test    rcx, rcx
0x1800426f5  jz      short loc_1800426FE
0x1800426f7  call    cs:__imp_LocalFree
0x1800426fd  nop
0x1800426fe  lea     rcx, [rsp+78h+var_30]
0x180042703  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x180042708  nop
0x180042709  lea     rcx, [rsp+78h+hKey]
0x180042711  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042716  xor     eax, eax
0x180042718  jmp     short loc_180042721
0x18004271a  mov     eax, dword ptr [rsp+78h+hKey]
0x180042721  lea     r11, [rsp+78h+var_8]
0x180042726  mov     rbx, [r11+10h]
0x18004272a  mov     rsi, [r11+18h]
0x18004272e  mov     rsp, r11
0x180042731  pop     rdi
0x180042732  retn
```
