# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackagedApps(std::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>> *)

- ea: `0x180043ce0`
- end: `0x180043f17`
- name: `?GetPackagedApps@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAV?$set@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@Z`
- size: `567`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800307bc`
- `0x18003ed98`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18000a13c`
- `0x18001e5c8`
- `0x180023c78`
- `0x18003d820`
- `0x1800434e4`
- `0x180043ce0`
- `0x18004706c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043dd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043e78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043eb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043dd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043e78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043eb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043e16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043e16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043e35`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackagedApps(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int i; // esi
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  PCWSTR StringRawBuffer; // rax
  PCWSTR v15; // rax
  HSTRING string; // [rsp+20h] [rbp-39h] BYREF
  unsigned int v18; // [rsp+28h] [rbp-31h] BYREF
  __int64 v19; // [rsp+30h] [rbp-29h] BYREF
  __int64 v20; // [rsp+38h] [rbp-21h] BYREF
  __int64 v21; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v22[16]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v24; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::clear(a2);
  v20 = 0;
  v4 = *(_QWORD *)(a1 + 400);
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 144LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  v6 = v5(v4, &v20);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 398;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v6,
      (int)string);
    goto LABEL_17;
  }
  v18 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 56LL))(v20, &v18);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 401;
    goto LABEL_5;
  }
  for ( i = 0; i < v18; ++i )
  {
    v19 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 48LL))(v20, i, &v19);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x196,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v10,
        (int)string);
      goto LABEL_15;
    }
    string = 0;
    v11 = v19;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 88LL);
    WindowsDeleteString(0);
    string = 0;
    v13 = v12(v11, &string);
    v7 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v13,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
LABEL_15:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      goto LABEL_17;
    }
    v21 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( (int)SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFromFamilyName(
                a1,
                StringRawBuffer,
                &v21) >= 0 )
    {
      v15 = WindowsGetStringRawBuffer(string, 0);
      std::wstring::wstring((__int64)v23, (__int64)v15);
      v24 = 1;
      std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::insert<0,0>(
        a2,
        (__int64)v22,
        (__int64)v23);
      std::wstring::_Tidy_deallocate(v23);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  }
  v7 = 0;
LABEL_17:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  return v7;
}

