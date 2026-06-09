# Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory::CreateProfileBuilder(Windows::Internal::AssignedAccess::ApplyOption,Windows::Internal::AssignedAccess::DefinitionVersion,Windows::Internal::AssignedAccess::IProfileOperationBuilder * *)

- ea: `0x1800331e0`
- end: `0x180033682`
- name: `?CreateProfileBuilder@DeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEAAJW4ApplyOption@234@W4DefinitionVersion@234@PEAPEAUIProfileOperationBuilder@234@@Z`
- size: `1186`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180032c60`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010c98`
- `0x180027190`
- `0x18002cf18`
- `0x18002d8a4`
- `0x18002e19c`
- `0x18002fd4c`
- `0x18002fe34`
- `0x1800305a4`
- `0x1800306d4`
- `0x180030cf0`
- `0x180030e14`
- `0x180031000`
- `0x18003165c`
- `0x18003175c`
- `0x1800331e0`
- `0x180033f8c`
- `0x180096010`

## string_xrefs

- `0x180033234`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033287`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x1800332c6`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x1800333fe`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x18003343b`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033592`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x18003360d`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory::CreateProfileBuilder(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int64 a4)
{
  int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  struct Windows::Internal::AssignedAccess::IProfileOperation *v10; // rdi
  Windows::Internal::AssignedAccess::CompositeOperation *v11; // rbx
  int v12; // edi
  __int64 v13; // rdx
  int v14; // r14d
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  char v18; // al
  struct Windows::Internal::AssignedAccess::IProfileOperation *v19; // rdi
  int v20; // eax
  int v21; // esi
  int v22; // eax
  int v24; // [rsp+20h] [rbp-59h]
  bool v25[8]; // [rsp+30h] [rbp-49h] BYREF
  struct Windows::Internal::AssignedAccess::IProfileOperation *v26; // [rsp+38h] [rbp-41h] BYREF
  int v27; // [rsp+40h] [rbp-39h] BYREF
  Windows::Internal::AssignedAccess::CompositeOperation *v28; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v30[2]; // [rsp+58h] [rbp-21h] BYREF
  int v31[8]; // [rsp+68h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v29 = a2;
  v27 = a3;
  v28 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::CompositeOperationBuilder,Windows::Internal::AssignedAccess::CompositeOperationBuilder,>(&v28);
  v9 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x241,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v7,
      v24);
    goto LABEL_59;
  }
  v10 = 0;
  v26 = 0;
  v11 = v28;
  if ( *(_BYTE *)(a1 + 17) )
  {
    v26 = 0;
    v24 = a1 + 22;
    v12 = Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory::CreateConfigurationModeBuilder<Windows::Internal::AssignedAccess::MultiAppDeviceConfigurationOperationBuilderFactory,enum Windows::Internal::AssignedAccess::DefinitionVersion const &,unsigned char &>(
            v8,
            &v26,
            a2,
            &v27);
    if ( v12 < 0 )
    {
      v13 = 583;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v12,
        v24);
LABEL_7:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v26);
      v9 = v12;
      goto LABEL_59;
    }
    v10 = v26;
    v14 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v11, v26);
    if ( v14 < 0 )
    {
      v15 = 584;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v14,
        v24);
