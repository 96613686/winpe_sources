# SystemSettings::RadialControllerSettings::EnumAppWindowProc(HWND__ *,__int64)

- ea: `0x180214670`
- end: `0x180214b29`
- name: `?EnumAppWindowProc@RadialControllerSettings@SystemSettings@@YAHPEAUHWND__@@_J@Z`
- size: `1209`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x180011bb0`
- `0x1800234c4`
- `0x1800234f8`
- `0x18002395c`
- `0x18002e1a4`
- `0x18003eaec`
- `0x180045e0c`
- `0x18005a028`
- `0x180066808`
- `0x18006956c`
- `0x180086824`
- `0x1801f8950`
- `0x18020883c`
- `0x18020c104`
- `0x180214670`
- `0x180215180`
- `0x18026f2c8`
- `0x180270e94`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180214a07`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180214a07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180214756`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180214756`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180214989`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180214989`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180214821`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180214821`
- `USER32!GetWindowThreadProcessId` at `0x180214801`
- `USER32!GetWindowThreadProcessId` at `0x180214801`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1802148ab`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1802148ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::RadialControllerSettings::EnumAppWindowProc(CallerIdentity *a1, HWND a2)
{
  HWND v4; // rdx
  unsigned __int16 **v5; // r8
  unsigned int ImmersiveAppIdFromWindow; // eax
  __int64 v7; // rdx
  HRESULT Instance; // eax
  LPVOID v9; // r15
  __int64 (__fastcall *v10)(LPVOID, CallerIdentity *, __int64, _QWORD); // rbx
  __int64 v11; // rax
  int v12; // eax
  HANDLE v13; // rax
  const char *v14; // r9
  void *v15; // rbx
  _QWORD *v16; // r15
  const WCHAR *v17; // rdi
  __int64 v18; // r8
  WCHAR *v19; // rbx
  int StringOrdinal; // eax
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rax
  _QWORD *v25; // rax
  int ppv; // [rsp+20h] [rbp-2F8h]
  int ppva; // [rsp+20h] [rbp-2F8h]
  PCWSTR pszItem; // [rsp+40h] [rbp-2D8h] BYREF
  DWORD dwProcessId; // [rsp+48h] [rbp-2D0h] BYREF
  void *v31[2]; // [rsp+50h] [rbp-2C8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-2B8h] BYREF
  HANDLE v33; // [rsp+68h] [rbp-2B0h] BYREF
  __int128 v34; // [rsp+70h] [rbp-2A8h] BYREF
  __m128i si128; // [rsp+80h] [rbp-298h]
  _OWORD v36[2]; // [rsp+90h] [rbp-288h] BYREF
  _OWORD v37[2]; // [rsp+B0h] [rbp-268h] BYREF
  DWORD v38; // [rsp+D0h] [rbp-248h]
  char v39; // [rsp+D4h] [rbp-244h]
  __int16 v40; // [rsp+D5h] [rbp-243h]
  char v41; // [rsp+D7h] [rbp-241h]
  WCHAR Filename[264]; // [rsp+E0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  pszItem = 0;
  if ( !a2 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\applicationhelpers.cpp",
      (const char *)0x8000FFFFLL,
      ppv);
  if ( SystemSettings::RadialControllerSettings::ShouldIncludeDesktopWindow((HWND)a1, a2) && a2 )
  {
    v4 = (HWND)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszItem);
    ImmersiveAppIdFromWindow = CallerIdentity::GetImmersiveAppIdFromWindow(a1, v4, v5);
    v7 = 0x80000000LL;
    if ( (int)(ImmersiveAppIdFromWindow + 0x80000000) >= 0 && ImmersiveAppIdFromWindow != -2147023728 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\applicationhelpers.cpp",
        (const char *)ImmersiveAppIdFromWindow,
        ppv);
    if ( !pszItem )
    {
      if ( !*(_QWORD *)a2 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a2);
        Instance = CoCreateInstance(
                     &CLSID_StartMenuCacheAndAppResolver,
                     0,
                     3u,
                     &GUID_de25675a_72de_44b4_9373_05170450c140,
                     (LPVOID *)a2);
        if ( Instance < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x70,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\applicationhelpers.cpp",
            (const char *)(unsigned int)Instance,
            ppva);
      }
      v9 = *(LPVOID *)a2;
      if ( *(_QWORD *)a2 )
      {
        v10 = *(__int64 (__fastcall **)(LPVOID, CallerIdentity *, __int64, _QWORD))(*(_QWORD *)v9 + 40LL);
        v11 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszItem);
        v12 = v10(v9, a1, v11, 0);
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x75,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\applicationhelpers.cpp",
            (const char *)(unsigned int)v12,
            0);
      }
    }
    dwProcessId = 0;
    if ( pszItem
      && !SystemSettings::PenSettings::IsBlockedAumid(
            (SystemSettings::PenSettings *)pszItem,
            (const unsigned __int16 *)v7)
      && GetWindowThreadProcessId((HWND)a1, &dwProcessId) )
    {
      v13 = OpenProcess(0x1000u, 0, dwProcessId);
      v15 = v13;
      v33 = v13;
      if ( v13 == (HANDLE)-1LL )
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x7F,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\applicationhelpers.cpp",
          v14);
      }
      else if ( v13 )
      {
        v32 = 0;
        v16 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v32);
        v17 = pszItem;
        *v16 = 0;
        v31[0] = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
        if ( SHCreateItemInKnownFolder(
               &FOLDERID_AppsFolder,
               0x4100u,
               v17,
               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
               v31) >= 0 )
          (*(void (__fastcall **)(void *, _QWORD, _QWORD *))(*(_QWORD *)v31[0] + 40LL))(v31[0], 0, v16);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
        v34 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v34) = 0;
        v36[0] = 0;
        v36[1] = si128;
        LOWORD(v36[0]) = 0;
        v37[0] = 0;
        v37[1] = si128;
        LOWORD(v37[0]) = 0;
        v39 = 0;
        v40 = 0;
        v41 = 0;
        v38 = dwProcessId;
        try
        {
          std::wstring::assign(&v34, pszItem);
          memset_0(Filename, 0, 0x208u);
          if ( K32GetModuleFileNameExW(v15, 0, Filename, 0x103u) )
          {
            std::wstring::assign(v36, Filename);
            v18 = -1;
            do
              ++v18;
            while ( Filename[v18] );
            v19 = &Filename[v18];
            if ( v18 && *(v19 - 1) == 92 )
              LODWORD(v18) = v18 - 1;
            StringOrdinal = FindStringOrdinal(0x800000u, Filename, v18, L"\\", 1, 1);
            if ( StringOrdinal != -1 )
              v19 = &Filename[StringOrdinal + 1];
            std::wstring::assign(v37, v19);
          }
          std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::pair<std::wstring,std::wstring>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::pair<std::wstring,std::wstring>>>>,0>>::find(
            *((_QWORD *)a2 + 1),
            v31,
            &v34);
          if ( v31[0] == **((void ***)a2 + 1) )
          {
            v23 = v32;
            if ( v32 )
              std::wstring::assign(v37, v32);
            v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v37, v23, v21, v22);
            InputDial::InputDialTraceProvider::Info(
              "shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\applicationhelpers.cpp",
              "na",
              0xA0u,
              "EnumAppWindowProc: aumid=%ws, friendlyName=%ws",
              pszItem,
              v24);
            v25 = (_QWORD *)std::map<std::wstring,SystemSettings::RadialControllerSettings::RadialControllerAppListInfo>::_Try_emplace<std::wstring const &,>(
                              *((_QWORD *)a2 + 1),
                              v31,
                              &v34);
            SystemSettings::RadialControllerSettings::RadialControllerAppListInfo::operator=(*v25 + 64LL, &v34);
          }
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0xA5,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\applicationhelpers.cpp",
            v22);
        }
        wil::cloud_store::validated_data_reference::~validated_data_reference((wil::cloud_store::validated_data_reference *)&v34);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v32);
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszItem);
  return 1;
}

```