```

## disassembly

```asm
0x180043ce0  mov     [rsp-8+arg_10], rbx
0x180043ce5  push    rbp
0x180043ce6  push    rsi
0x180043ce7  push    rdi
0x180043ce8  push    r14
0x180043cea  push    r15
0x180043cec  lea     rbp, [rsp-37h]
0x180043cf1  sub     rsp, 90h
0x180043cf8  mov     rax, cs:__security_cookie
0x180043cff  xor     rax, rsp
0x180043d02  mov     [rbp+57h+var_30], rax
0x180043d06  mov     r15, rdx
0x180043d09  mov     r14, rcx
0x180043d0c  mov     rcx, rdx
0x180043d0f  call    ?clear@?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::clear(void)
0x180043d14  mov     [rbp+57h+var_78], 0
0x180043d1c  mov     rdi, [r14+190h]
0x180043d23  mov     rax, [rdi]
0x180043d26  mov     rbx, [rax+90h]
0x180043d2d  lea     rcx, [rbp+57h+var_78]
0x180043d31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043d36  lea     rdx, [rbp+57h+var_78]
0x180043d3a  mov     rcx, rdi
0x180043d3d  mov     rax, rbx
0x180043d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d45  mov     ebx, eax
0x180043d47  test    eax, eax
0x180043d49  jns     short loc_180043D52
0x180043d4b  mov     edx, 18Eh
0x180043d50  jmp     short loc_180043D78
0x180043d52  mov     [rbp+57h+var_88], 0
0x180043d59  mov     rcx, [rbp+57h+var_78]
0x180043d5d  mov     rax, [rcx]
0x180043d60  lea     rdx, [rbp+57h+var_88]
0x180043d64  mov     rax, [rax+38h]
0x180043d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d6d  mov     ebx, eax
0x180043d6f  test    eax, eax
0x180043d71  jns     short loc_180043D90
0x180043d73  mov     edx, 191h; void *
0x180043d78  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043d7f  mov     r9d, eax; char *
0x180043d82  mov     rcx, [rbp+5Fh]; this
0x180043d86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043d8b  jmp     loc_180043EE9
0x180043d90  xor     esi, esi
0x180043d92  cmp     esi, [rbp+57h+var_88]
0x180043d95  jnb     loc_180043EE7
0x180043d9b  mov     [rbp+57h+var_80], 0
0x180043da3  mov     rcx, [rbp+57h+var_78]
0x180043da7  mov     rax, [rcx]
0x180043daa  lea     r8, [rbp+57h+var_80]
0x180043dae  mov     edx, esi
0x180043db0  mov     rax, [rax+30h]
0x180043db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043db9  mov     ebx, eax
0x180043dbb  test    eax, eax
0x180043dbd  js      loc_180043EC3
0x180043dc3  mov     [rbp+57h+string], 0
0x180043dcb  mov     rdi, [rbp+57h+var_80]
0x180043dcf  mov     rax, [rdi]
0x180043dd2  mov     rbx, [rax+58h]
0x180043dd6  xor     ecx, ecx; string
0x180043dd8  call    cs:__imp_WindowsDeleteString
0x180043dde  mov     [rbp+57h+string], 0
0x180043de6  lea     rdx, [rbp+57h+string]
0x180043dea  mov     rcx, rdi
0x180043ded  mov     rax, rbx
0x180043df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043df5  mov     ebx, eax
0x180043df7  test    eax, eax
0x180043df9  js      loc_180043E96
0x180043dff  mov     [rbp+57h+var_70], 0
0x180043e07  lea     rcx, [rbp+57h+var_70]
0x180043e0b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043e10  xor     edx, edx; length
0x180043e12  mov     rcx, [rbp+57h+string]; string
0x180043e16  call    cs:__imp_WindowsGetStringRawBuffer
0x180043e1c  lea     r8, [rbp+57h+var_70]
0x180043e20  mov     rdx, rax
0x180043e23  mov     rcx, r14
0x180043e26  call    ?GetPackageFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEBGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)
0x180043e2b  test    eax, eax
0x180043e2d  js      short loc_180043E6A
0x180043e2f  xor     edx, edx; length
0x180043e31  mov     rcx, [rbp+57h+string]; string
0x180043e35  call    cs:__imp_WindowsGetStringRawBuffer
0x180043e3b  mov     rdx, rax
0x180043e3e  lea     rcx, [rbp+57h+var_58]
0x180043e42  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043e47  mov     [rbp+57h+var_38], 1
0x180043e4f  lea     r8, [rbp+57h+var_58]
0x180043e53  lea     rdx, [rbp+57h+var_68]
0x180043e57  mov     rcx, r15
0x180043e5a  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@_N@1@$$QEAUAppIdentity@BatteryUsageHandlers@SystemSettings@@@Z; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::insert<0,0>(SystemSettings::BatteryUsageHandlers::AppIdentity &&)
0x180043e5f  nop
0x180043e60  lea     rcx, [rbp+57h+var_58]
0x180043e64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043e69  nop
0x180043e6a  lea     rcx, [rbp+57h+var_70]
0x180043e6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043e73  nop
0x180043e74  mov     rcx, [rbp+57h+string]; string
0x180043e78  call    cs:__imp_WindowsDeleteString
0x180043e7e  mov     [rbp+57h+string], 0
0x180043e86  lea     rcx, [rbp+57h+var_80]
0x180043e8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043e8f  inc     esi
0x180043e91  jmp     loc_180043D92
0x180043e96  mov     rcx, [rbp+5Fh]; this
0x180043e9a  mov     r9d, eax; char *
0x180043e9d  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043ea4  mov     edx, 199h; void *
0x180043ea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043eae  nop
0x180043eaf  mov     rcx, [rbp+57h+string]; string
0x180043eb3  call    cs:__imp_WindowsDeleteString
0x180043eb9  mov     [rbp+57h+string], 0
0x180043ec1  jmp     short loc_180043EDC
0x180043ec3  mov     rcx, [rbp+5Fh]; this
0x180043ec7  mov     r9d, eax; char *
0x180043eca  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043ed1  mov     edx, 196h; void *
0x180043ed6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043edb  nop
0x180043edc  lea     rcx, [rbp+57h+var_80]
0x180043ee0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043ee5  jmp     short loc_180043EE9
0x180043ee7  xor     ebx, ebx
0x180043ee9  lea     rcx, [rbp+57h+var_78]
0x180043eed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043ef2  mov     eax, ebx
0x180043ef4  mov     rcx, [rbp+57h+var_30]
0x180043ef8  xor     rcx, rsp; StackCookie
0x180043efb  call    __security_check_cookie
0x180043f00  mov     rbx, [rsp+0B0h+arg_10]
0x180043f08  add     rsp, 90h
0x180043f0f  pop     r15
0x180043f11  pop     r14
0x180043f13  pop     rdi
0x180043f14  pop     rsi
0x180043f15  pop     rbp
0x180043f16  retn
```
