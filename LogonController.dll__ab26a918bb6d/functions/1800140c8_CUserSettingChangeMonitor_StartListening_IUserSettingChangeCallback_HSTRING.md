# CUserSettingChangeMonitor::StartListening(IUserSettingChangeCallback *,HSTRING__ *)

- ea: `0x1800140c8`
- end: `0x1800143aa`
- name: `?StartListening@CUserSettingChangeMonitor@@QEAAXPEAUIUserSettingChangeCallback@@PEAUHSTRING__@@@Z`
- size: `738`
- prototype: `void(CUserSettingChangeMonitor *__hidden this, struct IUserSettingChangeCallback *, HSTRING)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014798`
- `0x1800268e0`

## callees

- `0x180004b70`
- `0x18000cd1c`
- `0x18000df10`
- `0x1800131f4`
- `0x1800140c8`
- `0x1800143b0`
- `0x18001445c`
- `0x1800309a8`
- `0x180030b94`
- `0x1800638bc`
- `0x18006c000`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001414b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800142ff`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001414b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800142ff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014104`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800142b3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014104`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800142b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180014162`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180014162`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014171`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014171`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014399`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014399`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014270`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014270`

## string_xrefs

- `0x1800141a3`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CUserSettingChangeMonitor::StartListening(
        RTL_SRWLOCK *this,
        struct IUserSettingChangeCallback *a2,
        HSTRING a3)
{
  RTL_SRWLOCK *v6; // rsi
  char Ptr; // r15
  PVOID v8; // rcx
  PCWSTR StringRawBuffer; // rbx
  wil::details::registry_watcher_state *v10; // rbx
  LSTATUS Key; // eax
  __int64 v12; // r8
  bool v13; // sf
  wil::details::registry_watcher_state *v14; // r14
  __int64 v15; // rcx
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::registry_watcher_state *v17; // [rsp+60h] [rbp-A0h] BYREF
  char v18[8]; // [rsp+68h] [rbp-98h] BYREF
  char v19[104]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-28h]
  WCHAR SubKey[264]; // [rsp+E0h] [rbp-20h] BYREF

  v6 = this + 7;
  AcquireSRWLockExclusive(this + 7);
  Ptr = (char)this[10].Ptr;
  if ( this[6].Ptr != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(struct IUserSettingChangeCallback *))(*(_QWORD *)a2 + 8LL))(a2);
    v8 = this[6].Ptr;
    this[6].Ptr = a2;
    if ( v8 )
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  if ( !Ptr )
  {
    (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 1))(this);
    hKey[0] = (HKEY)this;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(hKey);
    Windows::Internal::ComTaskPool::QueueTask__lambda_6321e3babc0a816ffe9e019d46a6ea4f___(v15, hKey);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(hKey);
    (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 2))(this);
  }
  if ( a3 )
  {
    if ( !WindowsIsStringEmpty(a3) )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
      if ( (int)EnsureSystemDataRegistryKeyForUser(StringRawBuffer) >= 0
        && (int)StringCchPrintfW(
                  SubKey,
                  0x104u,
                  L"%s\\%s\\%s\\%s",
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                  StringRawBuffer,
                  L"AnyoneRead",
                  L"Colors") >= 0 )
      {
        (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 1))(this);
        hKey[0] = (HKEY)this;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(hKey);
        hKey[1] = (HKEY)this;
        v20 = 0;
        v20 = wistd::__function::__func__lambda_924dd07b144eb448811ab1679ea18154__void___cdecl_enum_wil::RegistryChangeKind__::__func__lambda_924dd07b144eb448811ab1679ea18154__void___cdecl_enum_wil::RegistryChangeKind__(
                v19,
                hKey);
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(hKey);
        v10 = 0;
        v17 = 0;
        hKey[0] = 0;
        Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x10u, 0, hKey, 0);
        v13 = Key < 0;
        if ( Key > 0 )
          v13 = 1;
        if ( v13 )
        {
          if ( hKey[0] )
            RegCloseKey(hKey[0]);
        }
        else
        {
          wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
            (__int64)&v17,
            (__int64)hKey,
            v12,
            (__int64)v18);
          if ( hKey[0] )
            RegCloseKey(hKey[0]);
          v10 = v17;
        }
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
        AcquireSRWLockExclusive(v6);
        v14 = (wil::details::registry_watcher_state *)this[12].Ptr;
        this[12].Ptr = 0;
        if ( &this[12] != (RTL_SRWLOCK *)&v17 )
        {
          this[12].Ptr = v10;
          v10 = 0;
        }
        if ( v10 )
          wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(v10);
        v17 = v14;
        hKey[0] = 0;
        wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(hKey);
        if ( v6 )
          ReleaseSRWLockExclusive(v6);
        wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v17);
        (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 2))(this);
      }
    }
  }
}

```

## disassembly

