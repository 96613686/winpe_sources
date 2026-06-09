# Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::ApplyProfileForAccount(Windows::Internal::AssignedAccess::ApplyOption,Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *> * *)

- ea: `0x180023300`
- end: `0x18002366a`
- name: `?ApplyProfileForAccount@AssignedAccessControllerPrivileged@AssignedAccess@Internal@Windows@@UEAAJW4ApplyOption@234@PEAPEAU?$IVectorView@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@Collections@Foundation@4@@Z`
- size: `874`
- prototype: `__int64 __fastcall(__int64, int, char)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x18000f62c`
- `0x180010c98`
- `0x180013fac`
- `0x18001f2b0`
- `0x18002001c`
- `0x180022d20`
- `0x180023300`
- `0x180023768`
- `0x1800239fc`
- `0x180023e30`
- `0x180024780`
- `0x1800250e8`
- `0x180025998`
- `0x180050980`
- `0x180096010`

## string_xrefs

- `0x18002336c`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`
- `0x1800233b5`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`
- `0x180023426`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`
- `0x1800234a8`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`
- `0x180023523`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`
- `0x18002357b`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`
- `0x1800235dc`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`
- `0x18002332a`: `AAControllerPrivilegedApplyProfileForAccount`

## pseudocode

```c
// audit: low-user activatable ControllerPrivileged; non-admin limited to current config user matching real caller SID, dummy path has no caller-controlled payload.
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::ApplyProfileForAccount(
        __int64 a1,
        int a2,
        char a3)
{
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 v11; // rcx
  int CallerUserSid; // eax
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // rax
  Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged *v15; // rcx
  int v16; // eax
  int v17; // ecx
  unsigned int v18; // ebx
  bool IsUserAdmin; // si
  struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *v20; // rcx
  int TargetUserInfo; // eax
  unsigned int v22; // ebx
  const unsigned __int16 *v23; // rdx
  Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged *v24; // rcx
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  int v29; // [rsp+20h] [rbp-1B8h]
  int v30; // [rsp+20h] [rbp-1B8h]
  struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *v31; // [rsp+30h] [rbp-1A8h] BYREF
  _BYTE v32[40]; // [rsp+38h] [rbp-1A0h] BYREF
  _QWORD v33[42]; // [rsp+60h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v33,
    "AAControllerPrivilegedApplyProfileForAccount");
  v33[0] = &AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::`vftable';
  AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::StartActivity((AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount *)v33);
  v6 = Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::MigrateConfigurationIfNeeded((Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged *)(a1 - 48));
  v9 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
      (const char *)(unsigned int)v6,
      v29);
    AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount((AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount *)v33);
    return v9;
  }
  std::wstring::wstring(v32, v7, v8);
  CallerUserSid = Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::GetCallerUserSid(v11, v32);
  v13 = CallerUserSid;
  if ( CallerUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
      (const char *)(unsigned int)CallerUserSid,
      v29);
    std::wstring::_Tidy_deallocate(v32);
    AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount((AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount *)v33);
    return v13;
  }
  v31 = 0;
  v14 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
  if ( a2 == 2 )
  {
    v31 = 0;
    v16 = Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::CreateDummyUserInfo(v15, v14, &v31);
    v18 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
        (const char *)(unsigned int)v16,
        v29);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v31);
      std::wstring::_Tidy_deallocate(v32);
      AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount((AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount *)v33);
      return v18;
    }
  }
  else
  {
    IsUserAdmin = Windows::Internal::AssignedAccess::UserInfoHelper::IsUserAdmin(v14);
    v20 = v31;
    v31 = 0;
    TargetUserInfo = Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::GetTargetUserInfo(
                       v20,
                       v32,
                       &v31);
    v22 = TargetUserInfo;
    if ( TargetUserInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
        (const char *)(unsigned int)TargetUserInfo,
        v29);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v31);
      std::wstring::_Tidy_deallocate(v32);
      AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount((AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount *)v33);
      return v22;
    }
    if ( IsUserAdmin )
    {
      if ( !v31 )
      {
        v31 = 0;
        v23 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
        v25 = Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::CreateDummyUserInfo(v24, v23, &v31);
        v26 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x37,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
            (const char *)(unsigned int)v25,
            v29);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v31);
          std::wstring::_Tidy_deallocate(v32);
          AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount((AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount *)v33);
          return v26;
        }
        a2 = 2;
      }
    }
    else if ( !v31 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
        (const char *)0x80070057LL,
        v29);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v31);
      std::wstring::_Tidy_deallocate(v32);
      AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount((AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount *)v33);
      return 2147942487LL;
    }
  }
  v27 = Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::BuildAndRunProfileOperationsWithLog(
          v17,
          (unsigned int)v32,
          (_DWORD)v31,
          a2,
          a3);
  v28 = v27;
  if ( v27 >= 0 )
  {
    wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v33);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v31);
    std::wstring::_Tidy_deallocate(v32);
    AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount((AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount *)v33);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
      (const char *)(unsigned int)v27,
      v30);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v31);
    std::wstring::_Tidy_deallocate(v32);
    AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount((AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount *)v33);
    return v28;
  }
}

```

