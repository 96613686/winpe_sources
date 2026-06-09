# PluginEnumerator::EnumeratePlugins(__MIDL___MIDL_itf_provisioningplugineng_0000_0000_0005,std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>,std::allocator<Microsoft::WRL::ComPtr<IProvisioningPlugin>>> *)

- ea: `0x1800282e0`
- end: `0x18002861c`
- name: `?EnumeratePlugins@PluginEnumerator@@UEAAJW4__MIDL___MIDL_itf_provisioningplugineng_0000_0000_0005@@PEAV?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@@Z`
- size: `828`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800034e0`
- `0x180004394`
- `0x180004a90`
- `0x1800067fc`
- `0x1800087ec`
- `0x180010920`
- `0x18001c7b8`
- `0x180024d94`
- `0x180027dd4`
- `0x180028208`
- `0x1800282e0`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800283e0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002843c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002848a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028597`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800285ce`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800283e0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002843c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002848a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028597`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800285ce`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180028426`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180028426`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028370`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028370`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028330`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028330`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028509`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028509`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800284c6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800284c6`

## string_xrefs

- `0x180028362`: `SOFTWARE\Microsoft\Provisioning\Plugin\Providers`
- `0x18002838b`: `onecoreuap\admin\prov\plugineng\core\pluginenumerator.cpp`
- `0x180028474`: `onecoreuap\admin\prov\plugineng\core\pluginenumerator.cpp`
- `0x1800285ba`: `onecoreuap\admin\prov\plugineng\core\pluginenumerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PluginEnumerator::EnumeratePlugins(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  DWORD i; // edi
  BYTE *lpData; // rbx
  unsigned int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rax
  LPVOID v14; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-298h]
  HKEY hKey; // [rsp+40h] [rbp-278h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-270h] BYREF
  DWORD cchValueName; // [rsp+50h] [rbp-268h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-264h] BYREF
  __int64 v20; // [rsp+58h] [rbp-260h] BYREF
  _QWORD v21[2]; // [rsp+60h] [rbp-258h] BYREF
  CLSID pclsid; // [rsp+70h] [rbp-248h] BYREF
  WCHAR ValueName[264]; // [rsp+80h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::clear(a3);
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Provisioning\\Plugin\\Providers", 0, 0x20019u, &hKey);
  try
  {
    if ( v5 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x27,
             (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\pluginenumerator.cpp",
             (const char *)v5,
             phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      result = v6;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        cchValueName = 261;
        cbData = 78;
        lpData = (BYTE *)operator new[](0x4Eu, (const struct std::nothrow_t *)std::nothrow);
        if ( !lpData )
          break;
        operator delete[](0);
        v21[1] = lpData;
        v11 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, lpData, &cbData);
        if ( v11 == 259 )
        {
          operator delete[](lpData);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return 0;
        }
        if ( v11 != 234 )
        {
          if ( v11 )
          {
            v12 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x4C,
                    (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\pluginenumerator.cpp",
                    (const char *)v11,
                    phkResult);
            operator delete[](lpData);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            return v12;
          }
          *(_WORD *)&lpData[2 * ((unsigned __int64)cbData >> 1) - 2] = 0;
          pclsid = 0;
          if ( CLSIDFromString((LPCOLESTR)lpData, &pclsid) >= 0 )
          {
            ppv = 0;
            Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&ppv);
            if ( CoCreateInstance(&pclsid, 0, 0x17u, &GUID_f3bef5d5_b02a_43b5_9316_94aed0171a72, &ppv) >= 0
              && (*(int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, a2) >= 0 )
            {
              v20 = 0;
              v13 = *(_QWORD *)ppv;
              v20 = 0;
              if ( (*(int (__fastcall **)(LPVOID, __int64 *))(v13 + 24))(ppv, &v20) >= 0 )
              {
                v14 = ppv;
                ppv = 0;
                v21[0] = v14;
                std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::emplace_back<IProvisioningPlugin *>(a3, v21);
              }
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
            }
            Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&ppv);
          }
        }
        operator delete[](lpData);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\pluginenumerator.cpp",
        (const char *)0x8007000ELL,
        phkResult);
      operator delete[](0);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    cchValueName = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x78,
                     (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\pluginenumerator.cpp",
                     v7);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return cchValueName;
  }
  return result;
}

```

## disassembly