LABEL_11:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v26);
      v9 = v14;
      goto LABEL_59;
    }
  }
  if ( *(_BYTE *)(a1 + 18) && !*(_BYTE *)(a1 + 19) )
  {
    v30[0] = *(_QWORD *)(a1 + 248);
    v26 = 0;
    if ( v10 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v10 + 16LL))(v10);
    v24 = a1 + 152;
    v12 = Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory::CreateConfigurationModeBuilder<Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory,enum Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring &,Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *>(
            v30,
            &v26,
            a2,
            &v27);
    if ( v12 < 0 )
    {
      v13 = 592;
      goto LABEL_6;
    }
    v10 = v26;
    v14 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v11, v26);
    if ( v14 < 0 )
    {
      v15 = 593;
      goto LABEL_10;
    }
  }
  Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory::GetLocalGroupPolicyUserConfigurationTargetSid(
    a1,
    v31);
  if ( *(_BYTE *)(a1 + 20) )
  {
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<unsigned short const (&)[35]>(
      a1 + 24,
      v30);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<unsigned short const (&)[34]>(
      a1 + 24,
      v30);
    v25[0] = a2 == 2;
    v26 = 0;
    if ( v10 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v10 + 16LL))(v10);
    v12 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::BrowserDownloadManagerLockdownOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool,enum Windows::Internal::AssignedAccess::DefinitionVersion const &,std::unordered_set<std::wstring> &,std::wstring &,std::unordered_set<std::wstring> &>(
            (unsigned int)&v26,
            (unsigned int)v25,
            (unsigned int)&v27,
            (int)a1 + 24,
            (__int64)v31,
            a1 + 88);
    if ( v12 < 0 )
    {
      v16 = 603;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v12,
        v24);
      std::wstring::_Tidy_deallocate(v31);
      goto LABEL_7;
    }
    v10 = v26;
    v14 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v11, v26);
    if ( v14 < 0 )
    {
      v17 = 604;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v14,
        v24);
      std::wstring::_Tidy_deallocate(v31);
      goto LABEL_11;
    }
  }
  if ( *(_BYTE *)(a1 + 21) )
  {
    v25[0] = a2 == 2;
    v26 = 0;
    if ( v10 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v10 + 16LL))(v10);
    v12 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::FileExplorerLockdownOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool,enum Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring &>(
            &v26,
            v25,
            &v27,
            v31);
    if ( v12 < 0 )
    {
      v16 = 609;
      goto LABEL_25;
    }
    v10 = v26;
    v14 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v11, v26);
    if ( v14 < 0 )
    {
      v17 = 610;
      goto LABEL_28;
    }
  }
  v18 = 1;
  if ( *(_BYTE *)(a1 + 16) && a2 == 1 )
  {
    v25[0] = 1;
    v26 = 0;
    if ( v10 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v10 + 16LL))(v10);
    v12 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::KeyboardFilteringOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(
            &v26,
            v25);
    if ( v12 < 0 )
    {
      v16 = 618;
      goto LABEL_25;
    }
    v10 = v26;
    v14 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v11, v26);
    if ( v14 < 0 )
    {
      v17 = 619;
      goto LABEL_28;
    }
  }
  else if ( a2 == 2 )
  {
    goto LABEL_46;
  }
  v18 = 0;
LABEL_46:
  v25[0] = v18;
  v26 = 0;
  if ( v10 )
    (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v10 + 16LL))(v10);
  v12 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::ConfigurationOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool,std::wstring &>(
          &v26,
          v25,
          a1 + 216);
  if ( v12 < 0 )
  {
    v16 = 623;
    goto LABEL_25;
  }
  v19 = v26;
  v20 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v11, v26);
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v20,
      v24);
    std::wstring::_Tidy_deallocate(v31);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v26);
    v9 = v21;
    goto LABEL_59;
  }
  v26 = 0;
  if ( v19 )
    (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v19 + 16LL))(v19);
  v12 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::LocalGroupPolicySnapshotMaintenanceOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,enum Windows::Internal::AssignedAccess::ApplyOption &>(
          &v26,
          &v29);
  if ( v12 < 0 )
  {
    v16 = 626;
    goto LABEL_25;
  }
  v22 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v11, v26);
  v9 = v22;
  if ( v22 >= 0 )
  {
    wil::com_ptr_t<Windows::Internal::AssignedAccess::MDMPolicyOperationBuilder,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperationBuilder>(
      &v28,
      a4);
    std::wstring::_Tidy_deallocate(v31);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v26);
    v9 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x273,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v22,
      v24);
    std::wstring::_Tidy_deallocate(v31);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v26);
  }
LABEL_59:
  wil::com_ptr_t<Windows::Internal::AssignedAccess::RegistryKeyOperation,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::AssignedAccess::RegistryKeyOperation,wil::err_exception_policy>(&v28);
  return v9;
}

