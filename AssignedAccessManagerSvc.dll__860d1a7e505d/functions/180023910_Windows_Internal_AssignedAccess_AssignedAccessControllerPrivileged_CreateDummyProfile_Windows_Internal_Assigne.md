# Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::CreateDummyProfile(Windows::Internal::AssignedAccess::IAssignedAccessProfile * *)

- ea: `0x180023910`
- end: `0x1800239f5`
- name: `?CreateDummyProfile@AssignedAccessControllerPrivileged@AssignedAccess@Internal@Windows@@AEAAJPEAPEAUIAssignedAccessProfile@234@@Z`
- size: `229`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged *__hidden this, struct Windows::Internal::AssignedAccess::IAssignedAccessProfile **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800239fc`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180021f94`
- `0x18002249c`
- `0x180023910`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180023939`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180023939`

## string_xrefs

- `0x18002394d`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`
- `0x1800239ac`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::CreateDummyProfile(
        Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged *this,
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
      v6 = 163;
    }
    else
    {
      v6 = 162;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
      (const char *)(unsigned int)v5,
      v8[0]);
LABEL_9:
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v8);
    return v4;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA0,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
    (const char *)(unsigned int)v3,
    v8[0]);
  return v4;
}

```

## disassembly

```asm
0x180023910  mov     [rsp+arg_0], rbx
0x180023915  push    rdi
0x180023916  sub     rsp, 60h
0x18002391a  mov     rax, cs:__security_cookie
0x180023921  xor     rax, rsp
0x180023924  mov     [rsp+68h+var_18], rax
0x180023929  mov     rdi, rdx
0x18002392c  xorps   xmm0, xmm0
0x18002392f  movups  xmmword ptr [rsp+68h+pguid.Data1], xmm0
0x180023934  lea     rcx, [rsp+68h+pguid]; pguid
0x180023939  call    cs:__imp_CoCreateGuid
0x18002393f  mov     ebx, eax
0x180023941  test    eax, eax
0x180023943  jns     short loc_180023960
0x180023945  mov     rcx, [rsp+68h]; this
0x18002394a  mov     r9d, eax; char *
0x18002394d  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180023954  mov     edx, 0A0h; void *
0x180023959  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002395e  jmp     short loc_1800239DB
0x180023960  mov     qword ptr [rsp+68h+var_48], 0; int
0x180023969  lea     rcx, [rsp+68h+var_48]
0x18002396e  call    ??$MakeAndInitialize@VAssignedAccessProfile@AssignedAccess@Internal@Windows@@UIAssignedAccessProfile@234@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIAssignedAccessProfile@AssignedAccess@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessProfile,Windows::Internal::AssignedAccess::IAssignedAccessProfile,>(Windows::Internal::AssignedAccess::IAssignedAccessProfile * *)
0x180023973  mov     ebx, eax
0x180023975  test    eax, eax
0x180023977  jns     short loc_180023980
0x180023979  mov     edx, 0A2h
0x18002397e  jmp     short loc_1800239AC
0x180023980  mov     rcx, qword ptr [rsp+68h+var_48]
0x180023985  movaps  xmm0, xmmword ptr [rsp+68h+pguid.Data1]
0x18002398a  movdqa  [rsp+68h+var_38], xmm0
0x180023990  mov     rax, [rcx]
0x180023993  lea     rdx, [rsp+68h+var_38]
0x180023998  mov     rax, [rax+40h]
0x18002399c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239a1  mov     ebx, eax
0x1800239a3  test    eax, eax
0x1800239a5  jns     short loc_1800239C2
0x1800239a7  mov     edx, 0A3h; void *
0x1800239ac  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800239b3  mov     r9d, eax; char *
0x1800239b6  mov     rcx, [rsp+68h]; this
0x1800239bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239c0  jmp     short loc_1800239D1
0x1800239c2  mov     rdx, rdi
0x1800239c5  lea     rcx, [rsp+68h+var_48]
0x1800239ca  call    ??$copy_to@UIProfileOperation@AssignedAccess@Internal@Windows@@@?$com_ptr_t@UIProfileOperation@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIProfileOperation@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(Windows::Internal::AssignedAccess::IProfileOperation * *)
0x1800239cf  xor     ebx, ebx
0x1800239d1  lea     rcx, [rsp+68h+var_48]
0x1800239d6  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800239db  mov     eax, ebx
0x1800239dd  mov     rcx, [rsp+68h+var_18]
0x1800239e2  xor     rcx, rsp; StackCookie
0x1800239e5  call    __security_check_cookie
0x1800239ea  mov     rbx, [rsp+68h+arg_0]
0x1800239ef  add     rsp, 60h
0x1800239f3  pop     rdi
0x1800239f4  retn
```
