# CreateBrowserProcess

- ea: `0x180085578`
- end: `0x18008587d`
- name: `CreateBrowserProcess`
- size: `773`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180085364`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180011328`
- `0x1800263e4`
- `0x180038c70`
- `0x180044408`
- `0x18004670c`
- `0x18005ae90`
- `0x18005ba40`
- `0x180084d84`
- `0x180084fa8`
- `0x180085578`
- `0x180086404`
- `0x1800868f0`
- `0x180086ab8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008581b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008581b`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18008560a`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18008560a`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x1800857c3`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x1800857c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateBrowserProcess(__int64 a1, __int64 a2, DWORD *a3)
{
  int v4; // esi
  unsigned __int16 *v6; // r9
  const char *v7; // r9
  __int64 result; // rax
  HRESULT v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  const WCHAR *v14; // rax
  int v15; // eax
  unsigned int v16; // ebx
  const char *v17; // r9
  unsigned int LastError; // ebx
  unsigned int v19; // [rsp+20h] [rbp-2F8h]
  int v20; // [rsp+20h] [rbp-2F8h]
  struct BrowserChannels::Info *v21; // [rsp+28h] [rbp-2F0h]
  __int64 v22; // [rsp+30h] [rbp-2E8h] BYREF
  const WCHAR *v23; // [rsp+38h] [rbp-2E0h] BYREF
  _QWORD v24[2]; // [rsp+40h] [rbp-2D8h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+50h] [rbp-2C8h] BYREF
  _QWORD v26[4]; // [rsp+C0h] [rbp-258h] BYREF
  WCHAR pszPath[264]; // [rsp+E0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  try
  {
    v4 = a2;
    LOBYTE(a2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserReplacement>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_BrowserReplacement>::GetImpl'::`2'::impl,
      a2,
      0);
    pszPath[0] = 0;
    if ( BrowserChannels::Private::GetInstalledInfo(
           (BrowserChannels::Private *)0xFFFFFFFF80000002LL,
           (HKEY)&stru_1800B2DC0,
           pszPath,
           v6,
           v19,
           v21) )
    {
      std::wstring::wstring(v26);
      v9 = PathCchRemoveFileSpec(pszPath, 0x104u);
      v11 = v9;
      if ( v9 >= 0 )
      {
        LOBYTE(v10) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Allow_SwitchToDesktop_25561487>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_Servicing_Allow_SwitchToDesktop_25561487>::GetImpl'::`2'::impl,
          v10);
        v23 = 0;
        v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v23,
                L"%s=%s %s",
                L"--edge-redirect",
                a1);
        v13 = v12;
        if ( v12 >= 0 )
        {
          memset_0(&pExecInfo, 0, sizeof(pExecInfo));
          pExecInfo.cbSize = 112;
          pExecInfo.fMask = 134219072;
          pExecInfo.nShow = 5;
          pExecInfo.lpParameters = v23;
          pExecInfo.lpDirectory = pszPath;
          v14 = (const WCHAR *)v26;
          if ( v26[3] > 7u )
            v14 = (const WCHAR *)v26[0];
          pExecInfo.lpFile = v14;
          v22 = 0;
          LODWORD(v24[0]) = 2;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
          v15 = Microsoft::WRL::Details::MakeAndInitialize<CLauncherUIMode,CLauncherUIMode,enum EC_HOST_UI_MODE>(
                  &v22,
                  v24);
          v16 = v15;
          if ( v15 >= 0 )
          {
            *(_DWORD *)(v22 + 180) = 32;
            pExecInfo.hInstApp = (HINSTANCE)((v22 + 40) & -(__int64)(v22 != 0));
            if ( ShellExecuteExW(&pExecInfo) )
            {
              v24[0] = pExecInfo.hProcess;
              *a3 = GetProcessId(pExecInfo.hProcess);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v24);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
              std::wstring::_Tidy_deallocate(v26);
              result = 0;
            }
            else
            {
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0x9B,
                            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\browseractiv"
                                          "ationmanager.cpp",
                            v17);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
              std::wstring::_Tidy_deallocate(v26);
              result = LastError;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x92,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\browseractivationmanager.cpp",
              (const char *)(unsigned int)v15,
              v4);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
            std::wstring::_Tidy_deallocate(v26);
            result = v16;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x88,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\browseractivationmanager.cpp",
            (const char *)(unsigned int)v12,
            v4);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
          std::wstring::_Tidy_deallocate(v26);
          result = v13;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x83,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\browseractivationmanager.cpp",
          (const char *)(unsigned int)v9,
          v20);
        std::wstring::_Tidy_deallocate(v26);
        result = v11;
      }
    }
    else
    {
      result = 2147942402LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xBC,
                           (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\browseractivationmanager.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x180085578  mov     [rsp+arg_18], rbx
0x18008557d  push    rsi
0x18008557e  push    rdi
0x18008557f  push    r14
0x180085581  sub     rsp, 300h
0x180085588  mov     rax, cs:__security_cookie
0x18008558f  xor     rax, rsp
0x180085592  mov     [rsp+318h+var_28], rax
0x18008559a  mov     r14, r8
0x18008559d  mov     rsi, rdx
0x1800855a0  mov     rdi, rcx
0x1800855a3  xor     r8d, r8d
0x1800855a6  mov     dl, 1
0x1800855a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BrowserReplacement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserReplacement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserReplacement> `wil::Feature<__WilFeatureTraits_Feature_BrowserReplacement>::GetImpl(void)'::`2'::impl
0x1800855af  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserReplacement@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserReplacement>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800855b4  xor     eax, eax
0x1800855b6  mov     [rsp+318h+pszPath], ax
0x1800855be  lea     r8, [rsp+318h+pszPath]; unsigned __int16 *
0x1800855c6  lea     rdx, stru_1800B2DC0; HKEY
0x1800855cd  mov     rcx, 0FFFFFFFF80000002h; this
0x1800855d4  call    ?GetInstalledInfo@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAG1KPEAUInfo@2@@Z; BrowserChannels::Private::GetInstalledInfo(HKEY__ *,ushort *,ushort *,ulong,BrowserChannels::Info *)
0x1800855d9  test    al, al
0x1800855db  jnz     short loc_1800855E7
0x1800855dd  mov     eax, 80070002h
0x1800855e2  jmp     loc_180085858
0x1800855e7  lea     rdx, [rsp+318h+pszPath]
0x1800855ef  lea     rcx, [rsp+318h+var_258]
0x1800855f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800855fc  nop
0x1800855fd  mov     edx, 104h; cchPath
0x180085602  lea     rcx, [rsp+318h+pszPath]; pszPath
0x18008560a  call    cs:__imp_PathCchRemoveFileSpec
0x180085610  mov     ebx, eax
0x180085612  test    eax, eax
0x180085614  jns     short loc_180085647
0x180085616  mov     rcx, [rsp+318h]; this
0x18008561e  mov     r9d, eax; char *
0x180085621  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180085628  mov     edx, 83h; void *
0x18008562d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085632  nop
0x180085633  lea     rcx, [rsp+318h+var_258]
0x18008563b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085640  mov     eax, ebx
0x180085642  jmp     loc_180085858
0x180085647  mov     dl, 1
0x180085649  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_Allow_SwitchToDesktop_25561487@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Allow_SwitchToDesktop_25561487@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Allow_SwitchToDesktop_25561487> `wil::Feature<__WilFeatureTraits_Feature_Servicing_Allow_SwitchToDesktop_25561487>::GetImpl(void)'::`2'::impl
0x180085650  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Allow_SwitchToDesktop_25561487@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Allow_SwitchToDesktop_25561487>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180085655  mov     [rsp+318h+var_2E0], 0
0x18008565e  mov     qword ptr [rsp+318h+var_2F8], rsi; int
0x180085663  mov     r9, rdi
0x180085666  lea     r8, aEdgeRedirect; "--edge-redirect"
0x18008566d  lea     rdx, aSSS; "%s=%s %s"
0x180085674  lea     rcx, [rsp+318h+var_2E0]
0x180085679  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18008567e  mov     ebx, eax
0x180085680  test    eax, eax
0x180085682  jns     short loc_1800856BF
0x180085684  mov     rcx, [rsp+318h]; this
0x18008568c  mov     r9d, eax; char *
0x18008568f  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180085696  mov     edx, 88h; void *
0x18008569b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800856a0  lea     rcx, [rsp+318h+var_2E0]
0x1800856a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800856aa  nop
0x1800856ab  lea     rcx, [rsp+318h+var_258]
0x1800856b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800856b8  mov     eax, ebx
0x1800856ba  jmp     loc_180085858
0x1800856bf  mov     ebx, 70h ; 'p'
0x1800856c4  mov     r8d, ebx; Size
0x1800856c7  xor     edx, edx; Val
0x1800856c9  lea     rcx, [rsp+318h+pExecInfo]; void *
0x1800856ce  call    memset_0
0x1800856d3  mov     [rsp+318h+pExecInfo.cbSize], ebx
0x1800856d7  mov     [rsp+318h+pExecInfo.fMask], 8000540h
0x1800856df  mov     [rsp+318h+pExecInfo.nShow], 5
0x1800856ea  mov     rax, [rsp+318h+var_2E0]
0x1800856ef  mov     [rsp+318h+pExecInfo.lpParameters], rax
0x1800856f4  lea     rax, [rsp+318h+pszPath]
0x1800856fc  mov     [rsp+318h+pExecInfo.lpDirectory], rax
0x180085701  lea     rax, [rsp+318h+var_258]
0x180085709  cmp     [rsp+318h+var_240], 7
0x180085712  cmova   rax, [rsp+318h+var_258]
0x18008571b  mov     [rsp+318h+pExecInfo.lpFile], rax
0x180085720  mov     [rsp+318h+var_2E8], 0
0x180085729  mov     dword ptr [rsp+318h+var_2D8], 2
0x180085731  lea     rcx, [rsp+318h+var_2E8]
0x180085736  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008573b  lea     rdx, [rsp+318h+var_2D8]
0x180085740  lea     rcx, [rsp+318h+var_2E8]
0x180085745  call    ??$MakeAndInitialize@VCLauncherUIMode@@V1@W4EC_HOST_UI_MODE@@@Details@WRL@Microsoft@@YAJPEAPEAVCLauncherUIMode@@$$QEAW4EC_HOST_UI_MODE@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CLauncherUIMode,CLauncherUIMode,EC_HOST_UI_MODE>(CLauncherUIMode * *,EC_HOST_UI_MODE &&)
0x18008574a  mov     ebx, eax
0x18008574c  test    eax, eax
0x18008574e  jns     short loc_180085795
0x180085750  mov     rcx, [rsp+318h]; this
0x180085758  mov     r9d, eax; char *
0x18008575b  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180085762  mov     edx, 92h; void *
0x180085767  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008576c  lea     rcx, [rsp+318h+var_2E8]
0x180085771  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085776  lea     rcx, [rsp+318h+var_2E0]
0x18008577b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180085780  nop
0x180085781  lea     rcx, [rsp+318h+var_258]
0x180085789  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008578e  mov     eax, ebx
0x180085790  jmp     loc_180085858
0x180085795  mov     rax, [rsp+318h+var_2E8]
0x18008579a  mov     dword ptr [rax+0B4h], 20h ; ' '
0x1800857a4  mov     rax, [rsp+318h+var_2E8]
0x1800857a9  lea     rcx, [rax+28h]
0x1800857ad  neg     rax
0x1800857b0  sbb     rax, rax
0x1800857b3  and     rax, rcx
0x1800857b6  mov     [rsp+318h+pExecInfo.hInstApp], rax
0x1800857be  lea     rcx, [rsp+318h+pExecInfo]; pExecInfo
0x1800857c3  call    cs:__imp_ShellExecuteExW
0x1800857c9  test    eax, eax
0x1800857cb  jnz     short loc_18008580E
0x1800857cd  mov     rcx, [rsp+318h]; this
0x1800857d5  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800857dc  mov     edx, 9Bh; void *
0x1800857e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800857e6  mov     ebx, eax
0x1800857e8  lea     rcx, [rsp+318h+var_2E8]
0x1800857ed  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800857f2  lea     rcx, [rsp+318h+var_2E0]
0x1800857f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800857fc  nop
0x1800857fd  lea     rcx, [rsp+318h+var_258]
0x180085805  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008580a  mov     eax, ebx
0x18008580c  jmp     short loc_180085858
0x18008580e  mov     rcx, [rsp+318h+pExecInfo.hProcess]; Process
0x180085816  mov     [rsp+318h+var_2D8], rcx
0x18008581b  call    cs:__imp_GetProcessId
0x180085821  mov     [r14], eax
0x180085824  lea     rcx, [rsp+318h+var_2D8]
0x180085829  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008582e  lea     rcx, [rsp+318h+var_2E8]
0x180085833  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085838  lea     rcx, [rsp+318h+var_2E0]
0x18008583d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180085842  nop
0x180085843  lea     rcx, [rsp+318h+var_258]
0x18008584b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085850  xor     eax, eax
0x180085852  jmp     short loc_180085858
0x180085854  mov     eax, dword ptr [rsp+318h+var_2D8]
0x180085858  mov     rcx, [rsp+318h+var_28]
0x180085860  xor     rcx, rsp; StackCookie
0x180085863  call    __security_check_cookie
0x180085868  mov     rbx, [rsp+318h+arg_18]
0x180085870  add     rsp, 300h
0x180085877  pop     r14
0x180085879  pop     rdi
0x18008587a  pop     rsi
0x18008587b  retn
```
