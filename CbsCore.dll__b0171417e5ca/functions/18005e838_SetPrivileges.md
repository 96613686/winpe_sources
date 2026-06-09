# SetPrivileges

- ea: `0x18005e838`
- end: `0x18005eb1b`
- name: `SetPrivileges`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005eb24`

## callees

- `0x18002e280`
- `0x18002ec34`
- `0x18004f454`
- `0x18005e838`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800ec920`
- `0x1801026fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005e8a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005e8a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e88a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e88a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005e951`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005e9e2`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005e951`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005e9e2`

## string_xrefs

- `0x18005e8d0`: `Failed to get process token to set privileges into.`
- `0x18005ea15`: `Failed to adjust token privileges after resizing.`
- `0x18005ea97`: `Failed to adjust token privileges.`

## pseudocode

```c
__int64 __fastcall SetPrivileges(__int64 a1, struct _TOKEN_PRIVILEGES *a2)
{
  void **InitPointer; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  HANDLE v8; // rsi
  unsigned int v9; // ebx
  struct _TOKEN_PRIVILEGES *v10; // rbx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int PreviousState; // [rsp+20h] [rbp-48h]
  unsigned int v15; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v16[2]; // [rsp+38h] [rbp-30h] BYREF
  PTOKEN_PRIVILEGES v17; // [rsp+40h] [rbp-28h] BYREF
  DWORD BufferLength; // [rsp+48h] [rbp-20h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  TokenHandle = 0;
  v17 = 0;
  BufferLength = 0;
  if ( !a2 || !a2->PrivilegeCount )
    goto LABEL_31;
  InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&TokenHandle);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20028u, InitPointer) )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get process token to set privileges into.");
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      else
        v6 = LastError;
      v15 = v6;
      *(_QWORD *)v16 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v16);
    }
    if ( LastError )
    {
      v7 = 57;
LABEL_23:
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
             (const char *)(unsigned int)LastError,
             PreviousState);
      goto LABEL_32;
    }
    goto LABEL_31;
  }
  v8 = TokenHandle;
  if ( AdjustTokenPrivileges(TokenHandle, 0, a2, BufferLength, 0, &BufferLength) )
    goto LABEL_31;
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to adjust token privileges.");
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      else
        v12 = LastError;
      v15 = v12;
      *(_QWORD *)v16 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v16);
    }
    if ( LastError )
    {
      v7 = 90;
      goto LABEL_23;
    }
    goto LABEL_31;
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v17);
  if ( Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(&v17, BufferLength) )
  {
    v10 = v17;
    memset_0(v17, 0, BufferLength);
    if ( !AdjustTokenPrivileges(v8, 0, a2, BufferLength, v10, &BufferLength) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to adjust token privileges after resizing.");
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        else
          v11 = LastError;
        v15 = v11;
        *(_QWORD *)v16 = &v15;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v16);
      }
      if ( LastError )
      {
        v7 = 86;
        goto LABEL_23;
      }
    }
LABEL_31:
    v9 = 0;
    goto LABEL_32;
  }
  v9 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4F,
    (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
    (const char *)0x8007000ELL,
    PreviousState);
LABEL_32:
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v17);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&TokenHandle);
  return v9;
}

