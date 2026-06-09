# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetAlwaysOnApps(std::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>> *)

- ea: `0x18003f660`
- end: `0x18003f7b1`
- name: `?GetAlwaysOnApps@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJPEAV?$set@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@Z`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800334f0`

## callees

- `0x1800028d0`
- `0x18000a13c`
- `0x180013be0`
- `0x18001e360`
- `0x18001e5c8`
- `0x180038f1c`
- `0x18003d820`
- `0x18003f660`
- `0x18004706c`
- `0x18004834c`
- `0x1800512e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f760`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetAlwaysOnApps(__int64 a1, __int64 *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v8; // rsi
  char v9; // r8
  int v10; // eax
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v11; // rcx
  unsigned int v12; // ebx
  int v13[2]; // [rsp+20h] [rbp-68h] BYREF
  HSTRING string; // [rsp+28h] [rbp-60h] BYREF
  __int64 v15; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v16[16]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v17[32]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v18; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::clear(a2);
  v5 = qword_18007A078;
  v6 = *(_QWORD *)qword_18007A078;
  v15 = *(_QWORD *)qword_18007A078;
  while ( 1 )
  {
    if ( v6 == v5 )
      return 0;
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 32, v3, v4);
    *(_QWORD *)v13 = v8;
    string = 0;
    v10 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
            (Microsoft::WRL::Wrappers::HString *)&string,
            (__int64 *)v13,
            v9);
    v12 = v10;
    if ( v10 < 0 )
      break;
    v13[0] = 0;
    if ( SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBGCapability(
           v11,
           string,
           (enum SystemSettings::BatteryUsageHandlers::BackgroundCapability *)v13) >= 0
      && v13[0] == 3 )
    {
      SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(v17, v8);
      v18 = 1;
      std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::insert<0,0>(
        a2,
        (__int64)v16,
        (__int64)v17);
      std::wstring::_Tidy_deallocate(v17);
    }
    WindowsDeleteString(string);
    string = 0;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>>,std::_Iterator_base0>::operator++(&v15);
    v6 = v15;
    v5 = qword_18007A078;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x781,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
    (const char *)(unsigned int)v10,
    v13[0]);
  WindowsDeleteString(string);
  return v12;
}

```

## disassembly

```asm
0x18003f660  mov     [rsp+arg_0], rbx
0x18003f665  mov     [rsp+arg_10], rsi
0x18003f66a  push    rdi
0x18003f66b  sub     rsp, 80h
0x18003f672  mov     rax, cs:__security_cookie
0x18003f679  xor     rax, rsp
0x18003f67c  mov     [rsp+88h+var_18], rax
0x18003f681  mov     rdi, rdx
0x18003f684  mov     rcx, rdx
0x18003f687  call    ?clear@?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::clear(void)
0x18003f68c  mov     rax, cs:qword_18007A078
0x18003f693  mov     rcx, [rax]
0x18003f696  mov     [rsp+88h+var_58], rcx
0x18003f69b  cmp     rcx, rax
0x18003f69e  jnz     short loc_18003F6A7
0x18003f6a0  xor     eax, eax
0x18003f6a2  jmp     loc_18003F78E
0x18003f6a7  add     rcx, 20h ; ' '
0x18003f6ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f6b0  mov     rsi, rax
0x18003f6b3  mov     qword ptr [rsp+88h+var_68], rax; int
0x18003f6b8  mov     [rsp+88h+string], 0
0x18003f6c1  lea     rdx, [rsp+88h+var_68]
0x18003f6c6  lea     rcx, [rsp+88h+string]
0x18003f6cb  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003f6d0  mov     ebx, eax
0x18003f6d2  test    eax, eax
0x18003f6d4  jns     short loc_18003F705
0x18003f6d6  mov     rcx, [rsp+88h]; this
0x18003f6de  mov     r9d, eax; char *
0x18003f6e1  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003f6e8  mov     edx, 781h; void *
0x18003f6ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f6f2  nop
0x18003f6f3  mov     rcx, [rsp+88h+string]; string
0x18003f6f8  call    cs:__imp_WindowsDeleteString
0x18003f6fe  mov     eax, ebx
0x18003f700  jmp     loc_18003F78E
0x18003f705  mov     [rsp+88h+var_68], 0
0x18003f70d  lea     r8, [rsp+88h+var_68]; enum SystemSettings::BatteryUsageHandlers::BackgroundCapability *
0x18003f712  mov     rdx, [rsp+88h+string]; HSTRING
0x18003f717  call    ?GetAppBGCapability@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@PEAW4BackgroundCapability@23@@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBGCapability(HSTRING__ *,SystemSettings::BatteryUsageHandlers::BackgroundCapability *)
0x18003f71c  test    eax, eax
0x18003f71e  js      short loc_18003F75B
0x18003f720  cmp     [rsp+88h+var_68], 3
0x18003f725  jnz     short loc_18003F75B
0x18003f727  mov     rdx, rsi
0x18003f72a  lea     rcx, [rsp+88h+var_40]
0x18003f72f  call    ?GetPackageFamilyNameFromPackageFullName@BatteryUsageHandlers@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(ushort const *)
0x18003f734  mov     [rsp+88h+var_20], 1
0x18003f73d  lea     r8, [rsp+88h+var_40]
0x18003f742  lea     rdx, [rsp+88h+var_50]
0x18003f747  mov     rcx, rdi
0x18003f74a  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@_N@1@$$QEAUAppIdentity@BatteryUsageHandlers@SystemSettings@@@Z; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::insert<0,0>(SystemSettings::BatteryUsageHandlers::AppIdentity &&)
0x18003f74f  nop
0x18003f750  lea     rcx, [rsp+88h+var_40]
0x18003f755  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f75a  nop
0x18003f75b  mov     rcx, [rsp+88h+string]; string
0x18003f760  call    cs:__imp_WindowsDeleteString
0x18003f766  mov     [rsp+88h+string], 0
0x18003f76f  lea     rcx, [rsp+88h+var_58]
0x18003f774  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>>,std::_Iterator_base0>::operator++(void)
0x18003f779  mov     rcx, [rsp+88h+var_58]
0x18003f77e  mov     rax, cs:qword_18007A078
0x18003f785  jmp     loc_18003F69B
0x18003f78a  mov     eax, [rsp+88h+var_68]
0x18003f78e  mov     rcx, [rsp+88h+var_18]
0x18003f793  xor     rcx, rsp; StackCookie
0x18003f796  call    __security_check_cookie
0x18003f79b  lea     r11, [rsp+88h+var_8]
0x18003f7a3  mov     rbx, [r11+10h]
0x18003f7a7  mov     rsi, [r11+20h]
0x18003f7ab  mov     rsp, r11
0x18003f7ae  pop     rdi
0x18003f7af  retn
```
