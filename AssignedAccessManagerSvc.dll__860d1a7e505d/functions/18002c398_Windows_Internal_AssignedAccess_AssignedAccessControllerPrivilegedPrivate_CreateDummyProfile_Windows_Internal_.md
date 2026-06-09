# Windows::Internal::AssignedAccess::AssignedAccessControllerPrivilegedPrivate::CreateDummyProfile(Windows::Internal::AssignedAccess::IAssignedAccessProfile * *)

- ea: `0x18002c398`
- end: `0x18002c47d`
- name: `?CreateDummyProfile@AssignedAccessControllerPrivilegedPrivate@AssignedAccess@Internal@Windows@@AEAAJPEAPEAUIAssignedAccessProfile@234@@Z`
- size: `229`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AssignedAccessControllerPrivilegedPrivate *__hidden this, struct Windows::Internal::AssignedAccess::IAssignedAccessProfile **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002c484`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180021f94`
- `0x18002249c`
- `0x18002c398`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002c3c1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002c3c1`

## string_xrefs

- `0x18002c3d5`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivilegedprivate.cpp`
- `0x18002c434`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivilegedprivate.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessControllerPrivilegedPrivate::CreateDummyProfile(
        Windows::Internal::AssignedAccess::AssignedAccessControllerPrivilegedPrivate *this,
        struct Windows::Internal::AssignedAccess::IAssignedAccessProfile **a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rdx
  int v8[4]; // [rsp+20h] [rbp-48h] BYREF
  GUID v9; // [rsp+30h] [rbp-38h] BYREF
  GUID pguid; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  pguid = 0;
  v3 = CoCreateGuid(&pguid);
  v4 = v3;
  if ( v3 >= 0 )
  {
    *(_QWORD *)v8 = 0;
    v5 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessProfile,Windows::Internal::AssignedAccess::IAssignedAccessProfile,>(v8);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v9 = pguid;
      v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)v8 + 64LL))(*(_QWORD *)v8, &v9);
      v4 = v5;
      if ( v5 >= 0 )
      {
        wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(
          v8,
          a2);
        v4 = 0;
        goto LABEL_9;
      }
      v6 = 93;
    }
    else
    {
      v6 = 92;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivilegedprivate.cpp",
      (const char *)(unsigned int)v5,
      v8[0]);
LABEL_9:
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v8);
    return v4;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5A,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivilegedprivate.cpp",
    (const char *)(unsigned int)v3,
    v8[0]);
  return v4;
}

```

## disassembly

```asm
0x18002c398  mov     [rsp+arg_0], rbx
0x18002c39d  push    rdi
0x18002c39e  sub     rsp, 60h
0x18002c3a2  mov     rax, cs:__security_cookie
0x18002c3a9  xor     rax, rsp
0x18002c3ac  mov     [rsp+68h+var_18], rax
0x18002c3b1  mov     rdi, rdx
0x18002c3b4  xorps   xmm0, xmm0
0x18002c3b7  movups  xmmword ptr [rsp+68h+pguid.Data1], xmm0
0x18002c3bc  lea     rcx, [rsp+68h+pguid]; pguid
0x18002c3c1  call    cs:__imp_CoCreateGuid
0x18002c3c7  mov     ebx, eax
0x18002c3c9  test    eax, eax
0x18002c3cb  jns     short loc_18002C3E8
0x18002c3cd  mov     rcx, [rsp+68h]; this
0x18002c3d2  mov     r9d, eax; char *
0x18002c3d5  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18002c3dc  mov     edx, 5Ah ; 'Z'; void *
0x18002c3e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c3e6  jmp     short loc_18002C463
0x18002c3e8  mov     qword ptr [rsp+68h+var_48], 0; int
0x18002c3f1  lea     rcx, [rsp+68h+var_48]
0x18002c3f6  call    ??$MakeAndInitialize@VAssignedAccessProfile@AssignedAccess@Internal@Windows@@UIAssignedAccessProfile@234@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIAssignedAccessProfile@AssignedAccess@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessProfile,Windows::Internal::AssignedAccess::IAssignedAccessProfile,>(Windows::Internal::AssignedAccess::IAssignedAccessProfile * *)
0x18002c3fb  mov     ebx, eax
0x18002c3fd  test    eax, eax
0x18002c3ff  jns     short loc_18002C408
0x18002c401  mov     edx, 5Ch ; '\'
0x18002c406  jmp     short loc_18002C434
0x18002c408  mov     rcx, qword ptr [rsp+68h+var_48]
0x18002c40d  movaps  xmm0, xmmword ptr [rsp+68h+pguid.Data1]
0x18002c412  movdqa  [rsp+68h+var_38], xmm0
0x18002c418  mov     rax, [rcx]
0x18002c41b  lea     rdx, [rsp+68h+var_38]
0x18002c420  mov     rax, [rax+40h]
0x18002c424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c429  mov     ebx, eax
0x18002c42b  test    eax, eax
0x18002c42d  jns     short loc_18002C44A
0x18002c42f  mov     edx, 5Dh ; ']'; void *
0x18002c434  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18002c43b  mov     r9d, eax; char *
0x18002c43e  mov     rcx, [rsp+68h]; this
0x18002c443  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c448  jmp     short loc_18002C459
0x18002c44a  mov     rdx, rdi
0x18002c44d  lea     rcx, [rsp+68h+var_48]
0x18002c452  call    ??$copy_to@UIProfileOperation@AssignedAccess@Internal@Windows@@@?$com_ptr_t@UIProfileOperation@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIProfileOperation@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(Windows::Internal::AssignedAccess::IProfileOperation * *)
0x18002c457  xor     ebx, ebx
0x18002c459  lea     rcx, [rsp+68h+var_48]
0x18002c45e  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18002c463  mov     eax, ebx
0x18002c465  mov     rcx, [rsp+68h+var_18]
0x18002c46a  xor     rcx, rsp; StackCookie
0x18002c46d  call    __security_check_cookie
0x18002c472  mov     rbx, [rsp+68h+arg_0]
0x18002c477  add     rsp, 60h
0x18002c47b  pop     rdi
0x18002c47c  retn
```
