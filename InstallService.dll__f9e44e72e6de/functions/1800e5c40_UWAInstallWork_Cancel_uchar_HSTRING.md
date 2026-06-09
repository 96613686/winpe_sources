# UWAInstallWork::Cancel(uchar,HSTRING__ *)

- ea: `0x1800e5c40`
- end: `0x1800e5ee1`
- name: `?Cancel@UWAInstallWork@@UEAAJEPEAUHSTRING__@@@Z`
- size: `673`
- prototype: `__int64 __fastcall(UWAInstallWork *__hidden this, unsigned __int8, HSTRING)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x180012368`
- `0x180012394`
- `0x1800123f8`
- `0x180012428`
- `0x1800127c8`
- `0x18001c414`
- `0x1800e5c40`
- `0x1800ee3e8`
- `0x1800fa4c0`
- `0x1800fa880`
- `0x1800fa8c0`
- `0x1801131e0`
- `0x180115718`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800e5d8a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800e5d8a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e5e32`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e5e32`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e5e09`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e5e09`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e5e29`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e5e29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5e5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5e5c`

## string_xrefs

- `0x1800e5cbd`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800e5e94`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800e5e73`: `Releasing InstallAgentPdcActivation`
- `0x1800e5cb0`: `UWAInstallWork::Cancel`
- `0x1800e5e87`: `UWAInstallWork::Cancel`

## pseudocode