```asm
0x1800140c8  mov     [rsp-8+arg_8], rbx
0x1800140cd  push    rbp
0x1800140ce  push    rsi
0x1800140cf  push    rdi
0x1800140d0  push    r14
0x1800140d2  push    r15
0x1800140d4  lea     rbp, [rsp-200h]
0x1800140dc  sub     rsp, 300h
0x1800140e3  mov     rax, cs:__security_cookie
0x1800140ea  xor     rax, rsp
0x1800140ed  mov     [rbp+220h+var_30], rax
0x1800140f4  mov     r14, r8
0x1800140f7  mov     rbx, rdx
0x1800140fa  mov     rdi, rcx
0x1800140fd  lea     rsi, [rcx+38h]
0x180014101  mov     rcx, rsi; SRWLock
0x180014104  call    cs:__imp_AcquireSRWLockExclusive
0x18001410a  mov     r15b, [rdi+50h]
0x18001410e  cmp     [rdi+30h], rbx
0x180014112  jz      short loc_180014143
0x180014114  test    rbx, rbx
0x180014117  jz      short loc_180014129
0x180014119  mov     rax, [rbx]
0x18001411c  mov     rcx, rbx
0x18001411f  mov     rax, [rax+8]
0x180014123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014128  nop
0x180014129  mov     rcx, [rdi+30h]
0x18001412d  mov     [rdi+30h], rbx
0x180014131  test    rcx, rcx
0x180014134  jz      short loc_180014143
0x180014136  mov     rax, [rcx]
0x180014139  mov     rax, [rax+10h]
0x18001413d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014142  nop
0x180014143  test    rsi, rsi
0x180014146  jz      short loc_180014151
0x180014148  mov     rcx, rsi; SRWLock
0x18001414b  call    cs:__imp_ReleaseSRWLockExclusive
0x180014151  test    r15b, r15b
0x180014154  jz      loc_180014325
0x18001415a  test    r14, r14
0x18001415d  jz      short loc_1800141C3
0x18001415f  mov     rcx, r14; string
0x180014162  call    cs:__imp_WindowsIsStringEmpty
0x180014168  test    eax, eax
0x18001416a  jnz     short loc_1800141C3
0x18001416c  xor     edx, edx; length
0x18001416e  mov     rcx, r14; string
0x180014171  call    cs:__imp_WindowsGetStringRawBuffer
0x180014177  mov     rbx, rax
0x18001417a  mov     rcx, rax
0x18001417d  call    ?EnsureSystemDataRegistryKeyForUser@@YAJPEBG0W4SYSTEM_DATA_REGKEY_USER_ACCESS@@@Z; EnsureSystemDataRegistryKeyForUser(ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS)
0x180014182  test    eax, eax
0x180014184  js      short loc_1800141C3
0x180014186  lea     rax, aColors; "Colors"
0x18001418d  mov     [rsp+320h+lpSecurityAttributes], rax
0x180014192  mov     rcx, cs:off_18009E008; "AnyoneRead"
0x180014199  mov     qword ptr [rsp+320h+samDesired], rcx
0x18001419e  mov     qword ptr [rsp+320h+dwOptions], rbx
0x1800141a3  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800141aa  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800141b1  mov     edx, 104h; unsigned __int64
0x1800141b6  lea     rcx, [rbp+220h+SubKey]; unsigned __int16 *
0x1800141ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800141bf  test    eax, eax
0x1800141c1  jns     short loc_1800141E9
0x1800141c3  mov     rcx, [rbp+220h+var_30]
0x1800141ca  xor     rcx, rsp; StackCookie
0x1800141cd  call    __security_check_cookie
0x1800141d2  mov     rbx, [rsp+320h+arg_8]
0x1800141da  add     rsp, 300h
0x1800141e1  pop     r15
0x1800141e3  pop     r14
0x1800141e5  pop     rdi
0x1800141e6  pop     rsi
0x1800141e7  pop     rbp
0x1800141e8  retn
0x1800141e9  mov     rax, [rdi]
0x1800141ec  mov     rcx, rdi
0x1800141ef  mov     rax, [rax+8]
0x1800141f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141f8  nop
0x1800141f9  mov     [rsp+320h+hKey], rdi
0x1800141fe  lea     rcx, [rsp+320h+hKey]
0x180014203  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180014208  mov     [rsp+320h+var_2C8], rdi
0x18001420d  mov     [rbp+220h+var_248], 0
0x180014215  lea     rdx, [rsp+320h+hKey]
0x18001421a  lea     rcx, [rsp+320h+var_2B0]
0x18001421f  call    wistd____function____func__lambda_924dd07b144eb448811ab1679ea18154__void___cdecl_enum_wil__RegistryChangeKind______func__lambda_924dd07b144eb448811ab1679ea18154__void___cdecl_enum_wil__RegistryChangeKind__
0x180014224  mov     [rbp+220h+var_248], rax
0x180014228  lea     rcx, [rsp+320h+hKey]
0x18001422d  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180014232  nop
0x180014233  xor     ebx, ebx
0x180014235  mov     [rsp+320h+var_2C0], rbx
0x18001423a  mov     [rsp+320h+hKey], rbx
0x18001423f  mov     [rsp+320h+lpdwDisposition], rbx; lpdwDisposition
0x180014244  lea     rax, [rsp+320h+hKey]
0x180014249  mov     [rsp+320h+phkResult], rax; phkResult
0x18001424e  mov     [rsp+320h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180014253  mov     [rsp+320h+samDesired], 10h; samDesired
0x18001425b  mov     [rsp+320h+dwOptions], ebx; dwOptions
0x18001425f  xor     r9d, r9d; lpClass
0x180014262  xor     r8d, r8d; Reserved
0x180014265  lea     rdx, [rbp+220h+SubKey]; lpSubKey
0x180014269  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014270  call    cs:__imp_RegCreateKeyExW
0x180014276  test    eax, eax
0x180014278  jle     short loc_180014284
0x18001427a  movzx   eax, ax
0x18001427d  or      eax, 80070000h
0x180014282  test    eax, eax
0x180014284  jns     loc_18001437B
0x18001428a  mov     rcx, [rsp+320h+hKey]; hKey
0x18001428f  test    rcx, rcx
0x180014292  jz      short loc_18001429B
0x180014294  call    cs:__imp_RegCloseKey
0x18001429a  nop
0x18001429b  mov     rcx, [rbp+220h+var_248]
0x18001429f  test    rcx, rcx
0x1800142a2  jz      short loc_1800142B0
0x1800142a4  mov     rax, [rcx]
0x1800142a7  mov     rax, [rax+18h]
0x1800142ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142b0  mov     rcx, rsi; SRWLock
0x1800142b3  call    cs:__imp_AcquireSRWLockExclusive
0x1800142b9  lea     rax, [rdi+60h]
0x1800142bd  mov     r14, [rax]
0x1800142c0  mov     qword ptr [rax], 0
0x1800142c7  lea     rcx, [rsp+320h+var_2C0]
0x1800142cc  cmp     rax, rcx
0x1800142cf  jz      short loc_1800142D6
0x1800142d1  mov     [rax], rbx
0x1800142d4  xor     ebx, ebx
0x1800142d6  test    rbx, rbx
0x1800142d9  jnz     loc_18001436E
0x1800142df  mov     [rsp+320h+var_2C0], r14
0x1800142e4  mov     [rsp+320h+hKey], 0
0x1800142ed  lea     rcx, [rsp+320h+hKey]
0x1800142f2  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x1800142f7  test    rsi, rsi
0x1800142fa  jz      short loc_180014305
0x1800142fc  mov     rcx, rsi; SRWLock
0x1800142ff  call    cs:__imp_ReleaseSRWLockExclusive
0x180014305  lea     rcx, [rsp+320h+var_2C0]
0x18001430a  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x18001430f  nop
0x180014310  mov     rax, [rdi]
0x180014313  mov     rcx, rdi
0x180014316  mov     rax, [rax+10h]
0x18001431a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001431f  nop
0x180014320  jmp     loc_1800141C3
0x180014325  mov     rax, [rdi]
0x180014328  mov     rcx, rdi
0x18001432b  mov     rax, [rax+8]
0x18001432f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014334  nop
0x180014335  mov     [rsp+320h+hKey], rdi
0x18001433a  lea     rcx, [rsp+320h+hKey]
0x18001433f  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180014344  lea     rdx, [rsp+320h+hKey]
0x180014349  call    Windows__Internal__ComTaskPool__QueueTask__lambda_6321e3babc0a816ffe9e019d46a6ea4f___
0x18001434e  lea     rcx, [rsp+320h+hKey]
0x180014353  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180014358  nop
0x180014359  mov     rax, [rdi]
0x18001435c  mov     rcx, rdi
0x18001435f  mov     rax, [rax+10h]
0x180014363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014368  nop
0x180014369  jmp     loc_18001415A
0x18001436e  mov     rcx, rbx
0x180014371  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAUregistry_watcher_state@details@wil@@@Z$1?delete_registry_watcher_state@23@YAX0@ZPEAU123@@details@wil@@SAXPEAUregistry_watcher_state@23@@Z; wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(wil::details::registry_watcher_state *)
0x180014376  jmp     loc_1800142DF
0x18001437b  lea     r9, [rsp+320h+var_2B8]
0x180014380  lea     rdx, [rsp+320h+hKey]
0x180014385  lea     rcx, [rsp+320h+var_2C0]
0x18001438a  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18001438f  mov     rcx, [rsp+320h+hKey]; hKey
0x180014394  test    rcx, rcx
0x180014397  jz      short loc_18001439F
0x180014399  call    cs:__imp_RegCloseKey
0x18001439f  mov     rbx, [rsp+320h+var_2C0]
0x1800143a4  jmp     loc_18001429B
```