## disassembly

```asm
0x180214670  mov     [rsp+arg_10], rbx
0x180214675  mov     [rsp+arg_18], rsi
0x18021467a  push    rdi
0x18021467b  push    r12
0x18021467d  push    r15
0x18021467f  sub     rsp, 300h
0x180214686  mov     rax, cs:__security_cookie
0x18021468d  xor     rax, rsp
0x180214690  mov     [rsp+318h+var_28], rax
0x180214698  mov     rsi, rdx
0x18021469b  mov     rdi, rcx
0x18021469e  xor     r12d, r12d
0x1802146a1  mov     [rsp+318h+pszItem], r12
0x1802146a6  mov     rcx, [rsp+318h]; this
0x1802146ae  test    rdx, rdx
0x1802146b1  jnz     short loc_1802146C8
0x1802146b3  mov     r9d, 8000FFFFh; char *
0x1802146b9  lea     r8, aShellSystemset_20; "shell\\systemsettingsthreshold\\handler"...
0x1802146c0  lea     edx, [rsi+5Eh]; void *
0x1802146c3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802146c8  mov     rcx, rdi; hWnd
0x1802146cb  call    ?ShouldIncludeDesktopWindow@RadialControllerSettings@SystemSettings@@YA_NQEAUHWND__@@@Z; SystemSettings::RadialControllerSettings::ShouldIncludeDesktopWindow(HWND__ * const)
0x1802146d0  test    al, al
0x1802146d2  jz      loc_180214AF0
0x1802146d8  test    rsi, rsi
0x1802146db  jz      loc_180214AF0
0x1802146e1  lea     rcx, [rsp+318h+pszItem]
0x1802146e6  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1802146eb  mov     rdx, rax; HWND
0x1802146ee  mov     rcx, rdi; this
0x1802146f1  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x1802146f6  mov     edx, 80000000h
0x1802146fb  lea     ecx, [rax+rdx]
0x1802146fe  test    edx, ecx
0x180214700  jnz     short loc_180214725
0x180214702  cmp     eax, 80070490h
0x180214707  jz      short loc_180214725
0x180214709  mov     rcx, [rsp+318h]; this
0x180214711  mov     r9d, eax; char *
0x180214714  lea     r8, aShellSystemset_20; "shell\\systemsettingsthreshold\\handler"...
0x18021471b  mov     edx, 69h ; 'i'; void *
0x180214720  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180214725  cmp     [rsp+318h+pszItem], r12
0x18021472a  jnz     loc_1802147D9
0x180214730  cmp     [rsi], r12
0x180214733  jnz     short loc_180214782
0x180214735  mov     rcx, rsi
0x180214738  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021473d  mov     [rsp+318h+ppv], rsi; int
0x180214742  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x180214749  xor     edx, edx; pUnkOuter
0x18021474b  lea     r8d, [rdx+3]; dwClsContext
0x18021474f  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x180214756  call    cs:__imp_CoCreateInstance
0x18021475d  nop     dword ptr [rax+rax+00h]
0x180214762  mov     rcx, [rsp+318h]; this
0x18021476a  test    eax, eax
0x18021476c  jns     short loc_180214782
0x18021476e  mov     r9d, eax; char *
0x180214771  lea     r8, aShellSystemset_20; "shell\\systemsettingsthreshold\\handler"...
0x180214778  mov     edx, 70h ; 'p'; void *
0x18021477d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180214782  mov     r15, [rsi]
0x180214785  test    r15, r15
0x180214788  jz      short loc_1802147D9
0x18021478a  mov     rax, [r15]
0x18021478d  mov     rbx, [rax+28h]
0x180214791  lea     rcx, [rsp+318h+pszItem]
0x180214796  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18021479b  mov     qword ptr [rsp+318h+bIgnoreCase], r12
0x1802147a0  mov     [rsp+318h+ppv], r12; int
0x1802147a5  xor     r9d, r9d
0x1802147a8  mov     r8, rax
0x1802147ab  mov     rdx, rdi
0x1802147ae  mov     rcx, r15
0x1802147b1  mov     rax, rbx
0x1802147b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802147b9  mov     rcx, [rsp+318h]; this
0x1802147c1  test    eax, eax
0x1802147c3  jns     short loc_1802147D9
0x1802147c5  mov     r9d, eax; char *
0x1802147c8  lea     r8, aShellSystemset_20; "shell\\systemsettingsthreshold\\handler"...
0x1802147cf  mov     edx, 75h ; 'u'; void *
0x1802147d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802147d9  mov     [rsp+318h+dwProcessId], r12d
0x1802147de  mov     rcx, [rsp+318h+pszItem]; this
0x1802147e3  test    rcx, rcx
0x1802147e6  jz      loc_180214AF0
0x1802147ec  call    ?IsBlockedAumid@PenSettings@SystemSettings@@YA_NPEBG@Z; SystemSettings::PenSettings::IsBlockedAumid(ushort const *)
0x1802147f1  test    al, al
0x1802147f3  jnz     loc_180214AF0
0x1802147f9  lea     rdx, [rsp+318h+dwProcessId]; lpdwProcessId
0x1802147fe  mov     rcx, rdi; hWnd
0x180214801  call    cs:__imp_GetWindowThreadProcessId
0x180214808  nop     dword ptr [rax+rax+00h]
0x18021480d  test    eax, eax
0x18021480f  jz      loc_180214AF0
0x180214815  mov     r8d, [rsp+318h+dwProcessId]; dwProcessId
0x18021481a  xor     edx, edx; bInheritHandle
0x18021481c  mov     ecx, 1000h; dwDesiredAccess
0x180214821  call    cs:__imp_OpenProcess
0x180214828  nop     dword ptr [rax+rax+00h]
0x18021482d  mov     rbx, rax
0x180214830  mov     [rsp+318h+var_2B0], rax
0x180214835  mov     rcx, [rsp+318h]; this
0x18021483d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180214841  jnz     short loc_180214859
0x180214843  lea     r8, aShellSystemset_20; "shell\\systemsettingsthreshold\\handler"...
0x18021484a  mov     edx, 7Fh; void *
0x18021484f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180214854  jmp     loc_180214AE5
0x180214859  test    rbx, rbx
0x18021485c  jz      loc_180214AE5
0x180214862  mov     [rsp+318h+var_2B8], r12
0x180214867  lea     rcx, [rsp+318h+var_2B8]
0x18021486c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180214871  mov     r15, rax
0x180214874  mov     rdi, [rsp+318h+pszItem]
0x180214879  mov     [rax], r12
0x18021487c  mov     [rsp+318h+var_2C8], r12
0x180214881  lea     rcx, [rsp+318h+var_2C8]
0x180214886  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021488b  lea     rax, [rsp+318h+var_2C8]
0x180214890  mov     [rsp+318h+ppv], rax; ppv
0x180214895  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18021489c  mov     r8, rdi; pszItem
0x18021489f  mov     edx, 4100h; dwKFFlags
0x1802148a4  lea     rcx, FOLDERID_AppsFolder; kfid
0x1802148ab  call    cs:__imp_SHCreateItemInKnownFolder
0x1802148b2  nop     dword ptr [rax+rax+00h]
0x1802148b7  test    eax, eax
0x1802148b9  js      short loc_1802148D1
0x1802148bb  mov     rcx, [rsp+318h+var_2C8]
0x1802148c0  mov     rax, [rcx]
0x1802148c3  mov     r8, r15
0x1802148c6  xor     edx, edx
0x1802148c8  mov     rax, [rax+28h]
0x1802148cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802148d1  lea     rcx, [rsp+318h+var_2C8]
0x1802148d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802148db  xorps   xmm0, xmm0
0x1802148de  movups  [rsp+318h+var_2A8], xmm0
0x1802148e3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1802148eb  movdqa  [rsp+318h+var_298], xmm1
0x1802148f4  mov     word ptr [rsp+318h+var_2A8], r12w
0x1802148fa  movups  [rsp+318h+var_288], xmm0
0x180214902  movdqa  [rsp+318h+var_278], xmm1
0x18021490b  mov     word ptr [rsp+318h+var_288], r12w
0x180214914  movups  [rsp+318h+var_268], xmm0
0x18021491c  movdqa  [rsp+318h+var_258], xmm1
0x180214925  mov     word ptr [rsp+318h+var_268], r12w
0x18021492e  mov     [rsp+318h+var_244], r12b
0x180214936  xor     eax, eax
0x180214938  mov     [rsp+318h+var_243], ax
0x180214940  mov     [rsp+318h+var_241], al
0x180214947  mov     eax, [rsp+318h+dwProcessId]
0x18021494b  mov     [rsp+318h+var_248], eax
0x180214952  mov     rdx, [rsp+318h+pszItem]
0x180214957  lea     rcx, [rsp+318h+var_2A8]
0x18021495c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180214961  xor     edx, edx; Val
0x180214963  mov     r8d, 208h; Size
0x180214969  lea     rcx, [rsp+318h+Filename]; void *
0x180214971  call    memset_0
0x180214976  mov     r9d, 103h; nSize
0x18021497c  lea     r8, [rsp+318h+Filename]; lpFilename
0x180214984  xor     edx, edx; hModule
0x180214986  mov     rcx, rbx; hProcess
0x180214989  call    cs:__imp_K32GetModuleFileNameExW
0x180214990  nop     dword ptr [rax+rax+00h]
0x180214995  test    eax, eax
0x180214997  jz      loc_180214A36
0x18021499d  lea     rdx, [rsp+318h+Filename]
0x1802149a5  lea     rcx, [rsp+318h+var_288]
0x1802149ad  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1802149b2  lea     rax, [rsp+318h+Filename]
0x1802149ba  or      r8, 0FFFFFFFFFFFFFFFFh
0x1802149be  inc     r8
0x1802149c1  cmp     [rax+r8*2], r12w
0x1802149c6  jnz     short loc_1802149BE
0x1802149c8  lea     rbx, [rsp+318h+Filename]
0x1802149d0  lea     rbx, [rbx+r8*2]
0x1802149d4  test    r8, r8
0x1802149d7  jz      short loc_1802149E3
0x1802149d9  cmp     word ptr [rbx-2], 5Ch ; '\'
0x1802149de  jnz     short loc_1802149E3
0x1802149e0  dec     r8; cchSource
0x1802149e3  mov     [rsp+318h+bIgnoreCase], 1; bIgnoreCase
0x1802149eb  mov     dword ptr [rsp+318h+ppv], 1; cchValue
0x1802149f3  lea     r9, Control; "\\"
0x1802149fa  lea     rdx, [rsp+318h+Filename]; lpStringSource
0x180214a02  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180214a07  call    cs:__imp_FindStringOrdinal
0x180214a0e  nop     dword ptr [rax+rax+00h]
0x180214a13  cmp     eax, 0FFFFFFFFh
0x180214a16  jz      short loc_180214A26
0x180214a18  cdqe
0x180214a1a  lea     rbx, [rsp+318h+var_236]
0x180214a22  lea     rbx, [rbx+rax*2]
0x180214a26  mov     rdx, rbx
0x180214a29  lea     rcx, [rsp+318h+var_268]
0x180214a31  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180214a36  lea     r8, [rsp+318h+var_2A8]
0x180214a3b  lea     rdx, [rsp+318h+var_2C8]
0x180214a40  mov     rcx, [rsi+8]
0x180214a44  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::pair<std::wstring,std::wstring>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::pair<std::wstring,std::wstring>>>>,0>>::find(std::wstring const &)
0x180214a49  mov     rax, [rsi+8]
0x180214a4d  mov     rcx, [rax]
0x180214a50  cmp     [rsp+318h+var_2C8], rcx
0x180214a55  jnz     short loc_180214ACF
0x180214a57  mov     rdx, [rsp+318h+var_2B8]
0x180214a5c  test    rdx, rdx
0x180214a5f  jz      short loc_180214A6E
0x180214a61  lea     rcx, [rsp+318h+var_268]
0x180214a69  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180214a6e  lea     rcx, [rsp+318h+var_268]
0x180214a76  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180214a7b  mov     qword ptr [rsp+318h+bIgnoreCase], rax
0x180214a80  mov     rax, [rsp+318h+pszItem]
0x180214a85  mov     [rsp+318h+ppv], rax
0x180214a8a  lea     r9, aEnumappwindowp; "EnumAppWindowProc: aumid=%ws, friendlyN"...
0x180214a91  mov     r8d, 0A0h; unsigned int
0x180214a97  lea     rdx, aNa; "na"
0x180214a9e  lea     rcx, aShellSystemset_20; "shell\\systemsettingsthreshold\\handler"...
0x180214aa5  call    ?Info@InputDialTraceProvider@InputDial@@SAXPEBD0I0ZZ; InputDial::InputDialTraceProvider::Info(char const *,char const *,uint,char const *,...)
0x180214aaa  lea     r8, [rsp+318h+var_2A8]
0x180214aaf  lea     rdx, [rsp+318h+var_2C8]
0x180214ab4  mov     rcx, [rsi+8]
0x180214ab8  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadialControllerAppListInfo@RadialControllerSettings@SystemSettings@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadialControllerAppListInfo@RadialControllerSettings@SystemSettings@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadialControllerAppListInfo@RadialControllerSettings@SystemSettings@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,SystemSettings::RadialControllerSettings::RadialControllerAppListInfo>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180214abd  mov     rcx, [rax]
0x180214ac0  add     rcx, 40h ; '@'
0x180214ac4  lea     rdx, [rsp+318h+var_2A8]
0x180214ac9  call    ??4RadialControllerAppListInfo@RadialControllerSettings@SystemSettings@@QEAAAEAU012@$$QEAU012@@Z; SystemSettings::RadialControllerSettings::RadialControllerAppListInfo::operator=(SystemSettings::RadialControllerSettings::RadialControllerAppListInfo &&)
0x180214ace  nop
0x180214acf  lea     rcx, [rsp+318h+var_2A8]; this
0x180214ad4  call    ??1validated_data_reference@cloud_store@wil@@QEAA@XZ; wil::cloud_store::validated_data_reference::~validated_data_reference(void)
0x180214ad9  nop
0x180214ada  lea     rcx, [rsp+318h+var_2B8]
0x180214adf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180214ae4  nop
0x180214ae5  lea     rcx, [rsp+318h+var_2B0]
0x180214aea  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180214aef  nop
0x180214af0  lea     rcx, [rsp+318h+pszItem]
0x180214af5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180214afa  mov     eax, 1
0x180214aff  mov     rcx, [rsp+318h+var_28]
0x180214b07  xor     rcx, rsp; StackCookie
0x180214b0a  call    __security_check_cookie
0x180214b0f  lea     r11, [rsp+318h+var_18]
0x180214b17  mov     rbx, [r11+30h]
0x180214b1b  mov     rsi, [r11+38h]
0x180214b1f  mov     rsp, r11
0x180214b22  pop     r15
0x180214b24  pop     r12
0x180214b26  pop     rdi
0x180214b27  retn
```