## disassembly

```asm
0x180023300  mov     [rsp+arg_18], rbx; audit: low-user activatable ControllerPrivileged; non-admin limited to current config user matching real caller SID, dummy path has no caller-controlled payload.
0x180023305  push    rsi
0x180023306  push    rdi
0x180023307  push    r14
0x180023309  sub     rsp, 1C0h
0x180023310  mov     rax, cs:__security_cookie
0x180023317  xor     rax, rsp
0x18002331a  mov     [rsp+1D8h+var_28], rax
0x180023322  mov     r14, r8
0x180023325  mov     edi, edx
0x180023327  mov     rbx, rcx
0x18002332a  lea     rdx, aAacontrollerpr; "AAControllerPrivilegedApplyProfileForAc"...
0x180023331  lea     rcx, [rsp+1D8h+var_178]
0x180023336  call    ??0?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002333b  lea     rax, ??_7AAControllerPrivilegedApplyProfileForAccount@AssignedAccessTelemetry@@6B@; const AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::`vftable'
0x180023342  mov     [rsp+1D8h+var_178], rax
0x180023347  lea     rcx, [rsp+1D8h+var_178]; this
0x18002334c  call    ?StartActivity@AAControllerPrivilegedApplyProfileForAccount@AssignedAccessTelemetry@@QEAAXXZ; AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::StartActivity(void)
0x180023351  nop
0x180023352  lea     rcx, [rbx-30h]; this
0x180023356  call    ?MigrateConfigurationIfNeeded@AssignedAccessControllerPrivileged@AssignedAccess@Internal@Windows@@AEAAJXZ; Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::MigrateConfigurationIfNeeded(void)
0x18002335b  mov     ebx, eax
0x18002335d  test    eax, eax
0x18002335f  jns     short loc_18002338F
0x180023361  mov     rcx, [rsp+1D8h]; this
0x180023369  mov     r9d, eax; char *
0x18002336c  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180023373  mov     edx, 28h ; '('; void *
0x180023378  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002337d  nop
0x18002337e  lea     rcx, [rsp+1D8h+var_178]; this
0x180023383  call    ??1AAControllerPrivilegedApplyProfileForAccount@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount(void)
0x180023388  mov     eax, ebx
0x18002338a  jmp     loc_180023645
0x18002338f  lea     rcx, [rsp+1D8h+var_1A0]
0x180023394  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180023399  nop
0x18002339a  lea     rdx, [rsp+1D8h+var_1A0]
0x18002339f  call    ?GetCallerUserSid@AssignedAccessControllerPrivileged@AssignedAccess@Internal@Windows@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; audit: GetCallerUserSid uses IServerSecurity impersonation + OpenThreadToken; real caller SID gate for low-user reachable ControllerPrivileged.
0x1800233a4  mov     ebx, eax
0x1800233a6  test    eax, eax
0x1800233a8  jns     short loc_1800233E3
0x1800233aa  mov     rcx, [rsp+1D8h]; this
0x1800233b2  mov     r9d, eax; char *
0x1800233b5  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800233bc  mov     edx, 2Ah ; '*'; void *
0x1800233c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800233c6  nop
0x1800233c7  lea     rcx, [rsp+1D8h+var_1A0]
0x1800233cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800233d1  nop
0x1800233d2  lea     rcx, [rsp+1D8h+var_178]; this
0x1800233d7  call    ??1AAControllerPrivilegedApplyProfileForAccount@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount(void)
0x1800233dc  mov     eax, ebx
0x1800233de  jmp     loc_180023645
0x1800233e3  mov     [rsp+1D8h+var_1A8], 0
0x1800233ec  lea     rcx, [rsp+1D8h+var_1A0]
0x1800233f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800233f6  cmp     edi, 2
0x1800233f9  jnz     short loc_18002345D
0x1800233fb  mov     [rsp+1D8h+var_1A8], 0
0x180023404  lea     r8, [rsp+1D8h+var_1A8]; struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo **
0x180023409  mov     rdx, rax; unsigned __int16 *
0x18002340c  call    ?CreateDummyUserInfo@AssignedAccessControllerPrivileged@AssignedAccess@Internal@Windows@@AEAAJPEBGPEAPEAUIAssignedAccessUserInfo@234@@Z; Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::CreateDummyUserInfo(ushort const *,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo * *)
0x180023411  mov     ebx, eax
0x180023413  test    eax, eax
0x180023415  jns     loc_1800235B4
0x18002341b  mov     rcx, [rsp+1D8h]; this
0x180023423  mov     r9d, eax; char *
0x180023426  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18002342d  lea     edx, [rdi+2Ch]; void *
0x180023430  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023435  nop
0x180023436  lea     rcx, [rsp+1D8h+var_1A8]
0x18002343b  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180023440  nop
0x180023441  lea     rcx, [rsp+1D8h+var_1A0]
0x180023446  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002344b  nop
0x18002344c  lea     rcx, [rsp+1D8h+var_178]; this
0x180023451  call    ??1AAControllerPrivilegedApplyProfileForAccount@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount(void)
0x180023456  mov     eax, ebx
0x180023458  jmp     loc_180023645
0x18002345d  mov     rcx, rax; unsigned __int16 *
0x180023460  call    ?IsUserAdmin@UserInfoHelper@AssignedAccess@Internal@Windows@@SA_NPEBG@Z; Windows::Internal::AssignedAccess::UserInfoHelper::IsUserAdmin(ushort const *)
0x180023465  mov     sil, al
0x180023468  mov     rcx, [rsp+1D8h+var_1A8]
0x18002346d  mov     [rsp+1D8h+var_1A8], 0
0x180023476  test    rcx, rcx
0x180023479  jz      short loc_180023488
0x18002347b  mov     rdx, [rcx]
0x18002347e  mov     rax, [rdx+10h]
0x180023482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023487  nop
0x180023488  lea     r8, [rsp+1D8h+var_1A8]
0x18002348d  lea     rdx, [rsp+1D8h+var_1A0]
0x180023492  call    ?GetTargetUserInfo@AssignedAccessControllerPrivileged@AssignedAccess@Internal@Windows@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAssignedAccessUserInfo@234@@Z; Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::GetTargetUserInfo(std::wstring const &,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo * *)
0x180023497  mov     ebx, eax
0x180023499  test    eax, eax
0x18002349b  jns     short loc_1800234E1
0x18002349d  mov     rcx, [rsp+1D8h]; this
0x1800234a5  mov     r9d, eax; char *
0x1800234a8  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800234af  mov     edx, 33h ; '3'; void *
0x1800234b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800234b9  nop
0x1800234ba  lea     rcx, [rsp+1D8h+var_1A8]
0x1800234bf  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800234c4  nop
0x1800234c5  lea     rcx, [rsp+1D8h+var_1A0]
0x1800234ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800234cf  nop
0x1800234d0  lea     rcx, [rsp+1D8h+var_178]; this
0x1800234d5  call    ??1AAControllerPrivilegedApplyProfileForAccount@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount(void)
0x1800234da  mov     eax, ebx
0x1800234dc  jmp     loc_180023645
0x1800234e1  test    sil, sil
0x1800234e4  jz      short loc_180023563
0x1800234e6  cmp     [rsp+1D8h+var_1A8], 0
0x1800234ec  jnz     loc_1800235B4
0x1800234f2  mov     [rsp+1D8h+var_1A8], 0
0x1800234fb  lea     rcx, [rsp+1D8h+var_1A0]
0x180023500  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180023505  mov     rdx, rax; unsigned __int16 *
0x180023508  lea     r8, [rsp+1D8h+var_1A8]; struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo **
0x18002350d  call    ?CreateDummyUserInfo@AssignedAccessControllerPrivileged@AssignedAccess@Internal@Windows@@AEAAJPEBGPEAPEAUIAssignedAccessUserInfo@234@@Z; Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::CreateDummyUserInfo(ushort const *,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo * *)
0x180023512  mov     ebx, eax
0x180023514  test    eax, eax
0x180023516  jns     short loc_18002355C
0x180023518  mov     rcx, [rsp+1D8h]; this
0x180023520  mov     r9d, eax; char *
0x180023523  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18002352a  mov     edx, 37h ; '7'; void *
0x18002352f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023534  nop
0x180023535  lea     rcx, [rsp+1D8h+var_1A8]
0x18002353a  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18002353f  nop
0x180023540  lea     rcx, [rsp+1D8h+var_1A0]
0x180023545  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002354a  nop
0x18002354b  lea     rcx, [rsp+1D8h+var_178]; this
0x180023550  call    ??1AAControllerPrivilegedApplyProfileForAccount@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount(void)
0x180023555  mov     eax, ebx
0x180023557  jmp     loc_180023645
0x18002355c  mov     edi, 2
0x180023561  jmp     short loc_1800235B4
0x180023563  cmp     [rsp+1D8h+var_1A8], 0
0x180023569  jnz     short loc_1800235B4
0x18002356b  mov     rcx, [rsp+1D8h]; this
0x180023573  mov     ebx, 80070057h
0x180023578  mov     r9d, ebx; char *
0x18002357b  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180023582  mov     edx, 3Bh ; ';'; void *
0x180023587  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002358c  nop
0x18002358d  lea     rcx, [rsp+1D8h+var_1A8]
0x180023592  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180023597  nop
0x180023598  lea     rcx, [rsp+1D8h+var_1A0]
0x18002359d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800235a2  nop
0x1800235a3  lea     rcx, [rsp+1D8h+var_178]; this
0x1800235a8  call    ??1AAControllerPrivilegedApplyProfileForAccount@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount(void)
0x1800235ad  mov     eax, ebx
0x1800235af  jmp     loc_180023645
0x1800235b4  mov     qword ptr [rsp+1D8h+var_1B8], r14; int
0x1800235b9  mov     r9d, edi
0x1800235bc  mov     r8, [rsp+1D8h+var_1A8]
0x1800235c1  lea     rdx, [rsp+1D8h+var_1A0]
0x1800235c6  call    ?BuildAndRunProfileOperationsWithLog@AssignedAccessControllerPrivileged@AssignedAccess@Internal@Windows@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIAssignedAccessUserInfo@234@W4ApplyOption@234@PEAPEAU?$IVectorView@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@Collections@Foundation@4@@Z; Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::BuildAndRunProfileOperationsWithLog(std::wstring const &,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *,Windows::Internal::AssignedAccess::ApplyOption,Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *> * *)
0x1800235cb  mov     ebx, eax
0x1800235cd  test    eax, eax
0x1800235cf  jns     short loc_180023612
0x1800235d1  mov     rcx, [rsp+1D8h]; this
0x1800235d9  mov     r9d, eax; char *
0x1800235dc  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800235e3  mov     edx, 3Fh ; '?'; void *
0x1800235e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800235ed  nop
0x1800235ee  lea     rcx, [rsp+1D8h+var_1A8]
0x1800235f3  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800235f8  nop
0x1800235f9  lea     rcx, [rsp+1D8h+var_1A0]
0x1800235fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023603  nop
0x180023604  lea     rcx, [rsp+1D8h+var_178]; this
0x180023609  call    ??1AAControllerPrivilegedApplyProfileForAccount@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount(void)
0x18002360e  mov     eax, ebx
0x180023610  jmp     short loc_180023645
0x180023612  lea     rcx, [rsp+1D8h+var_178]
0x180023617  call    ?Stop@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002361c  nop
0x18002361d  lea     rcx, [rsp+1D8h+var_1A8]
0x180023622  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180023627  nop
0x180023628  lea     rcx, [rsp+1D8h+var_1A0]
0x18002362d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023632  nop
0x180023633  lea     rcx, [rsp+1D8h+var_178]; this
0x180023638  call    ??1AAControllerPrivilegedApplyProfileForAccount@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AAControllerPrivilegedApplyProfileForAccount::~AAControllerPrivilegedApplyProfileForAccount(void)
0x18002363d  xor     eax, eax
0x18002363f  jmp     short loc_180023645
0x180023641  mov     eax, dword ptr [rsp+1D8h+var_1A8]
0x180023645  mov     rcx, [rsp+1D8h+var_28]
0x18002364d  xor     rcx, rsp; StackCookie
0x180023650  call    __security_check_cookie
0x180023655  mov     rbx, [rsp+1D8h+arg_18]
0x18002365d  add     rsp, 1C0h
0x180023664  pop     r14
0x180023666  pop     rdi
0x180023667  pop     rsi
0x180023668  retn
```
