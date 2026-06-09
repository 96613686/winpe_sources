# SystemSettings::StartupHandlers::StartupAppListItemSetting::GetShortcutIconPath(ushort const * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1800d8c6c`
- end: `0x1800d8e4c`
- name: `?GetShortcutIconPath@StartupAppListItemSetting@StartupHandlers@SystemSettings@@AEAAJQEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d80a0`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18000e6cc`
- `0x180018244`
- `0x18004f990`
- `0x1800d7bc8`
- `0x1800d7e04`
- `0x1800d8c6c`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8e16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8e16`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x1800d8d2d`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x1800d8d2d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFileInfoW` at `0x1800d8da7`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFileInfoW` at `0x1800d8da7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StartupHandlers::StartupAppListItemSetting::GetShortcutIconPath(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rax
  HRESULT v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  unsigned __int64 v8; // r9
  void *v9; // rcx
  bool v10; // zf
  __int64 v11; // rax
  int v12; // eax
  void *v13; // rcx
  UINT uFlags; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  IUnknown *punk; // [rsp+38h] [rbp-C8h] BYREF
  void *p_punk; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  char v20; // [rsp+50h] [rbp-B0h]
  SHFILEINFOW psfi; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  punk = 0;
  v4 = *(_QWORD *)SystemSettings::StartupHandlers::StartupAppListItemSetting::m_appResolver;
  p_punk = &punk;
  ppidl = 0;
  v20 = 1;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, LPITEMIDLIST *, _QWORD))(v4 + 72))(
         SystemSettings::StartupHandlers::StartupAppListItemSetting::m_appResolver,
         a2,
         &ppidl,
         0);
  wil::details::out_param_t<wil::com_ptr_t<IShellItem,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IShellItem,wil::err_exception_policy>>(&p_punk);
  if ( v5 < 0 )
  {
    v6 = 55;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startupapplistitemsetting.cpp",
      (const char *)(unsigned int)v5,
      uFlags);
    goto LABEL_23;
  }
  if ( !punk )
  {
    v5 = -2147024894;
    v6 = 56;
    goto LABEL_5;
  }
  pv = 0;
  p_punk = &pv;
  ppidl = 0;
  v20 = 1;
  v5 = SHGetIDListFromObject(punk, &ppidl);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_punk);
  if ( v5 < 0 )
  {
    v7 = 58;
LABEL_8:
    v8 = (unsigned int)v5;
    goto LABEL_9;
  }
  memset_0(&psfi, 0, sizeof(psfi));
  if ( !SHGetFileInfoW((LPCWSTR)pv, 0, &psfi, 0x2B8u, 0x1008u) )
  {
    v7 = 60;
LABEL_17:
    v5 = -2147024894;
    goto LABEL_8;
  }
  v11 = -1;
  do
    ++v11;
  while ( psfi.szDisplayName[v11] );
  if ( !v11 )
  {
    v7 = 61;
    goto LABEL_17;
  }
  v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          a3,
          L"%s,%d",
          psfi.szDisplayName,
          (unsigned int)psfi.iIcon);
  v5 = v12;
  if ( v12 < 0 )
  {
    v8 = (unsigned int)v12;
    v7 = 62;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startupapplistitemsetting.cpp",
      (const char *)v8,
      uFlags);
    v9 = pv;
    v10 = pv == 0;
    pv = 0;
    if ( !v10 )
      CoTaskMemFree(v9);
    goto LABEL_23;
  }
  v13 = pv;
  pv = 0;
  if ( v13 )
    CoTaskMemFree(v13);
  v5 = 0;
LABEL_23:
  wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&punk);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800d8c6c  mov     [rsp-8+arg_0], rbx