```

## disassembly

```asm
0x18005e838  push    rbp
0x18005e83a  push    rbx
0x18005e83b  push    rsi
0x18005e83c  push    rdi
0x18005e83d  mov     rbp, rsp
0x18005e840  sub     rsp, 68h
0x18005e844  mov     rax, cs:__security_cookie
0x18005e84b  xor     rax, rsp
0x18005e84e  mov     [rbp+var_10], rax
0x18005e852  mov     [rbp+TokenHandle], 0
0x18005e85a  mov     rdi, rdx
0x18005e85d  mov     [rbp+var_28], 0
0x18005e865  mov     [rbp+BufferLength], 0
0x18005e86c  test    rdx, rdx
0x18005e86f  jz      loc_18005EAEF
0x18005e875  cmp     dword ptr [rdx], 0
0x18005e878  jz      loc_18005EAEF
0x18005e87e  lea     rcx, [rbp+TokenHandle]
0x18005e882  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18005e887  mov     rbx, rax
0x18005e88a  call    cs:__imp_GetCurrentProcess
0x18005e891  nop     dword ptr [rax+rax+00h]
0x18005e896  mov     r8, rbx; TokenHandle
0x18005e899  mov     edx, 20028h; DesiredAccess
0x18005e89e  mov     rcx, rax; ProcessHandle
0x18005e8a1  call    cs:__imp_OpenProcessToken
0x18005e8a8  nop     dword ptr [rax+rax+00h]
0x18005e8ad  test    eax, eax
0x18005e8af  jnz     short loc_18005E92F
0x18005e8b1  call    cs:__imp_GetLastError
0x18005e8b8  nop     dword ptr [rax+rax+00h]
0x18005e8bd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e8c4  mov     ebx, eax
0x18005e8c6  test    rcx, rcx
0x18005e8c9  jz      short loc_18005E91D
0x18005e8cb  mov     edi, 3
0x18005e8d0  lea     r9, aFailedToGetPro_60; "Failed to get process token to set priv"...
0x18005e8d7  mov     r8d, edi
0x18005e8da  xor     edx, edx
0x18005e8dc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005e8e1  test    ebx, ebx
0x18005e8e3  jg      short loc_18005E8E9
0x18005e8e5  mov     eax, ebx
0x18005e8e7  jmp     short loc_18005E8F1
0x18005e8e9  movzx   eax, bx
0x18005e8ec  or      eax, 80070000h
0x18005e8f1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005e8f8  lea     r9, a0; ": {0}"
0x18005e8ff  mov     [rbp+var_38], eax
0x18005e902  mov     r8d, edi
0x18005e905  lea     rax, [rbp+var_38]
0x18005e909  mov     dl, 1
0x18005e90b  mov     qword ptr [rbp+var_30], rax
0x18005e90f  lea     rax, [rbp+var_30]
0x18005e913  mov     [rsp+68h+PreviousState], rax
0x18005e918  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005e91d  test    ebx, ebx
0x18005e91f  jz      loc_18005EAEF
0x18005e925  mov     edx, 39h ; '9'
0x18005e92a  jmp     loc_18005EA6F
0x18005e92f  mov     rsi, [rbp+TokenHandle]
0x18005e933  lea     rax, [rbp+BufferLength]
0x18005e937  mov     r9d, [rbp+BufferLength]; BufferLength
0x18005e93b  mov     rcx, rsi; TokenHandle
0x18005e93e  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18005e943  mov     r8, rdi; NewState
0x18005e946  xor     edx, edx; DisableAllPrivileges
0x18005e948  mov     [rsp+68h+PreviousState], 0; int
0x18005e951  call    cs:__imp_AdjustTokenPrivileges
0x18005e958  nop     dword ptr [rax+rax+00h]
0x18005e95d  test    eax, eax
0x18005e95f  jnz     loc_18005EAEF
0x18005e965  call    cs:__imp_GetLastError
0x18005e96c  nop     dword ptr [rax+rax+00h]
0x18005e971  mov     ebx, eax
0x18005e973  cmp     eax, 7Ah ; 'z'
0x18005e976  jnz     loc_18005EA86
0x18005e97c  lea     rcx, [rbp+var_28]
0x18005e980  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18005e985  mov     edx, [rbp+BufferLength]
0x18005e988  lea     rcx, [rbp+var_28]
0x18005e98c  call    ?AllocateWithTotalSize@?$AutoNewWithUnsizedArrayPtr@U_BACKING_REGION_OUTPUT@@@Windows@@QEAAPEAU_BACKING_REGION_OUTPUT@@_K@Z; Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(unsigned __int64)
0x18005e991  test    rax, rax
0x18005e994  jnz     short loc_18005E9B6
0x18005e996  mov     rcx, [rbp+20h]; this
0x18005e99a  lea     r8, aOnecoreBaseCbs_106; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x18005e9a1  mov     ebx, 8007000Eh
0x18005e9a6  lea     edx, [rax+4Fh]; void *
0x18005e9a9  mov     r9d, ebx; char *
0x18005e9ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e9b1  jmp     loc_18005EAF1
0x18005e9b6  mov     rbx, [rbp+var_28]
0x18005e9ba  xor     edx, edx; Val
0x18005e9bc  mov     r8d, [rbp+BufferLength]; Size
0x18005e9c0  mov     rcx, rbx; void *
0x18005e9c3  call    memset_0
0x18005e9c8  mov     r9d, [rbp+BufferLength]; BufferLength
0x18005e9cc  lea     rax, [rbp+BufferLength]
0x18005e9d0  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18005e9d5  mov     r8, rdi; NewState
0x18005e9d8  xor     edx, edx; DisableAllPrivileges
0x18005e9da  mov     [rsp+68h+PreviousState], rbx; PreviousState
0x18005e9df  mov     rcx, rsi; TokenHandle
0x18005e9e2  call    cs:__imp_AdjustTokenPrivileges
0x18005e9e9  nop     dword ptr [rax+rax+00h]
0x18005e9ee  test    eax, eax
0x18005e9f0  jnz     loc_18005EAEF
0x18005e9f6  call    cs:__imp_GetLastError
0x18005e9fd  nop     dword ptr [rax+rax+00h]
0x18005ea02  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005ea09  mov     ebx, eax
0x18005ea0b  test    rcx, rcx
0x18005ea0e  jz      short loc_18005EA62
0x18005ea10  mov     edi, 3
0x18005ea15  lea     r9, aFailedToAdjust_1; "Failed to adjust token privileges after"...
0x18005ea1c  mov     r8d, edi
0x18005ea1f  xor     edx, edx
0x18005ea21  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005ea26  test    ebx, ebx
0x18005ea28  jg      short loc_18005EA2E
0x18005ea2a  mov     eax, ebx
0x18005ea2c  jmp     short loc_18005EA36
0x18005ea2e  movzx   eax, bx
0x18005ea31  or      eax, 80070000h
0x18005ea36  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005ea3d  lea     r9, a0; ": {0}"
0x18005ea44  mov     [rbp+var_38], eax
0x18005ea47  mov     r8d, edi
0x18005ea4a  lea     rax, [rbp+var_38]
0x18005ea4e  mov     dl, 1
0x18005ea50  mov     qword ptr [rbp+var_30], rax
0x18005ea54  lea     rax, [rbp+var_30]
0x18005ea58  mov     [rsp+68h+PreviousState], rax; unsigned int
0x18005ea5d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005ea62  test    ebx, ebx
0x18005ea64  jz      loc_18005EAEF
0x18005ea6a  mov     edx, 56h ; 'V'; void *
0x18005ea6f  mov     rcx, [rbp+20h]; this
0x18005ea73  lea     r8, aOnecoreBaseCbs_106; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x18005ea7a  mov     r9d, ebx; char *
0x18005ea7d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005ea82  mov     ebx, eax
0x18005ea84  jmp     short loc_18005EAF1
0x18005ea86  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005ea8d  test    rcx, rcx
0x18005ea90  jz      short loc_18005EAE4
0x18005ea92  mov     edi, 3
0x18005ea97  lea     r9, aFailedToAdjust_0; "Failed to adjust token privileges."
0x18005ea9e  mov     r8d, edi
0x18005eaa1  xor     edx, edx
0x18005eaa3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005eaa8  test    ebx, ebx
0x18005eaaa  jg      short loc_18005EAB0
0x18005eaac  mov     eax, ebx
0x18005eaae  jmp     short loc_18005EAB8
0x18005eab0  movzx   eax, bx
0x18005eab3  or      eax, 80070000h
0x18005eab8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005eabf  lea     r9, a0; ": {0}"
0x18005eac6  mov     [rbp+var_38], eax
0x18005eac9  mov     r8d, edi
0x18005eacc  lea     rax, [rbp+var_38]
0x18005ead0  mov     dl, 1
0x18005ead2  mov     qword ptr [rbp+var_30], rax
0x18005ead6  lea     rax, [rbp+var_30]
0x18005eada  mov     [rsp+68h+PreviousState], rax
0x18005eadf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005eae4  test    ebx, ebx
0x18005eae6  jz      short loc_18005EAEF
0x18005eae8  mov     edx, 5Ah ; 'Z'
0x18005eaed  jmp     short loc_18005EA6F
0x18005eaef  xor     ebx, ebx
0x18005eaf1  lea     rcx, [rbp+var_28]
0x18005eaf5  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18005eafa  lea     rcx, [rbp+TokenHandle]
0x18005eafe  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18005eb03  mov     eax, ebx
0x18005eb05  mov     rcx, [rbp+var_10]
0x18005eb09  xor     rcx, rsp; StackCookie
0x18005eb0c  call    __security_check_cookie
0x18005eb11  add     rsp, 68h
0x18005eb15  pop     rdi
0x18005eb16  pop     rsi
0x18005eb17  pop     rbx
0x18005eb18  pop     rbp
0x18005eb19  retn
```
