# BackgroundTaskHandler::LaunchBackGroundTask(_GUID const *,void *,ulong,IBackgroundSessionCallbacks *)

- ea: `0x18004e984`
- end: `0x18004eb88`
- name: `?LaunchBackGroundTask@BackgroundTaskHandler@@QEAAJPEBU_GUID@@PEAXKPEAUIBackgroundSessionCallbacks@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(BackgroundTaskHandler *this, const struct _GUID *, void *, __int64, struct IBackgroundSessionCallbacks *)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ce08`
- `0x1800441e4`
- `0x18004848c`

## callees

- `0x180003ca0`
- `0x18000a074`
- `0x18000b360`
- `0x1800127a4`
- `0x1800129dc`
- `0x180023664`
- `0x18004df4c`
- `0x18004e330`
- `0x18004e984`
- `0x18004eb90`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004ea40`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004ea40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004e9bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004e9bd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004e9cf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004e9cf`

## string_xrefs

- `0x18004eb3c`: `onecoreuap\printscan\print\workflow\broker\psa_lib\backgroundtaskhandler.cpp`
- `0x18004eb4f`: `onecoreuap\printscan\print\workflow\broker\psa_lib\backgroundtaskhandler.cpp`
- `0x18004eb61`: `onecoreuap\printscan\print\workflow\broker\psa_lib\backgroundtaskhandler.cpp`
- `0x18004eb75`: `onecoreuap\printscan\print\workflow\broker\psa_lib\backgroundtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall BackgroundTaskHandler::LaunchBackGroundTask(
        BackgroundTaskHandler *this,
        const struct _GUID *a2,
        void *a3,
        __int64 a4,
        struct IBackgroundSessionCallbacks *a5)
{
  DWORD CurrentProcessId; // edi
  HANDLE v7; // rax
  const char *v8; // r9
  HRESULT v9; // eax
  __int64 v10; // r11
  int v11; // eax
  int v12; // eax
  const char *v13; // r9
  __int64 result; // rax
  int v15; // [rsp+20h] [rbp-C8h]
  int v16; // [rsp+20h] [rbp-C8h]
  int v17; // [rsp+70h] [rbp-78h] BYREF
  HANDLE v18; // [rsp+78h] [rbp-70h] BYREF
  GUID pguid; // [rsp+80h] [rbp-68h] BYREF
  HANDLE v20; // [rsp+90h] [rbp-58h]
  DWORD v21; // [rsp+98h] [rbp-50h]
  int v22; // [rsp+9Ch] [rbp-4Ch]
  __int64 v23; // [rsp+A0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  CurrentProcessId = GetCurrentProcessId();
  v7 = OpenProcess(0x101000u, 0, CurrentProcessId);
  try
  {
    v18 = v7;
    if ( !v7 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\backgroundtaskhandler.cpp",
        v8);
    v22 = 0;
    v23 = 1;
    v21 = CurrentProcessId;
    v20 = v7;
    wil::AcquireSRWLockExclusive(&v17, (char *)this + 96);
    BackgroundTaskHandler::CheckAndCancelBgTask(this);
    pguid = 0;
    v9 = CoCreateGuid(&pguid);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\backgroundtaskhandler.cpp",
        (const char *)(unsigned int)v9,
        v15);
    winrt::hstring::c_str((BackgroundTaskHandler *)((char *)this + 24));
    v16 = (unsigned int)winrt::hstring::c_str((BackgroundTaskHandler *)((char *)this + 16));
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 56LL))(
            v10,
            0,
            0,
            *((unsigned int *)this + 18));
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\backgroundtaskhandler.cpp",
        (const char *)(unsigned int)v11,
        v16);
    *((_BYTE *)this + 76) = 1;
    v12 = BackgroundTaskHandler::RegisterForWnfCallbacks(this, a5, &pguid, (const struct _GUID *)((char *)this + 40));
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\backgroundtaskhandler.cpp",
        (const char *)(unsigned int)v12,
        v16);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x44,
                           (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\backgroundtaskhandler.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x18004e984  push    rbx
0x18004e986  push    rsi
0x18004e987  push    rdi
0x18004e988  push    r12
0x18004e98a  push    r13
0x18004e98c  push    r14
0x18004e98e  push    r15
0x18004e990  sub     rsp, 0B0h
0x18004e997  mov     rax, cs:__security_cookie
0x18004e99e  xor     rax, rsp
0x18004e9a1  mov     [rsp+0E8h+var_40], rax
0x18004e9a9  mov     r13d, r9d
0x18004e9ac  mov     r12, r8
0x18004e9af  mov     r15, rdx
0x18004e9b2  mov     rbx, rcx
0x18004e9b5  mov     rsi, [rsp+0E8h+arg_20]
0x18004e9bd  call    cs:__imp_GetCurrentProcessId
0x18004e9c3  mov     edi, eax
0x18004e9c5  mov     r8d, eax; dwProcessId
0x18004e9c8  xor     edx, edx; bInheritHandle
0x18004e9ca  mov     ecx, 101000h; dwDesiredAccess
0x18004e9cf  call    cs:__imp_OpenProcess
0x18004e9d5  mov     [rsp+0E8h+var_70], rax
0x18004e9da  mov     rcx, [rsp+0E8h]; this
0x18004e9e2  test    rax, rax
0x18004e9e5  jz      loc_18004EB3C
0x18004e9eb  mov     [rsp+0E8h+var_4C], 0
0x18004e9f6  mov     [rsp+0E8h+var_48], 1
0x18004ea02  mov     [rsp+0E8h+var_50], edi
0x18004ea09  mov     [rsp+0E8h+var_58], rax
0x18004ea11  mov     edi, 1
0x18004ea16  lea     rdx, [rbx+60h]
0x18004ea1a  lea     rcx, [rsp+0E8h+var_78]
0x18004ea1f  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18004ea24  nop
0x18004ea25  mov     rcx, rbx; this
0x18004ea28  call    ?CheckAndCancelBgTask@BackgroundTaskHandler@@AEAAXXZ; BackgroundTaskHandler::CheckAndCancelBgTask(void)
0x18004ea2d  xorps   xmm0, xmm0
0x18004ea30  movups  xmmword ptr [rsp+0E8h+pguid.Data1], xmm0
0x18004ea38  lea     rcx, [rsp+0E8h+pguid]; pguid
0x18004ea40  call    cs:__imp_CoCreateGuid
0x18004ea46  mov     rcx, [rsp+0E8h]; this
0x18004ea4e  test    eax, eax
0x18004ea50  js      loc_18004EB4C
0x18004ea56  mov     r11, [rbx+40h]
0x18004ea5a  lea     rcx, [rbx+18h]; this
0x18004ea5e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004ea63  mov     rdx, rax
0x18004ea66  lea     rcx, [rbx+10h]; this
0x18004ea6a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004ea6f  lea     r14, [rbx+28h]
0x18004ea73  mov     rcx, [r11]
0x18004ea76  mov     r10, [rcx+38h]
0x18004ea7a  mov     [rsp+0E8h+var_90], r14
0x18004ea7f  lea     rcx, [rsp+0E8h+pguid]
0x18004ea87  mov     [rsp+0E8h+var_98], rcx
0x18004ea8c  lea     rcx, [rsp+0E8h+var_58]
0x18004ea94  mov     [rsp+0E8h+var_A0], rcx
0x18004ea99  mov     [rsp+0E8h+var_A8], r13d
0x18004ea9e  mov     [rsp+0E8h+var_B0], r12
0x18004eaa3  mov     [rsp+0E8h+var_B8], r15
0x18004eaa8  mov     [rsp+0E8h+var_C0], rdx
0x18004eaad  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x18004eab2  mov     r9d, [rbx+48h]
0x18004eab6  xor     r8d, r8d
0x18004eab9  xor     edx, edx
0x18004eabb  mov     rcx, r11
0x18004eabe  mov     rax, r10
0x18004eac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eac6  mov     rcx, [rsp+0E8h]; this
0x18004eace  test    eax, eax
0x18004ead0  js      loc_18004EB5E
0x18004ead6  xchg    dil, [rbx+4Ch]
0x18004eada  mov     r9, r14; struct _GUID *
0x18004eadd  lea     r8, [rsp+0E8h+pguid]; struct _GUID *
0x18004eae5  mov     rdx, rsi; struct IBackgroundSessionCallbacks *
0x18004eae8  mov     rcx, rbx; this
0x18004eaeb  call    ?RegisterForWnfCallbacks@BackgroundTaskHandler@@AEAAJPEAUIBackgroundSessionCallbacks@@AEBU_GUID@@1@Z; BackgroundTaskHandler::RegisterForWnfCallbacks(IBackgroundSessionCallbacks *,_GUID const &,_GUID const &)
0x18004eaf0  mov     rcx, [rsp+0E8h]; this
0x18004eaf8  test    eax, eax
0x18004eafa  js      short loc_18004EB72
0x18004eafc  lea     rcx, [rsp+0E8h+var_78]
0x18004eb01  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004eb06  nop
0x18004eb07  lea     rcx, [rsp+0E8h+var_70]
0x18004eb0c  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004eb11  xor     eax, eax
0x18004eb13  jmp     short loc_18004EB19
0x18004eb15  mov     eax, [rsp+0E8h+var_78]
0x18004eb19  mov     rcx, [rsp+0E8h+var_40]
0x18004eb21  xor     rcx, rsp; StackCookie
0x18004eb24  call    __security_check_cookie
0x18004eb29  add     rsp, 0B0h
0x18004eb30  pop     r15
0x18004eb32  pop     r14
0x18004eb34  pop     r13
0x18004eb36  pop     r12
0x18004eb38  pop     rdi
0x18004eb39  pop     rsi
0x18004eb3a  pop     rbx
0x18004eb3b  retn
0x18004eb3c  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\workflow"...
0x18004eb43  lea     edx, [rax+2Dh]; void *
0x18004eb46  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004eb4c  mov     r9d, eax; char *
0x18004eb4f  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\workflow"...
0x18004eb56  lea     edx, [rdi+39h]; void *
0x18004eb59  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eb5e  mov     r9d, eax; char *
0x18004eb61  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\workflow"...
0x18004eb68  mov     edx, 3Dh ; '='; void *
0x18004eb6d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eb72  mov     r9d, eax; char *
0x18004eb75  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\workflow"...
0x18004eb7c  mov     edx, 40h ; '@'; void *
0x18004eb81  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
