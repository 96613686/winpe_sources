# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackagedApps(std::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>> *)

- ea: `0x180043aa0`
- end: `0x180043cd7`
- name: `?GetPackagedApps@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJPEAV?$set@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@Z`
- size: `567`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800334f0`
- `0x18003ea14`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18000a13c`
- `0x18001e5c8`
- `0x180023c78`
- `0x18003d820`
- `0x180043258`
- `0x180043aa0`
- `0x18004706c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043b98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043c38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043c73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043b98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043c38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043c73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043bd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043bd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043bf5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackagedApps(__int64 a1, __int64 *a2)
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
  v4 = *(_QWORD *)(a1 + 392);
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 144LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  v6 = v5(v4, &v20);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 1880;
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
    v8 = 1883;
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
        (void *)0x760,
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
        (void *)0x763,
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
    if ( (int)SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFromFamilyName(
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
0x180043aa0  mov     [rsp-8+arg_10], rbx
0x180043aa5  push    rbp
0x180043aa6  push    rsi
0x180043aa7  push    rdi
0x180043aa8  push    r14
0x180043aaa  push    r15
0x180043aac  lea     rbp, [rsp-37h]
0x180043ab1  sub     rsp, 90h
0x180043ab8  mov     rax, cs:__security_cookie
0x180043abf  xor     rax, rsp
0x180043ac2  mov     [rbp+57h+var_30], rax
0x180043ac6  mov     r15, rdx
0x180043ac9  mov     r14, rcx
0x180043acc  mov     rcx, rdx
0x180043acf  call    ?clear@?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::clear(void)
0x180043ad4  mov     [rbp+57h+var_78], 0
0x180043adc  mov     rdi, [r14+188h]
0x180043ae3  mov     rax, [rdi]
0x180043ae6  mov     rbx, [rax+90h]
0x180043aed  lea     rcx, [rbp+57h+var_78]
0x180043af1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043af6  lea     rdx, [rbp+57h+var_78]
0x180043afa  mov     rcx, rdi
0x180043afd  mov     rax, rbx
0x180043b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b05  mov     ebx, eax
0x180043b07  test    eax, eax
0x180043b09  jns     short loc_180043B12
0x180043b0b  mov     edx, 758h
0x180043b10  jmp     short loc_180043B38
0x180043b12  mov     [rbp+57h+var_88], 0
0x180043b19  mov     rcx, [rbp+57h+var_78]
0x180043b1d  mov     rax, [rcx]
0x180043b20  lea     rdx, [rbp+57h+var_88]
0x180043b24  mov     rax, [rax+38h]
0x180043b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b2d  mov     ebx, eax
0x180043b2f  test    eax, eax
0x180043b31  jns     short loc_180043B50
0x180043b33  mov     edx, 75Bh; void *
0x180043b38  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043b3f  mov     r9d, eax; char *
0x180043b42  mov     rcx, [rbp+5Fh]; this
0x180043b46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043b4b  jmp     loc_180043CA9
0x180043b50  xor     esi, esi
0x180043b52  cmp     esi, [rbp+57h+var_88]
0x180043b55  jnb     loc_180043CA7
0x180043b5b  mov     [rbp+57h+var_80], 0
0x180043b63  mov     rcx, [rbp+57h+var_78]
0x180043b67  mov     rax, [rcx]
0x180043b6a  lea     r8, [rbp+57h+var_80]
0x180043b6e  mov     edx, esi
0x180043b70  mov     rax, [rax+30h]
0x180043b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b79  mov     ebx, eax
0x180043b7b  test    eax, eax
0x180043b7d  js      loc_180043C83
0x180043b83  mov     [rbp+57h+string], 0
0x180043b8b  mov     rdi, [rbp+57h+var_80]
0x180043b8f  mov     rax, [rdi]
0x180043b92  mov     rbx, [rax+58h]
0x180043b96  xor     ecx, ecx; string
0x180043b98  call    cs:__imp_WindowsDeleteString
0x180043b9e  mov     [rbp+57h+string], 0
0x180043ba6  lea     rdx, [rbp+57h+string]
0x180043baa  mov     rcx, rdi
0x180043bad  mov     rax, rbx
0x180043bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bb5  mov     ebx, eax
0x180043bb7  test    eax, eax
0x180043bb9  js      loc_180043C56
0x180043bbf  mov     [rbp+57h+var_70], 0
0x180043bc7  lea     rcx, [rbp+57h+var_70]
0x180043bcb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043bd0  xor     edx, edx; length
0x180043bd2  mov     rcx, [rbp+57h+string]; string
0x180043bd6  call    cs:__imp_WindowsGetStringRawBuffer
0x180043bdc  lea     r8, [rbp+57h+var_70]
0x180043be0  mov     rdx, rax
0x180043be3  mov     rcx, r14
0x180043be6  call    ?GetPackageFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJPEBGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)
0x180043beb  test    eax, eax
0x180043bed  js      short loc_180043C2A
0x180043bef  xor     edx, edx; length
0x180043bf1  mov     rcx, [rbp+57h+string]; string
0x180043bf5  call    cs:__imp_WindowsGetStringRawBuffer
0x180043bfb  mov     rdx, rax
0x180043bfe  lea     rcx, [rbp+57h+var_58]
0x180043c02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043c07  mov     [rbp+57h+var_38], 1
0x180043c0f  lea     r8, [rbp+57h+var_58]
0x180043c13  lea     rdx, [rbp+57h+var_68]
0x180043c17  mov     rcx, r15
0x180043c1a  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@_N@1@$$QEAUAppIdentity@BatteryUsageHandlers@SystemSettings@@@Z; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::insert<0,0>(SystemSettings::BatteryUsageHandlers::AppIdentity &&)
0x180043c1f  nop
0x180043c20  lea     rcx, [rbp+57h+var_58]
0x180043c24  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043c29  nop
0x180043c2a  lea     rcx, [rbp+57h+var_70]
0x180043c2e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043c33  nop
0x180043c34  mov     rcx, [rbp+57h+string]; string
0x180043c38  call    cs:__imp_WindowsDeleteString
0x180043c3e  mov     [rbp+57h+string], 0
0x180043c46  lea     rcx, [rbp+57h+var_80]
0x180043c4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043c4f  inc     esi
0x180043c51  jmp     loc_180043B52
0x180043c56  mov     rcx, [rbp+5Fh]; this
0x180043c5a  mov     r9d, eax; char *
0x180043c5d  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043c64  mov     edx, 763h; void *
0x180043c69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043c6e  nop
0x180043c6f  mov     rcx, [rbp+57h+string]; string
0x180043c73  call    cs:__imp_WindowsDeleteString
0x180043c79  mov     [rbp+57h+string], 0
0x180043c81  jmp     short loc_180043C9C
0x180043c83  mov     rcx, [rbp+5Fh]; this
0x180043c87  mov     r9d, eax; char *
0x180043c8a  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043c91  mov     edx, 760h; void *
0x180043c96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043c9b  nop
0x180043c9c  lea     rcx, [rbp+57h+var_80]
0x180043ca0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043ca5  jmp     short loc_180043CA9
0x180043ca7  xor     ebx, ebx
0x180043ca9  lea     rcx, [rbp+57h+var_78]
0x180043cad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043cb2  mov     eax, ebx
0x180043cb4  mov     rcx, [rbp+57h+var_30]
0x180043cb8  xor     rcx, rsp; StackCookie
0x180043cbb  call    __security_check_cookie
0x180043cc0  mov     rbx, [rsp+0B0h+arg_10]
0x180043cc8  add     rsp, 90h
0x180043ccf  pop     r15
0x180043cd1  pop     r14
0x180043cd3  pop     rdi
0x180043cd4  pop     rsi
0x180043cd5  pop     rbp
0x180043cd6  retn
```