```

## disassembly

```asm
0x1800331e0  push    rbp
0x1800331e2  push    rbx
0x1800331e3  push    rsi
0x1800331e4  push    rdi
0x1800331e5  push    r12
0x1800331e7  push    r13
0x1800331e9  push    r14
0x1800331eb  push    r15
0x1800331ed  lea     rbp, [rsp-1Fh]
0x1800331f2  sub     rsp, 98h
0x1800331f9  mov     rax, cs:__security_cookie
0x180033200  xor     rax, rsp
0x180033203  mov     [rbp+57h+var_48], rax
0x180033207  mov     r12, r9
0x18003320a  mov     r15d, edx
0x18003320d  mov     rsi, rcx
0x180033210  mov     [rbp+57h+var_80], edx
0x180033213  mov     [rbp+57h+var_90], r8d
0x180033217  xor     r13d, r13d
0x18003321a  mov     [rbp+57h+var_88], r13
0x18003321e  lea     rcx, [rbp+57h+var_88]
0x180033222  call    ??$MakeAndInitialize@VCompositeOperationBuilder@AssignedAccess@Internal@Windows@@V1234@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompositeOperationBuilder@AssignedAccess@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::CompositeOperationBuilder,Windows::Internal::AssignedAccess::CompositeOperationBuilder,>(Windows::Internal::AssignedAccess::CompositeOperationBuilder * *)
0x180033227  mov     ebx, eax
0x180033229  test    eax, eax
0x18003322b  jns     short loc_18003324A
0x18003322d  mov     rcx, [rbp+5Fh]; this
0x180033231  mov     r9d, eax; char *
0x180033234  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18003323b  mov     edx, 241h; void *
0x180033240  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033245  jmp     loc_180033657
0x18003324a  mov     rdi, r13
0x18003324d  mov     [rbp+57h+var_98], r13
0x180033251  mov     rbx, [rbp+57h+var_88]
0x180033255  cmp     [rsi+11h], r13b
0x180033259  jz      loc_1800332EB
0x18003325f  mov     [rbp+57h+var_98], r13
0x180033263  lea     rax, [rsi+16h]
0x180033267  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18003326c  lea     r9, [rbp+57h+var_90]
0x180033270  mov     r8d, r15d
0x180033273  lea     rdx, [rbp+57h+var_98]
0x180033277  call    ??$CreateConfigurationModeBuilder@VMultiAppDeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEBW4DefinitionVersion@234@AEAE@DeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEAAJPEAPEAUIProfileOperationBuilder@123@W4ApplyOption@123@AEBW4DefinitionVersion@123@AEAE@Z; Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory::CreateConfigurationModeBuilder<Windows::Internal::AssignedAccess::MultiAppDeviceConfigurationOperationBuilderFactory,Windows::Internal::AssignedAccess::DefinitionVersion const &,uchar &>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,Windows::Internal::AssignedAccess::ApplyOption,Windows::Internal::AssignedAccess::DefinitionVersion const &,uchar &)
0x18003327c  mov     edi, eax
0x18003327e  test    eax, eax
0x180033280  jns     short loc_1800332AB
0x180033282  mov     edx, 247h; void *
0x180033287  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18003328e  mov     r9d, edi; char *
0x180033291  mov     rcx, [rbp+5Fh]; this
0x180033295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003329a  nop
0x18003329b  lea     rcx, [rbp+57h+var_98]
0x18003329f  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800332a4  mov     ebx, edi
0x1800332a6  jmp     loc_180033657
0x1800332ab  mov     rdi, [rbp+57h+var_98]
0x1800332af  mov     rdx, rdi; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x1800332b2  mov     rcx, rbx; this
0x1800332b5  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x1800332ba  mov     r14d, eax
0x1800332bd  test    eax, eax
0x1800332bf  jns     short loc_1800332EB
0x1800332c1  mov     edx, 248h; void *
0x1800332c6  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800332cd  mov     r9d, r14d; char *
0x1800332d0  mov     rcx, [rbp+5Fh]; this
0x1800332d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800332d9  nop
0x1800332da  lea     rcx, [rbp+57h+var_98]
0x1800332de  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800332e3  mov     ebx, r14d
0x1800332e6  jmp     loc_180033657
0x1800332eb  cmp     [rsi+12h], r13b
0x1800332ef  jz      short loc_180033370
0x1800332f1  cmp     [rsi+13h], r13b
0x1800332f5  jnz     short loc_180033370
0x1800332f7  mov     rax, [rsi+0F8h]
0x1800332fe  mov     [rbp+57h+var_78], rax
0x180033302  mov     [rbp+57h+var_98], r13
0x180033306  test    rdi, rdi
0x180033309  jz      short loc_18003331B
0x18003330b  mov     rax, [rdi]
0x18003330e  mov     rcx, rdi
0x180033311  mov     rax, [rax+10h]
0x180033315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003331a  nop
0x18003331b  lea     rax, [rsi+98h]
0x180033322  lea     rcx, [rbp+57h+var_78]
0x180033326  mov     [rsp+0D0h+var_A8], rcx
0x18003332b  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180033330  lea     r9, [rbp+57h+var_90]
0x180033334  mov     r8d, r15d
0x180033337  lea     rdx, [rbp+57h+var_98]
0x18003333b  call    ??$CreateConfigurationModeBuilder@VSingleAppDeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEBW4DefinitionVersion@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIAssignedAccessConfiguration@234@@DeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEAAJPEAPEAUIProfileOperationBuilder@123@W4ApplyOption@123@AEBW4DefinitionVersion@123@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEAPEAUIAssignedAccessConfiguration@123@@Z; Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory::CreateConfigurationModeBuilder<Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory,Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring &,Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,Windows::Internal::AssignedAccess::ApplyOption,Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring &,Windows::Internal::AssignedAccess::IAssignedAccessConfiguration * &&)
0x180033340  mov     edi, eax
0x180033342  test    eax, eax
0x180033344  jns     short loc_180033350
0x180033346  mov     edx, 250h
0x18003334b  jmp     loc_180033287
0x180033350  mov     rdi, [rbp+57h+var_98]
0x180033354  mov     rdx, rdi; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180033357  mov     rcx, rbx; this
0x18003335a  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x18003335f  mov     r14d, eax
0x180033362  test    eax, eax
0x180033364  jns     short loc_180033370
0x180033366  mov     edx, 251h
0x18003336b  jmp     loc_1800332C6
0x180033370  lea     rdx, [rbp+57h+var_68]
0x180033374  mov     rcx, rsi
0x180033377  call    ?GetLocalGroupPolicyUserConfigurationTargetSid@DeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::AssignedAccess::DeviceConfigurationOperationBuilderFactory::GetLocalGroupPolicyUserConfigurationTargetSid(void)
0x18003337c  nop
0x18003337d  cmp     [rsi+14h], r13b
0x180033381  jz      loc_180033456
0x180033387  lea     r14, [rsi+18h]
0x18003338b  lea     rdx, [rbp+57h+var_78]
0x18003338f  mov     rcx, r14
0x180033392  call    ??$emplace@AEAY0CD@$$CBG@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAY0CD@$$CBG@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<ushort const (&)[35]>(ushort const (&)[35])
0x180033397  lea     rdx, [rbp+57h+var_78]
0x18003339b  mov     rcx, r14
0x18003339e  call    ??$emplace@AEAY0CC@$$CBG@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAY0CC@$$CBG@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<ushort const (&)[34]>(ushort const (&)[34])
0x1800333a3  cmp     r15d, 2
0x1800333a7  setz    al
0x1800333aa  mov     [rbp+57h+var_A0], al
0x1800333ad  mov     [rbp+57h+var_98], r13
0x1800333b1  test    rdi, rdi
0x1800333b4  jz      short loc_1800333C6
0x1800333b6  mov     rax, [rdi]
0x1800333b9  mov     rcx, rdi
0x1800333bc  mov     rax, [rax+10h]
0x1800333c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333c5  nop
0x1800333c6  lea     rax, [rsi+58h]
0x1800333ca  mov     [rsp+0D0h+var_A8], rax
0x1800333cf  lea     rax, [rbp+57h+var_68]
0x1800333d3  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800333d8  mov     r9, r14
0x1800333db  lea     r8, [rbp+57h+var_90]
0x1800333df  lea     rdx, [rbp+57h+var_A0]
0x1800333e3  lea     rcx, [rbp+57h+var_98]
0x1800333e7  call    ??$MakeAndInitialize@VBrowserDownloadManagerLockdownOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_NAEBW4DefinitionVersion@234@AEAV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@8@AEAV78@@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_NAEBW4DefinitionVersion@456@AEAV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@9@3@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::BrowserDownloadManagerLockdownOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool,Windows::Internal::AssignedAccess::DefinitionVersion const &,std::unordered_set<std::wstring> &,std::wstring &,std::unordered_set<std::wstring> &>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&,Windows::Internal::AssignedAccess::DefinitionVersion const &,std::unordered_set<std::wstring> &,std::wstring &,std::unordered_set<std::wstring> &)
0x1800333ec  mov     edi, eax
0x1800333ee  test    eax, eax
0x1800333f0  jns     short loc_180033419
0x1800333f2  mov     edx, 25Bh; void *
0x1800333f7  mov     rcx, [rbp+5Fh]; this
0x1800333fb  mov     r9d, edi; char *
0x1800333fe  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033405  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003340a  nop
0x18003340b  lea     rcx, [rbp+57h+var_68]
0x18003340f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033414  jmp     loc_18003329B
0x180033419  mov     rdi, [rbp+57h+var_98]
0x18003341d  mov     rdx, rdi; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180033420  mov     rcx, rbx; this
0x180033423  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180033428  mov     r14d, eax
0x18003342b  test    eax, eax
0x18003342d  jns     short loc_180033456
0x18003342f  mov     edx, 25Ch; void *
0x180033434  mov     rcx, [rbp+5Fh]; this
0x180033438  mov     r9d, r14d; char *
0x18003343b  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033447  nop
0x180033448  lea     rcx, [rbp+57h+var_68]
0x18003344c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033451  jmp     loc_1800332DA
0x180033456  cmp     [rsi+15h], r13b
0x18003345a  jz      short loc_1800334C4
0x18003345c  cmp     r15d, 2
0x180033460  setz    al
0x180033463  mov     [rbp+57h+var_A0], al
0x180033466  mov     [rbp+57h+var_98], r13
0x18003346a  test    rdi, rdi
0x18003346d  jz      short loc_18003347F
0x18003346f  mov     rax, [rdi]
0x180033472  mov     rcx, rdi
0x180033475  mov     rax, [rax+10h]
0x180033479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003347e  nop
0x18003347f  lea     r9, [rbp+57h+var_68]
0x180033483  lea     r8, [rbp+57h+var_90]
0x180033487  lea     rdx, [rbp+57h+var_A0]
0x18003348b  lea     rcx, [rbp+57h+var_98]
0x18003348f  call    ??$MakeAndInitialize@VFileExplorerLockdownOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_NAEBW4DefinitionVersion@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_NAEBW4DefinitionVersion@456@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::FileExplorerLockdownOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool,Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring &>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&,Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring &)
0x180033494  mov     edi, eax
0x180033496  test    eax, eax
0x180033498  jns     short loc_1800334A4
0x18003349a  mov     edx, 261h
0x18003349f  jmp     loc_1800333F7
0x1800334a4  mov     rdi, [rbp+57h+var_98]
0x1800334a8  mov     rdx, rdi; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x1800334ab  mov     rcx, rbx; this
0x1800334ae  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x1800334b3  mov     r14d, eax
0x1800334b6  test    eax, eax
0x1800334b8  jns     short loc_1800334C4
0x1800334ba  mov     edx, 262h
0x1800334bf  jmp     loc_180033434
0x1800334c4  mov     eax, 1
0x1800334c9  cmp     [rsi+10h], r13b
0x1800334cd  jz      short loc_18003352D
0x1800334cf  cmp     r15d, eax
0x1800334d2  jnz     short loc_18003352D
0x1800334d4  mov     [rbp+57h+var_A0], al
0x1800334d7  mov     [rbp+57h+var_98], r13
0x1800334db  test    rdi, rdi
0x1800334de  jz      short loc_1800334F0
0x1800334e0  mov     rax, [rdi]
0x1800334e3  mov     rcx, rdi
0x1800334e6  mov     rax, [rax+10h]
0x1800334ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334ef  nop
0x1800334f0  lea     rdx, [rbp+57h+var_A0]
0x1800334f4  lea     rcx, [rbp+57h+var_98]
0x1800334f8  call    ??$MakeAndInitialize@VKeyboardFilteringOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_N@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::KeyboardFilteringOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&)
0x1800334fd  mov     edi, eax
0x1800334ff  test    eax, eax
0x180033501  jns     short loc_18003350D
0x180033503  mov     edx, 26Ah
0x180033508  jmp     loc_1800333F7
0x18003350d  mov     rdi, [rbp+57h+var_98]
0x180033511  mov     rdx, rdi; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180033514  mov     rcx, rbx; this
0x180033517  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x18003351c  mov     r14d, eax
0x18003351f  test    eax, eax
0x180033521  jns     short loc_180033533
0x180033523  mov     edx, 26Bh
0x180033528  jmp     loc_180033434
0x18003352d  cmp     r15d, 2
0x180033531  jz      short loc_180033536
0x180033533  mov     al, r13b
0x180033536  mov     [rbp+57h+var_A0], al
0x180033539  mov     [rbp+57h+var_98], r13
0x18003353d  test    rdi, rdi
0x180033540  jz      short loc_180033552
0x180033542  mov     rax, [rdi]
0x180033545  mov     rcx, rdi
0x180033548  mov     rax, [rax+10h]
0x18003354c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033551  nop
0x180033552  lea     r8, [rsi+0D8h]
0x180033559  lea     rdx, [rbp+57h+var_A0]
0x18003355d  lea     rcx, [rbp+57h+var_98]
0x180033561  call    ??$MakeAndInitialize@VConfigurationOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::ConfigurationOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool,std::wstring &>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&,std::wstring &)
0x180033566  mov     edi, eax
0x180033568  test    eax, eax
0x18003356a  jns     short loc_180033576
0x18003356c  mov     edx, 26Fh
0x180033571  jmp     loc_1800333F7
0x180033576  mov     rdi, [rbp+57h+var_98]
0x18003357a  mov     rdx, rdi; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x18003357d  mov     rcx, rbx; this
0x180033580  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180033585  mov     esi, eax
0x180033587  test    eax, eax
0x180033589  jns     short loc_1800335BE
0x18003358b  mov     rcx, [rbp+5Fh]; this
0x18003358f  mov     r9d, eax; char *
0x180033592  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033599  mov     edx, 270h; void *
0x18003359e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800335a3  nop
0x1800335a4  lea     rcx, [rbp+57h+var_68]
0x1800335a8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800335ad  nop
0x1800335ae  lea     rcx, [rbp+57h+var_98]
0x1800335b2  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800335b7  mov     ebx, esi
0x1800335b9  jmp     loc_180033657
0x1800335be  mov     [rbp+57h+var_98], r13
0x1800335c2  test    rdi, rdi
0x1800335c5  jz      short loc_1800335D7
0x1800335c7  mov     rax, [rdi]
0x1800335ca  mov     rcx, rdi
0x1800335cd  mov     rax, [rax+10h]
0x1800335d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335d6  nop
0x1800335d7  lea     rdx, [rbp+57h+var_80]
0x1800335db  lea     rcx, [rbp+57h+var_98]
0x1800335df  call    ??$MakeAndInitialize@VLocalGroupPolicySnapshotMaintenanceOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@AEAW4ApplyOption@234@@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@AEAW4ApplyOption@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::LocalGroupPolicySnapshotMaintenanceOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,Windows::Internal::AssignedAccess::ApplyOption &>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,Windows::Internal::AssignedAccess::ApplyOption &)
0x1800335e4  mov     edi, eax
0x1800335e6  test    eax, eax
0x1800335e8  jns     short loc_1800335F4
0x1800335ea  mov     edx, 272h
0x1800335ef  jmp     loc_1800333F7
0x1800335f4  mov     rdx, [rbp+57h+var_98]; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x1800335f8  mov     rcx, rbx; this
0x1800335fb  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180033600  mov     ebx, eax
0x180033602  test    eax, eax
0x180033604  jns     short loc_180033634
0x180033606  mov     rcx, [rbp+5Fh]; this
0x18003360a  mov     r9d, eax; char *
0x18003360d  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033614  mov     edx, 273h; void *
  ... truncated ...
```
