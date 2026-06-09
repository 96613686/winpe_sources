# DiagnosticsElevatedManagerImpl::EnableDevicePortalInOobe(void)

- ea: `0x180023d60`
- end: `0x180023eda`
- name: `?EnableDevicePortalInOobe@DiagnosticsElevatedManagerImpl@@UEAAJXZ`
- size: `378`
- prototype: `__int64 __fastcall(DiagnosticsElevatedManagerImpl *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180015310`
- `0x1800153f8`
- `0x1800227ac`
- `0x18002353c`
- `0x180023d60`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023e3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023e97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023e3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023e97`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023e02`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023e02`
- `Wldp!__imp_?WldpQueryPolicySettingEnabledInternal@@YAJW4WLDP_POLICY_SETTING_INTERNAL@@PEAH@Z` at `0x180023d7c`
- `Wldp!__imp_?WldpQueryPolicySettingEnabledInternal@@YAJW4WLDP_POLICY_SETTING_INTERNAL@@PEAH@Z` at `0x180023d7c`
- `Wldp!__imp_WldpEnableDeveloperMode` at `0x180023db1`
- `Wldp!__imp_WldpEnableDeveloperMode` at `0x180023db1`
- `api-ms-win-appmodel-unlock-l1-1-0!SetIsDeveloperModeEnabled` at `0x180023de0`
- `api-ms-win-appmodel-unlock-l1-1-0!SetIsDeveloperModeEnabled` at `0x180023de0`

## string_xrefs

- `0x180023d8e`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`
- `0x180023dc2`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`
- `0x180023e1a`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`
- `0x180023e55`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`
- `0x180023e78`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\diagnosticoperations.cpp`
- `0x180023dfb`: `debugregsvcapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall DiagnosticsElevatedManagerImpl::EnableDevicePortalInOobe(DiagnosticsElevatedManagerImpl *this)
{
  int v1; // eax
  int IsDeveloperModeEnabled; // ebx
  __int64 v4; // rdx
  HMODULE Library; // rax
  const char *v6; // r9
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  int v12; // edi
  FARPROC v13; // rax
  int v14; // eax
  int v15; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v17; // [rsp+38h] [rbp+10h] BYREF
  HMODULE v18; // [rsp+40h] [rbp+18h] BYREF

  v17 = 0;
  v1 = WldpQueryPolicySettingEnabledInternal(4, &v17);
  if ( v1 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
      (const char *)(unsigned int)v1,
      v15);
    return 0;
  }
  if ( !v17 )
    return 0;
  IsDeveloperModeEnabled = WldpEnableDeveloperMode(0);
  if ( IsDeveloperModeEnabled >= 0 )
  {
    IsDeveloperModeEnabled = SetIsDeveloperModeEnabled(1);
    if ( IsDeveloperModeEnabled < 0 )
    {
      v4 = 106;
      goto LABEL_7;
    }
    Library = LoadLibraryExW(L"debugregsvcapi.dll", 0, 0x800u);
    v7 = Library;
    v18 = Library;
    if ( !Library )
    {
      IsDeveloperModeEnabled = wil::details::in1diag3::Return_GetLastError(
                                 retaddr,
                                 (void *)0x6D,
                                 (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
                                 v6);
LABEL_23:
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v18);
      return (unsigned int)IsDeveloperModeEnabled;
    }
    ProcAddress = GetProcAddress(Library, "SetDevicePortalAuthenticationState");
    if ( ProcAddress )
    {
      v11 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
          (const char *)(unsigned int)v11,
          v15);
        IsDeveloperModeEnabled = v12;
        goto LABEL_23;
      }
      v13 = GetProcAddress(v7, "SetWebManagementState");
      if ( v13 )
      {
        v14 = ((__int64 (__fastcall *)(__int64))v13)(1);
        IsDeveloperModeEnabled = v14;
        if ( v14 >= 0 )
        {
          IsDeveloperModeEnabled = 0;
          goto LABEL_23;
        }
        v10 = (unsigned int)v14;
        v9 = 119;
        goto LABEL_15;
      }
      v9 = 118;
    }
    else
    {
      v9 = 113;
    }
    IsDeveloperModeEnabled = -2147418113;
    v10 = 2147549183LL;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
      (const char *)v10,
      v15);
    goto LABEL_23;
  }
  v4 = 105;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\diagnosticoperations.cpp",
    (const char *)(unsigned int)IsDeveloperModeEnabled,
    v15);
  return (unsigned int)IsDeveloperModeEnabled;
}

```

## disassembly

