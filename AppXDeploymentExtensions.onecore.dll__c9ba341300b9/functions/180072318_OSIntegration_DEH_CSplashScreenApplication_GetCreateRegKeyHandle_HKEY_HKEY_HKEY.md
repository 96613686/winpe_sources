# OSIntegration::DEH::CSplashScreenApplication::_GetCreateRegKeyHandle(HKEY__ * *,HKEY__ * *,HKEY__ * *)

- ea: `0x180072318`
- end: `0x1800728cc`
- name: `?_GetCreateRegKeyHandle@CSplashScreenApplication@DEH@OSIntegration@@AEAAJPEAPEAUHKEY__@@00@Z`
- size: `1460`
- prototype: `__int64 __fastcall(OSIntegration::DEH::CSplashScreenApplication *__hidden this, HKEY *, HKEY *, HKEY *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180071f10`
- `0x180072200`

## callees

- `0x18004f3c4`
- `0x18005c774`
- `0x180072318`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a2854`
- `0x1800cceb4`
- `0x1800f0700`
- `0x1800f073c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007250c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007250c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072395`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800723aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072427`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800725ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800725c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072616`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007262b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072775`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007280a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072822`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072872`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072886`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007289b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800728b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072395`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800723aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072427`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800725ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800725c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072616`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007262b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072775`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007280a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072822`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072872`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072886`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007289b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800728b0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800723f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072468`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072484`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800724c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800726b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007273f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800727b0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800723f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072468`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072484`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800724c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800726b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007273f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800727b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800727d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800727d8`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180072502`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18007255f`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180072502`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18007255f`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800724e4`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800724e4`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180072599`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180072601`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180072709`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180072599`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180072601`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180072709`

## string_xrefs

- `0x180072375`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x180072404`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x180072571`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x1800725dc`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x18007264a`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x1800726c4`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x180072750`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x1800727e9`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::DEH::CSplashScreenApplication::_GetCreateRegKeyHandle(
        LPCWSTR *this,
        HKEY *a2,
        HKEY *a3,
        HKEY *a4)
{
  void *v8; // rdi
  int IsStateSeparationEnabled; // eax
  unsigned int v10; // ebx
  HKEY v11; // rcx
  bool v12; // cc
  HKEY v13; // rcx
  bool v14; // cc
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rbx
  unsigned __int64 v19; // rax
  const char *v20; // r9
  unsigned int LastError; // esi
  int Error; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  HKEY v26; // rax
  HKEY v27; // rcx
  HKEY v28; // rax
  HKEY v29; // rax
  int dwOptions; // [rsp+20h] [rbp-49h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-49h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-49h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-49h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-49h]
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-11h] BYREF
  HKEY v37; // [rsp+60h] [rbp-9h] BYREF
  HKEY v38; // [rsp+68h] [rbp-1h] BYREF
  _QWORD v39[10]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned int v41; // [rsp+D0h] [rbp+67h] BYREF

  v8 = 0;
  phkResult = 0;
  hKey = 0;
  if ( *((_BYTE *)this[25] + 406) )
  {
    LOBYTE(v41) = 0;
    IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled((bool *)&v41);
    v10 = IsStateSeparationEnabled;
    if ( IsStateSeparationEnabled < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CF,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
        (const char *)(unsigned int)IsStateSeparationEnabled,
        dwOptions);
LABEL_4:
      v11 = hKey;
      v12 = (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_5:
      if ( v12 )
        RegCloseKey(v11);
      v13 = phkResult;
      v14 = (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_8:
      if ( v14 )
        RegCloseKey(v13);
      return v10;
    }
    if ( (_BYTE)v41 )
    {
      v16 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"OSDATA\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\SystemAppData",
              0,
              0,
              0,
              0xF003Fu,
              0,
              &phkResult,
              0);
      if ( v16 )
      {
        v17 = 467;
LABEL_14:
        v10 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v17,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
                (const char *)v16,
                dwOptionsa);
        if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(hKey);
        v13 = phkResult;
        v14 = (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
        goto LABEL_8;
      }
      v16 = RegCreateKeyExW(phkResult, this[13], 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
      if ( v16 )
      {
        v17 = 468;
        goto LABEL_14;
      }
    }
    else
    {
      v16 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\SystemAppData",
              0,
              0,
              0,
              0xF003Fu,
              0,
              &phkResult,
              0);
      if ( v16 )
      {
        v17 = 472;
        goto LABEL_14;
      }
      v16 = RegCreateKeyExW(phkResult, this[13], 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
      if ( v16 )
      {
        v17 = 473;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v18 = OpenStateExplicit(this[21], this[13]);
    v39[0] = v18;
    v41 = 0;
    if ( !(unsigned int)GetSystemAppDataKey(v18, 0, 0, &v41) )
    {
      if ( GetLastError() != 122 )
      {
        Error = ResultFromKnownLastError();
        v10 = Error;
        if ( Error < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1EB,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
            (const char *)(unsigned int)Error,
            dwOptions);
        operator delete(0, 2u);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(v39);
        goto LABEL_47;
      }
      v19 = 2LL * v41;
      if ( !is_mul_ok(v41, 2u) )
        v19 = -1;
      v8 = operator new[](v19, (const struct std::nothrow_t *)std::nothrow);
      if ( !v8 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E7,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
          (const char *)0x8007000ELL,
          dwOptions);
        operator delete(0, 2u);
        if ( v18 )
          CloseState(v18);
        if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(hKey);
        if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(phkResult);
        return 2147942414LL;
      }
      operator delete(0, 2u);
    }
    if ( !(unsigned int)GetSystemAppDataKey(v18, &phkResult, v8, &v41) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1EF,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
                    v20);
      operator delete(v8, 2u);
      if ( v18 )
        CloseState(v18);
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(hKey);
      if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(phkResult);
      return LastError;
    }
    v23 = RegCreateKeyExW(phkResult, (LPCWSTR)v8, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v23 )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1F1,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
              (const char *)v23,
              dwOptionsb);
      operator delete(v8, 2u);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(v39);
      goto LABEL_4;
    }
    operator delete(v8, 2u);
    if ( v18 )
      CloseState(v18);
  }
  v37 = 0;
  v24 = RegCreateKeyExW(hKey, L"SplashScreen", 0, 0, 0, 0xF003Fu, 0, &v37, 0);
  if ( v24 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1F5,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
            (const char *)v24,
            dwOptionsc);
    if ( (unsigned __int64)v37 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(v37);
    goto LABEL_4;
  }
  v38 = 0;
  if ( RegCreateKeyExW(v37, this[16], 0, 0, 0, 0xF003Fu, 0, &v38, 0) == 5 )
  {
    v25 = RegOpenKeyExW(v37, this[16], 0, 0x20019u, &v38);
    if ( v25 )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x202,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
              (const char *)v25,
              dwOptionsd);
      if ( (unsigned __int64)v38 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(v38);
      if ( (unsigned __int64)v37 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(v37);
LABEL_47:
      v11 = hKey;
      v12 = (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
      goto LABEL_5;
    }
  }
  if ( a2 )
  {
    v26 = v38;
    v27 = 0;
    v38 = 0;
    *a2 = v26;
  }
  else
  {
    v27 = v38;
  }
  if ( a3 )
  {
    v28 = v37;
    v37 = 0;
    *a3 = v28;
  }
  if ( a4 )
  {
    v29 = hKey;
    hKey = 0;
    *a4 = v29;
  }
  if ( (unsigned __int64)v27 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v27);
  if ( (unsigned __int64)v37 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v37);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  return 0;
}