0x1800d8c71  push    rbp
0x1800d8c72  push    rsi
0x1800d8c73  push    rdi
0x1800d8c74  lea     rbp, [rsp-230h]
0x1800d8c7c  sub     rsp, 330h
0x1800d8c83  mov     rax, cs:__security_cookie
0x1800d8c8a  xor     rax, rsp
0x1800d8c8d  mov     [rbp+240h+var_20], rax
0x1800d8c94  mov     rdi, r8
0x1800d8c97  xor     esi, esi
0x1800d8c99  mov     [rsp+340h+punk], rsi
0x1800d8c9e  mov     rcx, cs:?m_appResolver@StartupAppListItemSetting@StartupHandlers@SystemSettings@@0V?$com_ptr_t@UIApplicationResolver@@Uerr_exception_policy@wil@@@wil@@A; wil::com_ptr_t<IApplicationResolver,wil::err_exception_policy> SystemSettings::StartupHandlers::StartupAppListItemSetting::m_appResolver
0x1800d8ca5  mov     rax, [rcx]
0x1800d8ca8  lea     r8, [rsp+340h+punk]
0x1800d8cad  mov     [rsp+340h+var_300], r8
0x1800d8cb2  mov     [rsp+340h+ppidl], rsi
0x1800d8cb7  mov     [rsp+340h+var_2F0], 1
0x1800d8cbc  xor     r9d, r9d
0x1800d8cbf  lea     r8, [rsp+340h+ppidl]
0x1800d8cc4  mov     rax, [rax+48h]
0x1800d8cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8ccd  mov     ebx, eax
0x1800d8ccf  lea     rcx, [rsp+340h+var_300]
0x1800d8cd4  call    ??1?$out_param_t@V?$com_ptr_t@UIShellItem@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<IShellItem,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IShellItem,wil::err_exception_policy>>(void)
0x1800d8cd9  test    ebx, ebx
0x1800d8cdb  jns     short loc_1800D8CE2
0x1800d8cdd  lea     edx, [rsi+37h]
0x1800d8ce0  jmp     short loc_1800D8CF4
0x1800d8ce2  mov     rcx, [rsp+340h+punk]; punk
0x1800d8ce7  test    rcx, rcx
0x1800d8cea  jnz     short loc_1800D8D0F
0x1800d8cec  mov     ebx, 80070002h
0x1800d8cf1  lea     edx, [rcx+38h]; void *
0x1800d8cf4  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d8cfb  mov     r9d, ebx; char *
0x1800d8cfe  mov     rcx, [rbp+248h]; this
0x1800d8d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8d0a  jmp     loc_1800D8E1E
0x1800d8d0f  mov     [rsp+340h+pv], rsi
0x1800d8d14  lea     rax, [rsp+340h+pv]
0x1800d8d19  mov     [rsp+340h+var_300], rax
0x1800d8d1e  mov     [rsp+340h+ppidl], rsi
0x1800d8d23  mov     [rsp+340h+var_2F0], 1
0x1800d8d28  lea     rdx, [rsp+340h+ppidl]; ppidl
0x1800d8d2d  call    cs:__imp_SHGetIDListFromObject
0x1800d8d33  mov     ebx, eax
0x1800d8d35  lea     rcx, [rsp+340h+var_300]
0x1800d8d3a  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800d8d3f  test    ebx, ebx
0x1800d8d41  jns     short loc_1800D8D7C
0x1800d8d43  mov     edx, 3Ah ; ':'; void *
0x1800d8d48  mov     r9d, ebx; char *
0x1800d8d4b  mov     rcx, [rbp+248h]; this
0x1800d8d52  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d8d59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8d5e  mov     rcx, [rsp+340h+pv]; pv
0x1800d8d63  test    rcx, rcx
0x1800d8d66  mov     [rsp+340h+pv], rsi
0x1800d8d6b  jz      loc_1800D8E1E
0x1800d8d71  call    cs:__imp_CoTaskMemFree
0x1800d8d77  jmp     loc_1800D8E1E
0x1800d8d7c  mov     ebx, 2B8h
0x1800d8d81  mov     r8d, ebx; Size
0x1800d8d84  xor     edx, edx; Val
0x1800d8d86  lea     rcx, [rsp+340h+psfi]; void *
0x1800d8d8b  call    memset_0
0x1800d8d90  mov     [rsp+340h+uFlags], 1008h; uFlags
0x1800d8d98  mov     r9d, ebx; cbFileInfo
0x1800d8d9b  lea     r8, [rsp+340h+psfi]; psfi
0x1800d8da0  xor     edx, edx; dwFileAttributes
0x1800d8da2  mov     rcx, [rsp+340h+pv]; pszPath
0x1800d8da7  call    cs:__imp_SHGetFileInfoW
0x1800d8dad  test    rax, rax
0x1800d8db0  jnz     short loc_1800D8DB7
0x1800d8db2  lea     edx, [rax+3Ch]
0x1800d8db5  jmp     short loc_1800D8DD1
0x1800d8db7  lea     rcx, [rsp+340h+psfi.szDisplayName]
0x1800d8dbc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d8dc0  inc     rax
0x1800d8dc3  cmp     [rcx+rax*2], si
0x1800d8dc7  jnz     short loc_1800D8DC0
0x1800d8dc9  test    rax, rax
0x1800d8dcc  jnz     short loc_1800D8DDB
0x1800d8dce  lea     edx, [rax+3Dh]
0x1800d8dd1  mov     ebx, 80070002h
0x1800d8dd6  jmp     loc_1800D8D48
0x1800d8ddb  mov     r9d, [rsp+340h+psfi.iIcon]
0x1800d8de0  lea     r8, [rsp+340h+psfi.szDisplayName]
0x1800d8de5  lea     rdx, aSD; "%s,%d"
0x1800d8dec  mov     rcx, rdi
0x1800d8def  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800d8df4  mov     ebx, eax
0x1800d8df6  test    eax, eax
0x1800d8df8  jns     short loc_1800D8E07
0x1800d8dfa  mov     r9d, eax
0x1800d8dfd  mov     edx, 3Eh ; '>'
0x1800d8e02  jmp     loc_1800D8D4B
0x1800d8e07  mov     rcx, [rsp+340h+pv]; pv
0x1800d8e0c  mov     [rsp+340h+pv], rsi
0x1800d8e11  test    rcx, rcx
0x1800d8e14  jz      short loc_1800D8E1C
0x1800d8e16  call    cs:__imp_CoTaskMemFree
0x1800d8e1c  mov     ebx, esi
0x1800d8e1e  lea     rcx, [rsp+340h+punk]
0x1800d8e23  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800d8e28  mov     eax, ebx
0x1800d8e2a  mov     rcx, [rbp+240h+var_20]
0x1800d8e31  xor     rcx, rsp; StackCookie
0x1800d8e34  call    __security_check_cookie
0x1800d8e39  mov     rbx, [rsp+340h+arg_0]
0x1800d8e41  add     rsp, 330h
0x1800d8e48  pop     rdi
0x1800d8e49  pop     rsi
0x1800d8e4a  pop     rbp
0x1800d8e4b  retn
```