```asm
0x180023d60  mov     [rsp+arg_0], rbx
0x180023d65  push    rdi; int
0x180023d66  sub     rsp, 20h
0x180023d6a  mov     [rsp+28h+arg_8], 0
0x180023d72  lea     rdx, [rsp+28h+arg_8]
0x180023d77  mov     ecx, 4
0x180023d7c  call    cs:__imp_?WldpQueryPolicySettingEnabledInternal@@YAJW4WLDP_POLICY_SETTING_INTERNAL@@PEAH@Z
0x180023d82  mov     rcx, [rsp+28h]; this
0x180023d87  test    eax, eax
0x180023d89  jns     short loc_180023DA1
0x180023d8b  mov     r9d, eax; char *
0x180023d8e  lea     r8, aOnecoreuapShel_16
0x180023d95  mov     edx, 66h ; 'f'; void *
0x180023d9a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180023d9f  jmp     short loc_180023DA8
0x180023da1  cmp     [rsp+28h+arg_8], 0
0x180023da6  jnz     short loc_180023DAF
0x180023da8  xor     eax, eax
0x180023daa  jmp     loc_180023ECF
0x180023daf  xor     ecx, ecx
0x180023db1  call    cs:__imp_WldpEnableDeveloperMode
0x180023db7  mov     ebx, eax
0x180023db9  test    eax, eax
0x180023dbb  jns     short loc_180023DDB
0x180023dbd  mov     edx, 69h ; 'i'; void *
0x180023dc2  lea     r8, aOnecoreuapShel_16
0x180023dc9  mov     r9d, ebx; char *
0x180023dcc  mov     rcx, [rsp+28h]; this
0x180023dd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180023dd6  jmp     loc_180023ECD
0x180023ddb  mov     ecx, 1
0x180023de0  call    cs:__imp_SetIsDeveloperModeEnabled
0x180023de6  mov     ebx, eax
0x180023de8  test    eax, eax
0x180023dea  jns     short loc_180023DF3
0x180023dec  mov     edx, 6Ah ; 'j'
0x180023df1  jmp     short loc_180023DC2
0x180023df3  xor     edx, edx; hFile
0x180023df5  mov     r8d, 800h; dwFlags
0x180023dfb  lea     rcx, LibFileName
0x180023e02  call    cs:__imp_LoadLibraryExW
0x180023e08  mov     rbx, rax
0x180023e0b  mov     [rsp+28h+arg_10], rax
0x180023e10  test    rax, rax
0x180023e13  jnz     short loc_180023E30
0x180023e15  mov     rcx, [rsp+28h]; this
0x180023e1a  lea     r8, aOnecoreuapShel_16
0x180023e21  lea     edx, [rax+6Dh]; void *
0x180023e24  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z
0x180023e29  mov     ebx, eax
0x180023e2b  jmp     loc_180023EC3
0x180023e30  lea     rdx, aSetdeviceporta
0x180023e37  mov     rcx, rbx; hModule
0x180023e3a  call    cs:__imp_GetProcAddress
0x180023e40  test    rax, rax
0x180023e43  jnz     short loc_180023E63
0x180023e45  lea     edx, [rax+71h]; void *
0x180023e48  mov     ebx, 8000FFFFh
0x180023e4d  mov     r9d, ebx; char *
0x180023e50  mov     rcx, [rsp+28h]; this
0x180023e55  lea     r8, aOnecoreuapShel_16
0x180023e5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180023e61  jmp     short loc_180023EC3
0x180023e63  xor     ecx, ecx
0x180023e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e6a  mov     edi, eax
0x180023e6c  test    eax, eax
0x180023e6e  jns     short loc_180023E8D
0x180023e70  mov     rcx, [rsp+28h]; this
0x180023e75  mov     r9d, eax; char *
0x180023e78  lea     r8, aOnecoreuapShel_16
0x180023e7f  mov     edx, 72h ; 'r'; void *
0x180023e84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180023e89  mov     ebx, edi
0x180023e8b  jmp     short loc_180023EC3
0x180023e8d  lea     rdx, aSetwebmanageme
0x180023e94  mov     rcx, rbx; hModule
0x180023e97  call    cs:__imp_GetProcAddress
0x180023e9d  test    rax, rax
0x180023ea0  jnz     short loc_180023EA7
0x180023ea2  lea     edx, [rax+76h]
0x180023ea5  jmp     short loc_180023E48
0x180023ea7  mov     ecx, 1
0x180023eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eb1  mov     ebx, eax
0x180023eb3  test    eax, eax
0x180023eb5  jns     short loc_180023EC1
0x180023eb7  mov     r9d, eax
0x180023eba  mov     edx, 77h ; 'w'
0x180023ebf  jmp     short loc_180023E50
0x180023ec1  xor     ebx, ebx
0x180023ec3  lea     rcx, [rsp+28h+arg_10]
0x180023ec8  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023ecd  mov     eax, ebx
0x180023ecf  mov     rbx, [rsp+28h+arg_0]
0x180023ed4  add     rsp, 20h
0x180023ed8  pop     rdi
0x180023ed9  retn
```