```

## disassembly

```asm
0x180072318  push    rbp
0x18007231a  push    rbx
0x18007231b  push    rsi
0x18007231c  push    rdi
0x18007231d  push    r12
0x18007231f  push    r13
0x180072321  push    r14
0x180072323  push    r15
0x180072325  lea     rbp, [rsp-1Fh]
0x18007232a  sub     rsp, 88h
0x180072331  mov     r15, r9
0x180072334  mov     r13, r8
0x180072337  mov     r12, rdx
0x18007233a  mov     r14, rcx
0x18007233d  xor     edi, edi
0x18007233f  mov     [rbp+57h+var_68], rdi
0x180072343  mov     [rbp+57h+hKey], rdi
0x180072347  mov     rax, [rcx+0C8h]
0x18007234e  cmp     [rax+196h], dil
0x180072355  jz      loc_1800724D9
0x18007235b  mov     byte ptr [rbp+57h+arg_0], dil
0x18007235f  lea     rcx, [rbp+57h+arg_0]; bool *
0x180072363  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x180072368  mov     ebx, eax
0x18007236a  test    eax, eax
0x18007236c  jns     short loc_1800723B7
0x18007236e  mov     rcx, [rbp+5Fh]; this
0x180072372  mov     r9d, eax; char *
0x180072375  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007237c  mov     edx, 1CFh; void *
0x180072381  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072386  nop
0x180072387  mov     rcx, [rbp+57h+hKey]; hKey
0x18007238b  lea     rdx, [rcx-1]
0x18007238f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180072393  ja      short loc_18007239C
0x180072395  call    cs:__imp_RegCloseKey
0x18007239b  nop
0x18007239c  mov     rcx, [rbp+57h+var_68]; hKey
0x1800723a0  lea     rax, [rcx-1]
0x1800723a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800723a8  ja      short loc_1800723B0
0x1800723aa  call    cs:__imp_RegCloseKey
0x1800723b0  mov     eax, ebx
0x1800723b2  jmp     loc_1800728B8
0x1800723b7  mov     [rsp+0C0h+lpdwDisposition], rdi; lpdwDisposition
0x1800723bc  lea     rax, [rbp+57h+var_68]
0x1800723c0  mov     esi, 0F003Fh
0x1800723c5  xor     r9d, r9d; lpClass
0x1800723c8  xor     r8d, r8d; Reserved
0x1800723cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800723d2  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800723d7  mov     [rsp+0C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800723dc  mov     [rsp+0C0h+samDesired], esi; samDesired
0x1800723e0  mov     [rsp+0C0h+dwOptions], edi; unsigned int
0x1800723e4  cmp     byte ptr [rbp+57h+arg_0], dil
0x1800723e8  jz      loc_18007247D
0x1800723ee  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Classes\\Local Settin"...
0x1800723f5  call    cs:__imp_RegCreateKeyExW
0x1800723fb  test    eax, eax
0x1800723fd  jz      short loc_18007243F
0x1800723ff  mov     edx, 1D3h; void *
0x180072404  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007240b  mov     r9d, eax; char *
0x18007240e  mov     rcx, [rbp+5Fh]; this
0x180072412  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180072417  mov     ebx, eax
0x180072419  mov     rcx, [rbp+57h+hKey]; hKey
0x18007241d  lea     rdx, [rcx-1]
0x180072421  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180072425  ja      short loc_18007242E
0x180072427  call    cs:__imp_RegCloseKey
0x18007242d  nop
0x18007242e  mov     rcx, [rbp+57h+var_68]
0x180072432  lea     rdx, [rcx-1]
0x180072436  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007243a  jmp     loc_1800723A8
0x18007243f  mov     [rsp+0C0h+lpdwDisposition], rdi; lpdwDisposition
0x180072444  lea     rax, [rbp+57h+hKey]
0x180072448  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18007244d  mov     [rsp+0C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180072452  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180072456  mov     [rsp+0C0h+dwOptions], edi; dwOptions
0x18007245a  xor     r9d, r9d; lpClass
0x18007245d  xor     r8d, r8d; Reserved
0x180072460  mov     rdx, [r14+68h]; lpSubKey
0x180072464  mov     rcx, [rbp+57h+var_68]; hKey
0x180072468  call    cs:__imp_RegCreateKeyExW
0x18007246e  test    eax, eax
0x180072470  jz      loc_18007270F
0x180072476  mov     edx, 1D4h
0x18007247b  jmp     short loc_180072404
0x18007247d  lea     rdx, aSoftwareClasse; "Software\\Classes\\Local Settings\\Soft"...
0x180072484  call    cs:__imp_RegCreateKeyExW
0x18007248a  test    eax, eax
0x18007248c  jz      short loc_180072498
0x18007248e  mov     edx, 1D8h
0x180072493  jmp     loc_180072404
0x180072498  mov     [rsp+0C0h+lpdwDisposition], rdi; lpdwDisposition
0x18007249d  lea     rax, [rbp+57h+hKey]
0x1800724a1  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800724a6  mov     [rsp+0C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800724ab  mov     [rsp+0C0h+samDesired], esi; samDesired
0x1800724af  mov     [rsp+0C0h+dwOptions], edi; dwOptions
0x1800724b3  xor     r9d, r9d; lpClass
0x1800724b6  xor     r8d, r8d; Reserved
0x1800724b9  mov     rdx, [r14+68h]; lpSubKey
0x1800724bd  mov     rcx, [rbp+57h+var_68]; hKey
0x1800724c1  call    cs:__imp_RegCreateKeyExW
0x1800724c7  test    eax, eax
0x1800724c9  jz      loc_18007270F
0x1800724cf  mov     edx, 1D9h
0x1800724d4  jmp     loc_180072404
0x1800724d9  mov     rdx, [rcx+68h]
0x1800724dd  mov     rcx, [rcx+0A8h]
0x1800724e4  call    cs:__imp_OpenStateExplicit
0x1800724ea  mov     rbx, rax
0x1800724ed  mov     [rbp+57h+var_50], rax
0x1800724f1  xor     esi, esi
0x1800724f3  mov     [rbp+57h+arg_0], esi
0x1800724f6  lea     r9, [rbp+57h+arg_0]
0x1800724fa  xor     r8d, r8d
0x1800724fd  xor     edx, edx
0x1800724ff  mov     rcx, rax
0x180072502  call    cs:__imp_GetSystemAppDataKey
0x180072508  test    eax, eax
0x18007250a  jnz     short loc_180072551
0x18007250c  call    cs:__imp_GetLastError
0x180072512  cmp     eax, 7Ah ; 'z'
0x180072515  jnz     loc_180072638
0x18007251b  mov     ecx, [rbp+57h+arg_0]
0x18007251e  lea     eax, [rsi+2]
0x180072521  mul     rcx
0x180072524  lea     rcx, [rsi-1]
0x180072528  cmovb   rax, rcx
0x18007252c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180072533  mov     rcx, rax; unsigned __int64
0x180072536  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007253b  mov     rdi, rax
0x18007253e  test    rax, rax
0x180072541  jz      loc_1800725D0
0x180072547  lea     edx, [rsi+2]; unsigned __int64
0x18007254a  xor     ecx, ecx; void *
0x18007254c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180072551  lea     r9, [rbp+57h+arg_0]
0x180072555  mov     r8, rdi
0x180072558  lea     rdx, [rbp+57h+var_68]
0x18007255c  mov     rcx, rbx
0x18007255f  call    cs:__imp_GetSystemAppDataKey
0x180072565  test    eax, eax
0x180072567  jnz     loc_180072682
0x18007256d  mov     rcx, [rbp+5Fh]; this
0x180072571  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180072578  mov     edx, 1EFh; void *
0x18007257d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072582  mov     esi, eax
0x180072584  mov     edx, 2; unsigned __int64
0x180072589  mov     rcx, rdi; void *
0x18007258c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180072591  test    rbx, rbx
0x180072594  jz      short loc_1800725A0
0x180072596  mov     rcx, rbx
0x180072599  call    cs:__imp_CloseState
0x18007259f  nop
0x1800725a0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800725a4  lea     rdx, [rcx-1]
0x1800725a8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800725ac  ja      short loc_1800725B5
0x1800725ae  call    cs:__imp_RegCloseKey
0x1800725b4  nop
0x1800725b5  mov     rcx, [rbp+57h+var_68]; hKey
0x1800725b9  lea     rax, [rcx-1]
0x1800725bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800725c1  ja      short loc_1800725C9
0x1800725c3  call    cs:__imp_RegCloseKey
0x1800725c9  mov     eax, esi
0x1800725cb  jmp     loc_1800728B8
0x1800725d0  mov     rcx, [rbp+5Fh]; this
0x1800725d4  mov     edi, 8007000Eh
0x1800725d9  mov     r9d, edi; char *
0x1800725dc  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800725e3  mov     edx, 1E7h; void *
0x1800725e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800725ed  mov     edx, 2; unsigned __int64
0x1800725f2  xor     ecx, ecx; void *
0x1800725f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800725f9  test    rbx, rbx
0x1800725fc  jz      short loc_180072608
0x1800725fe  mov     rcx, rbx
0x180072601  call    cs:__imp_CloseState
0x180072607  nop
0x180072608  mov     rcx, [rbp+57h+hKey]; hKey
0x18007260c  lea     rax, [rcx-1]
0x180072610  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180072614  ja      short loc_18007261D
0x180072616  call    cs:__imp_RegCloseKey
0x18007261c  nop
0x18007261d  mov     rcx, [rbp+57h+var_68]; hKey
0x180072621  lea     rdx, [rcx-1]
0x180072625  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180072629  ja      short loc_180072631
0x18007262b  call    cs:__imp_RegCloseKey
0x180072631  mov     eax, edi
0x180072633  jmp     loc_1800728B8
0x180072638  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18007263d  mov     ebx, eax
0x18007263f  test    eax, eax
0x180072641  jns     short loc_18007265B
0x180072643  mov     rcx, [rbp+5Fh]; this
0x180072647  mov     r9d, eax; char *
0x18007264a  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180072651  mov     edx, 1EBh; void *
0x180072656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007265b  mov     edx, 2; unsigned __int64
0x180072660  xor     ecx, ecx; void *
0x180072662  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180072667  lea     rcx, [rbp+57h+var_50]
0x18007266b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180072670  nop
0x180072671  mov     rcx, [rbp+57h+hKey]
0x180072675  lea     rax, [rcx-1]
0x180072679  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007267d  jmp     loc_180072393
0x180072682  mov     [rsp+0C0h+lpdwDisposition], rsi; lpdwDisposition
0x180072687  lea     rax, [rbp+57h+hKey]
0x18007268b  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180072690  mov     [rsp+0C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180072695  mov     esi, 0F003Fh
0x18007269a  mov     [rsp+0C0h+samDesired], esi; samDesired
0x18007269e  mov     [rsp+0C0h+dwOptions], 0; unsigned int
0x1800726a6  xor     r9d, r9d; lpClass
0x1800726a9  xor     r8d, r8d; Reserved
0x1800726ac  mov     rdx, rdi; lpSubKey
0x1800726af  mov     rcx, [rbp+57h+var_68]; hKey
0x1800726b3  call    cs:__imp_RegCreateKeyExW
0x1800726b9  test    eax, eax
0x1800726bb  jz      short loc_1800726F2
0x1800726bd  mov     rcx, [rbp+5Fh]; this
0x1800726c1  mov     r9d, eax; char *
0x1800726c4  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800726cb  mov     edx, 1F1h; void *
0x1800726d0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800726d5  mov     ebx, eax
0x1800726d7  mov     edx, 2; unsigned __int64
0x1800726dc  mov     rcx, rdi; void *
0x1800726df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800726e4  lea     rcx, [rbp+57h+var_50]
0x1800726e8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800726ed  jmp     loc_180072387
0x1800726f2  mov     edx, 2; unsigned __int64
0x1800726f7  mov     rcx, rdi; void *
0x1800726fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800726ff  xor     edi, edi
0x180072701  test    rbx, rbx
0x180072704  jz      short loc_18007270F
0x180072706  mov     rcx, rbx
0x180072709  call    cs:__imp_CloseState
0x18007270f  mov     [rbp+57h+var_60], rdi
0x180072713  mov     [rsp+0C0h+lpdwDisposition], rdi; lpdwDisposition
0x180072718  lea     rax, [rbp+57h+var_60]
0x18007271c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180072721  mov     [rsp+0C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180072726  mov     [rsp+0C0h+samDesired], esi; samDesired
0x18007272a  mov     [rsp+0C0h+dwOptions], edi; unsigned int
0x18007272e  xor     r9d, r9d; lpClass
0x180072731  xor     r8d, r8d; Reserved
0x180072734  lea     rdx, aSplashscreen; "SplashScreen"
0x18007273b  mov     rcx, [rbp+57h+hKey]; hKey
0x18007273f  call    cs:__imp_RegCreateKeyExW
0x180072745  test    eax, eax
0x180072747  jz      short loc_180072780
0x180072749  mov     rcx, [rbp+5Fh]; this
0x18007274d  mov     r9d, eax; char *
0x180072750  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180072757  mov     edx, 1F5h; void *
0x18007275c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180072761  mov     ebx, eax
0x180072763  mov     rcx, [rbp+57h+var_60]; hKey
0x180072767  lea     rdx, [rcx-1]
0x18007276b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007276f  ja      loc_180072387
0x180072775  call    cs:__imp_RegCloseKey
0x18007277b  jmp     loc_180072387
0x180072780  mov     [rbp+57h+var_58], rdi
0x180072784  mov     [rsp+0C0h+lpdwDisposition], rdi; lpdwDisposition
0x180072789  lea     rax, [rbp+57h+var_58]
0x18007278d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180072792  mov     [rsp+0C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180072797  mov     [rsp+0C0h+samDesired], esi; samDesired
0x18007279b  mov     [rsp+0C0h+dwOptions], edi; dwOptions
0x18007279f  xor     r9d, r9d; lpClass
0x1800727a2  xor     r8d, r8d; Reserved
0x1800727a5  mov     rdx, [r14+80h]; lpSubKey
0x1800727ac  mov     rcx, [rbp+57h+var_60]; hKey
0x1800727b0  call    cs:__imp_RegCreateKeyExW
0x1800727b6  cmp     eax, 5
0x1800727b9  jnz     short loc_18007282D
0x1800727bb  lea     rax, [rbp+57h+var_58]
0x1800727bf  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x1800727c4  mov     r9d, 20019h; samDesired
  ... truncated ...
```