```asm
0x1800282e0  mov     [rsp+arg_0], rbx
0x1800282e5  push    rsi
0x1800282e6  push    rdi
0x1800282e7  push    r14
0x1800282e9  sub     rsp, 2A0h
0x1800282f0  mov     rax, cs:__security_cookie
0x1800282f7  xor     rax, rsp
0x1800282fa  mov     [rsp+2B8h+var_28], rax
0x180028302  mov     rsi, r8
0x180028305  mov     r14d, edx
0x180028308  mov     [rsp+2B8h+hKey], 0
0x180028311  mov     rcx, r8
0x180028314  call    ?clear@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@QEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::clear(void)
0x180028319  mov     rbx, [rsp+2B8h+hKey]
0x18002831e  test    rbx, rbx
0x180028321  jz      short loc_180028346
0x180028323  lea     rcx, [rsp+2B8h+var_260]; this
0x180028328  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002832d  mov     rcx, rbx; hKey
0x180028330  call    cs:__imp_RegCloseKey
0x180028337  nop     dword ptr [rax+rax+00h]
0x18002833c  lea     rcx, [rsp+2B8h+var_260]; this
0x180028341  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180028346  mov     [rsp+2B8h+hKey], 0
0x18002834f  lea     rax, [rsp+2B8h+hKey]
0x180028354  mov     [rsp+2B8h+phkResult], rax; int
0x180028359  mov     r9d, 20019h; samDesired
0x18002835f  xor     r8d, r8d; ulOptions
0x180028362  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Provisioning\\Plug"...
0x180028369  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028370  call    cs:__imp_RegOpenKeyExW
0x180028377  nop     dword ptr [rax+rax+00h]
0x18002837c  test    eax, eax
0x18002837e  jz      short loc_1800283AF
0x180028380  mov     rcx, [rsp+2B8h]; this
0x180028388  mov     r9d, eax; char *
0x18002838b  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180028392  mov     edx, 27h ; '''; void *
0x180028397  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002839c  mov     ebx, eax
0x18002839e  lea     rcx, [rsp+2B8h+hKey]
0x1800283a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800283a8  mov     eax, ebx
0x1800283aa  jmp     loc_1800285F7
0x1800283af  xor     edi, edi
0x1800283b1  mov     [rsp+2B8h+cchValueName], 105h
0x1800283b9  mov     [rsp+2B8h+cbData], 4Eh ; 'N'
0x1800283c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800283c8  mov     ecx, 4Eh ; 'N'; unsigned __int64
0x1800283cd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800283d2  mov     rbx, rax
0x1800283d5  test    rax, rax
0x1800283d8  jz      loc_1800285AA
0x1800283de  xor     ecx, ecx
0x1800283e0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800283e7  nop     dword ptr [rax+rax+00h]
0x1800283ec  mov     [rsp+2B8h+var_250], rbx
0x1800283f1  lea     rax, [rsp+2B8h+cbData]
0x1800283f6  mov     [rsp+2B8h+lpcbData], rax; lpcbData
0x1800283fb  mov     [rsp+2B8h+lpData], rbx; lpData
0x180028400  mov     [rsp+2B8h+lpType], 0; lpType
0x180028409  mov     [rsp+2B8h+phkResult], 0; unsigned int
0x180028412  lea     r9, [rsp+2B8h+cchValueName]; lpcchValueName
0x180028417  lea     r8, [rsp+2B8h+ValueName]; lpValueName
0x18002841f  mov     edx, edi; dwIndex
0x180028421  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180028426  call    cs:__imp_RegEnumValueW
0x18002842d  nop     dword ptr [rax+rax+00h]
0x180028432  cmp     eax, 103h
0x180028437  jnz     short loc_18002845A
0x180028439  mov     rcx, rbx
0x18002843c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028443  nop     dword ptr [rax+rax+00h]
0x180028448  nop
0x180028449  lea     rcx, [rsp+2B8h+hKey]
0x18002844e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028453  xor     eax, eax
0x180028455  jmp     loc_1800285F7
0x18002845a  cmp     eax, 0EAh
0x18002845f  jz      loc_180028594
0x180028465  test    eax, eax
0x180028467  jz      short loc_1800284A8
0x180028469  mov     rcx, [rsp+2B8h]; this
0x180028471  mov     r9d, eax; char *
0x180028474  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002847b  mov     edx, 4Ch ; 'L'; void *
0x180028480  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028485  mov     edi, eax
0x180028487  mov     rcx, rbx
0x18002848a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028491  nop     dword ptr [rax+rax+00h]
0x180028496  nop
0x180028497  lea     rcx, [rsp+2B8h+hKey]
0x18002849c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800284a1  mov     eax, edi
0x1800284a3  jmp     loc_1800285F7
0x1800284a8  mov     ecx, [rsp+2B8h+cbData]
0x1800284ac  shr     rcx, 1
0x1800284af  xor     eax, eax
0x1800284b1  mov     [rbx+rcx*2-2], ax
0x1800284b6  xorps   xmm0, xmm0
0x1800284b9  movups  xmmword ptr [rsp+2B8h+pclsid.Data1], xmm0
0x1800284be  lea     rdx, [rsp+2B8h+pclsid]; pclsid
0x1800284c3  mov     rcx, rbx; lpsz
0x1800284c6  call    cs:__imp_CLSIDFromString
0x1800284cd  nop     dword ptr [rax+rax+00h]
0x1800284d2  test    eax, eax
0x1800284d4  js      loc_180028594
0x1800284da  mov     [rsp+2B8h+ppv], 0
0x1800284e3  lea     rcx, [rsp+2B8h+ppv]
0x1800284e8  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800284ed  lea     rax, [rsp+2B8h+ppv]
0x1800284f2  mov     [rsp+2B8h+phkResult], rax; ppv
0x1800284f7  lea     r9, _GUID_f3bef5d5_b02a_43b5_9316_94aed0171a72; riid
0x1800284fe  xor     edx, edx; pUnkOuter
0x180028500  lea     r8d, [rdx+17h]; dwClsContext
0x180028504  lea     rcx, [rsp+2B8h+pclsid]; rclsid
0x180028509  call    cs:__imp_CoCreateInstance
0x180028510  nop     dword ptr [rax+rax+00h]
0x180028515  test    eax, eax
0x180028517  js      short loc_180028589
0x180028519  mov     rcx, [rsp+2B8h+ppv]
0x18002851e  mov     rax, [rcx]
0x180028521  mov     edx, r14d
0x180028524  mov     rax, [rax+38h]
0x180028528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002852d  test    eax, eax
0x18002852f  js      short loc_180028589
0x180028531  mov     [rsp+2B8h+var_260], 0
0x18002853a  mov     rcx, [rsp+2B8h+ppv]
0x18002853f  mov     rax, [rcx]
0x180028542  mov     [rsp+2B8h+var_260], 0
0x18002854b  lea     rdx, [rsp+2B8h+var_260]
0x180028550  mov     rax, [rax+18h]
0x180028554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028559  test    eax, eax
0x18002855b  js      short loc_18002857E
0x18002855d  mov     rax, [rsp+2B8h+ppv]
0x180028562  mov     [rsp+2B8h+ppv], 0
0x18002856b  mov     [rsp+2B8h+var_258], rax
0x180028570  lea     rdx, [rsp+2B8h+var_258]
0x180028575  mov     rcx, rsi
0x180028578  call    ??$emplace_back@PEAUIProvisioningPlugin@@@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@QEAAX$$QEAPEAUIProvisioningPlugin@@@Z; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::emplace_back<IProvisioningPlugin *>(IProvisioningPlugin * &&)
0x18002857d  nop
0x18002857e  lea     rcx, [rsp+2B8h+var_260]
0x180028583  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028588  nop
0x180028589  lea     rcx, [rsp+2B8h+ppv]
0x18002858e  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180028593  nop
0x180028594  mov     rcx, rbx
0x180028597  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002859e  nop     dword ptr [rax+rax+00h]
0x1800285a3  inc     edi
0x1800285a5  jmp     loc_1800283B1
0x1800285aa  mov     rcx, [rsp+2B8h]; this
0x1800285b2  mov     ebx, 8007000Eh
0x1800285b7  mov     r9d, ebx; char *
0x1800285ba  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800285c1  mov     edx, 31h ; '1'; void *
0x1800285c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800285cb  nop
0x1800285cc  xor     ecx, ecx
0x1800285ce  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800285d5  nop     dword ptr [rax+rax+00h]
0x1800285da  nop
0x1800285db  lea     rcx, [rsp+2B8h+hKey]
0x1800285e0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800285e5  mov     eax, ebx
0x1800285e7  jmp     short loc_1800285F7
0x1800285e9  lea     rcx, [rsp+2B8h+hKey]
0x1800285ee  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800285f3  mov     eax, [rsp+2B8h+cchValueName]
0x1800285f7  mov     rcx, [rsp+2B8h+var_28]
0x1800285ff  xor     rcx, rsp; StackCookie
0x180028602  call    __security_check_cookie
0x180028607  mov     rbx, [rsp+2B8h+arg_0]
0x18002860f  add     rsp, 2A0h
0x180028616  pop     r14
0x180028618  pop     rdi
0x180028619  pop     rsi
0x18002861a  retn
```