```c
__int64 __fastcall UWAInstallWork::Cancel(UWAInstallWork *this, char a2, HSTRING a3)
{
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int v7; // r12d
  unsigned int v8; // edi
  int v9; // r15d
  PCWSTR v10; // rax
  const char *v11; // r9
  struct _TP_WORK *ThreadpoolWork; // rdi
  const unsigned __int16 *v13; // rax
  char *v15; // [rsp+20h] [rbp-A9h]
  _BYTE v16[8]; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v17[8]; // [rsp+48h] [rbp-81h] BYREF
  int v18[4]; // [rsp+50h] [rbp-79h] BYREF
  __int128 v19; // [rsp+60h] [rbp-69h]
  __int128 v20; // [rsp+70h] [rbp-59h]
  __int128 v21; // [rsp+80h] [rbp-49h]
  __int128 v22; // [rsp+90h] [rbp-39h]
  __int128 v23; // [rsp+A0h] [rbp-29h]
  __int128 v24; // [rsp+B0h] [rbp-19h]
  __int128 v25; // [rsp+C0h] [rbp-9h]
  char v26; // [rsp+D0h] [rbp+7h]

  if ( a2 && !a3 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
    LogSimpleMessage(
      (_DWORD)a3 + 2,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      0x42Fu,
      "UWAInstallWork::Cancel",
      -1,
      L"CV should be passed in for interactive action",
      (const char *)this + 304,
      StringRawBuffer);
  }
  Microsoft::WRL::Wrappers::SRWLock::LockShared(v16, (char *)this + 1048);
  v7 = *((_DWORD *)this + 267);
  v8 = *((_DWORD *)this + 265);
  if ( v8 == 2 || v8 == 14 || (v9 = 0, v8 == 3) )
    v9 = UWAInstallWork::_RequestAbort(this);
  if ( a3 )
  {
    v10 = WindowsGetStringRawBuffer(a3, 0);
    _o_wcstombs(v18, v10, 129);
  }
  else
  {
    *(_OWORD *)v18 = *((_OWORD *)this + 19);
    v19 = *((_OWORD *)this + 20);
    v20 = *((_OWORD *)this + 21);
    v21 = *((_OWORD *)this + 22);
    v22 = *((_OWORD *)this + 23);
    v23 = *((_OWORD *)this + 24);
    v24 = *((_OWORD *)this + 25);
    v25 = *((_OWORD *)this + 26);
    v26 = *((_BYTE *)this + 432);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v16);
  if ( v9 < 0 )
  {
    if ( v8 != 2 )
      goto LABEL_22;
LABEL_21:
    UWAInstallWork::_RaiseProgressEvent(this, 0);
    goto LABEL_22;
  }
  if ( a2 )
    WindowsUpdate::Telemetry::CancelInstallation(this, (struct UWAInstallWork *)v8, v7, (int)v18, v15);
  else
    WindowsUpdate::Telemetry::AbortedInstallation(this, (struct UWAInstallWork *)v7, (int)v18, v11);
  wil::AcquireSRWLockExclusive(v17, (char *)this + 1048);
  *((_DWORD *)this + 265) = 5;
  *((_DWORD *)this + 267) = 0;
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v17);
  if ( v8 == 2 )
    goto LABEL_21;
  if ( !a2 )
  {
    UWAInstallWork::_CleanupAfterCancel(this);
    goto LABEL_21;
  }
  ThreadpoolWork = CreateThreadpoolWork(UWAInstallWork::s_CleanupAfterCancel, this, 0);
  if ( ThreadpoolWork )
  {
    (*(void (__fastcall **)(UWAInstallWork *))(*(_QWORD *)this + 8LL))(this);
    SubmitThreadpoolWork(ThreadpoolWork);
    CloseThreadpoolWork(ThreadpoolWork);
  }
LABEL_22:
  v13 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
  LogMessage(
    4u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
    0x476u,
    "UWAInstallWork::Cancel",
    -1,
    L"Releasing InstallAgentPdcActivation",
    (const char *)this + 304,
    v13);
  UWAInstallWork::_ReleasePdcActivation(this);
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800e5c40  mov     [rsp-8+arg_8], rbx
0x1800e5c45  push    rbp
0x1800e5c46  push    rsi
0x1800e5c47  push    rdi
0x1800e5c48  push    r12
0x1800e5c4a  push    r13
0x1800e5c4c  push    r14
0x1800e5c4e  push    r15
0x1800e5c50  lea     rbp, [rsp-27h]
0x1800e5c55  sub     rsp, 0F0h
0x1800e5c5c  mov     rax, cs:__security_cookie
0x1800e5c63  xor     rax, rsp
0x1800e5c66  mov     [rbp+57h+var_40], rax
0x1800e5c6a  mov     rsi, r8
0x1800e5c6d  mov     r14b, dl
0x1800e5c70  mov     rbx, rcx
0x1800e5c73  test    dl, dl
0x1800e5c75  jz      short loc_1800E5CCC
0x1800e5c77  test    r8, r8
0x1800e5c7a  jnz     short loc_1800E5CCC
0x1800e5c7c  xor     edx, edx; length
0x1800e5c7e  mov     rcx, [rcx+1D8h]; string
0x1800e5c85  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5c8b  lea     rcx, [rbx+130h]
0x1800e5c92  mov     [rsp+120h+var_E8], rax; unsigned __int16 *
0x1800e5c97  mov     [rsp+120h+var_F0], rcx; char *
0x1800e5c9c  lea     rax, aCvShouldBePass; "CV should be passed in for interactive "...
0x1800e5ca3  mov     [rsp+120h+var_F8], rax; unsigned __int16 *
0x1800e5ca8  mov     dword ptr [rsp+120h+var_100], 0FFFFFFFFh; char *
0x1800e5cb0  lea     r9, aUwainstallwork_30; "UWAInstallWork::Cancel"
0x1800e5cb7  mov     r8d, 42Fh; unsigned int
0x1800e5cbd  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800e5cc4  lea     ecx, [rsi+2]; unsigned int
0x1800e5cc7  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800e5ccc  lea     r13, [rbx+418h]
0x1800e5cd3  mov     rdx, r13
0x1800e5cd6  lea     rcx, [rsp+120h+var_E0]
0x1800e5cdb  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800e5ce0  mov     r12d, [rbx+42Ch]
0x1800e5ce7  mov     edi, [rbx+424h]
0x1800e5ced  cmp     edi, 2
0x1800e5cf0  jz      short loc_1800E5CFF
0x1800e5cf2  cmp     edi, 0Eh
0x1800e5cf5  jz      short loc_1800E5CFF
0x1800e5cf7  xor     r15d, r15d
0x1800e5cfa  cmp     edi, 3
0x1800e5cfd  jnz     short loc_1800E5D0A
0x1800e5cff  mov     rcx, rbx; this
0x1800e5d02  call    ?_RequestAbort@UWAInstallWork@@AEAAJXZ; UWAInstallWork::_RequestAbort(void)
0x1800e5d07  mov     r15d, eax
0x1800e5d0a  test    rsi, rsi
0x1800e5d0d  jnz     short loc_1800E5D72
0x1800e5d0f  movups  xmm0, xmmword ptr [rbx+130h]
0x1800e5d16  movups  xmmword ptr [rbp+57h+var_D0], xmm0
0x1800e5d1a  movups  xmm1, xmmword ptr [rbx+140h]
0x1800e5d21  movups  [rbp+57h+var_C0], xmm1
0x1800e5d25  movups  xmm0, xmmword ptr [rbx+150h]
0x1800e5d2c  movups  [rbp+57h+var_B0], xmm0
0x1800e5d30  movups  xmm1, xmmword ptr [rbx+160h]
0x1800e5d37  movups  [rbp+57h+var_A0], xmm1
0x1800e5d3b  movups  xmm0, xmmword ptr [rbx+170h]
0x1800e5d42  movups  [rbp+57h+var_90], xmm0
0x1800e5d46  movups  xmm1, xmmword ptr [rbx+180h]
0x1800e5d4d  movups  [rbp+57h+var_80], xmm1
0x1800e5d51  movups  xmm0, xmmword ptr [rbx+190h]
0x1800e5d58  movups  [rbp+57h+var_70], xmm0
0x1800e5d5c  movups  xmm1, xmmword ptr [rbx+1A0h]
0x1800e5d63  movups  [rbp+57h+var_60], xmm1
0x1800e5d67  mov     al, [rbx+1B0h]
0x1800e5d6d  mov     [rbp+57h+var_50], al
0x1800e5d70  jmp     short loc_1800E5D90
0x1800e5d72  xor     edx, edx; length
0x1800e5d74  mov     rcx, rsi; string
0x1800e5d77  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5d7d  mov     rdx, rax
0x1800e5d80  mov     r8d, 81h
0x1800e5d86  lea     rcx, [rbp+57h+var_D0]
0x1800e5d8a  call    cs:__imp__o_wcstombs
0x1800e5d90  lea     rcx, [rsp+120h+var_E0]; this
0x1800e5d95  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800e5d9a  test    r15d, r15d
0x1800e5d9d  js      loc_1800E5E44
0x1800e5da3  mov     rcx, rbx; this
0x1800e5da6  test    r14b, r14b
0x1800e5da9  jz      short loc_1800E5DBB
0x1800e5dab  lea     r9, [rbp+57h+var_D0]; int
0x1800e5daf  mov     r8d, r12d; unsigned int
0x1800e5db2  mov     edx, edi; struct UWAInstallWork *
0x1800e5db4  call    ?CancelInstallation@Telemetry@WindowsUpdate@@YAXPEAVUWAInstallWork@@IJPEBD@Z; WindowsUpdate::Telemetry::CancelInstallation(UWAInstallWork *,uint,long,char const *)
0x1800e5db9  jmp     short loc_1800E5DC7
0x1800e5dbb  lea     r8, [rbp+57h+var_D0]; int
0x1800e5dbf  mov     edx, r12d; struct UWAInstallWork *
0x1800e5dc2  call    ?AbortedInstallation@Telemetry@WindowsUpdate@@YAXPEAVUWAInstallWork@@JPEBD@Z; WindowsUpdate::Telemetry::AbortedInstallation(UWAInstallWork *,long,char const *)
0x1800e5dc7  mov     rdx, r13
0x1800e5dca  lea     rcx, [rsp+120h+var_D8]
0x1800e5dcf  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800e5dd4  mov     dword ptr [rbx+424h], 5
0x1800e5dde  mov     dword ptr [rbx+42Ch], 0
0x1800e5de8  lea     rcx, [rsp+120h+var_D8]; this
0x1800e5ded  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800e5df2  cmp     edi, 2
0x1800e5df5  jz      short loc_1800E5E49
0x1800e5df7  test    r14b, r14b
0x1800e5dfa  jz      short loc_1800E5E3A
0x1800e5dfc  xor     r8d, r8d; pcbe
0x1800e5dff  mov     rdx, rbx; pv
0x1800e5e02  lea     rcx, ?s_CleanupAfterCancel@UWAInstallWork@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e5e09  call    cs:__imp_CreateThreadpoolWork
0x1800e5e0f  mov     rdi, rax
0x1800e5e12  test    rax, rax
0x1800e5e15  jz      short loc_1800E5E53
0x1800e5e17  mov     rcx, [rbx]
0x1800e5e1a  mov     rax, [rcx+8]
0x1800e5e1e  mov     rcx, rbx
0x1800e5e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5e26  mov     rcx, rdi; pwk
0x1800e5e29  call    cs:__imp_SubmitThreadpoolWork
0x1800e5e2f  mov     rcx, rdi; pwk
0x1800e5e32  call    cs:__imp_CloseThreadpoolWork
0x1800e5e38  jmp     short loc_1800E5E53
0x1800e5e3a  mov     rcx, rbx; this
0x1800e5e3d  call    ?_CleanupAfterCancel@UWAInstallWork@@AEAAXXZ; UWAInstallWork::_CleanupAfterCancel(void)
0x1800e5e42  jmp     short loc_1800E5E49
0x1800e5e44  cmp     edi, 2
0x1800e5e47  jnz     short loc_1800E5E53
0x1800e5e49  xor     edx, edx; bool
0x1800e5e4b  mov     rcx, rbx; this
0x1800e5e4e  call    ?_RaiseProgressEvent@UWAInstallWork@@AEAAX_N@Z; UWAInstallWork::_RaiseProgressEvent(bool)
0x1800e5e53  xor     edx, edx; length
0x1800e5e55  mov     rcx, [rbx+1D8h]; string
0x1800e5e5c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5e62  lea     r8, [rbx+130h]
0x1800e5e69  mov     [rsp+120h+var_E8], rax; unsigned __int16 *
0x1800e5e6e  mov     [rsp+120h+var_F0], r8; char *
0x1800e5e73  lea     rax, aReleasingInsta; "Releasing InstallAgentPdcActivation"
0x1800e5e7a  mov     [rsp+120h+var_F8], rax; unsigned __int16 *
0x1800e5e7f  mov     dword ptr [rsp+120h+var_100], 0FFFFFFFFh; int
0x1800e5e87  lea     r9, aUwainstallwork_30; "UWAInstallWork::Cancel"
0x1800e5e8e  mov     r8d, 476h; unsigned int
0x1800e5e94  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800e5e9b  mov     ecx, 4; unsigned int
0x1800e5ea0  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800e5ea5  mov     rcx, rbx; this
0x1800e5ea8  call    ?_ReleasePdcActivation@UWAInstallWork@@AEAAXXZ; UWAInstallWork::_ReleasePdcActivation(void)
0x1800e5ead  lea     rcx, [rsp+120h+var_E0]; this
0x1800e5eb2  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800e5eb7  mov     eax, r15d
0x1800e5eba  mov     rcx, [rbp+57h+var_40]
0x1800e5ebe  xor     rcx, rsp; StackCookie
0x1800e5ec1  call    __security_check_cookie
0x1800e5ec6  mov     rbx, [rsp+120h+arg_8]
0x1800e5ece  add     rsp, 0F0h
0x1800e5ed5  pop     r15
0x1800e5ed7  pop     r14
0x1800e5ed9  pop     r13
0x1800e5edb  pop     r12
0x1800e5edd  pop     rdi
0x1800e5ede  pop     rsi
0x1800e5edf  pop     rbp
0x1800e5ee0  retn
```
