# SetPrivileges

- ea: `0x1400203b8`
- end: `0x1400206c6`
- name: `SetPrivileges`
- size: `782`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002027c`
- `0x1400206cc`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x140017810`
- `0x140017d14`
- `0x1400184fc`
- `0x140019bb8`
- `0x14001b210`
- `0x1400203b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020591`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140020426`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140020426`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020415`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140020415`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140020516`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140020583`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140020516`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140020583`

## string_xrefs

- `0x140020449`: `Failed to get process token to set privileges into.`
- `0x1400205aa`: `Failed to adjust token privileges after resizing.`
- `0x14002062a`: `Failed to adjust token privileges.`

## pseudocode

```c
__int64 __fastcall SetPrivileges(__int64 a1, struct _TOKEN_PRIVILEGES *a2, struct _TOKEN_PRIVILEGES **a3)
{
  struct _TOKEN_PRIVILEGES *v3; // rdi
  void **InitPointer; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // ebx
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rdx
  HANDLE v12; // r15
  struct _TOKEN_PRIVILEGES *v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  unsigned int PreviousState; // [rsp+20h] [rbp-40h]
  unsigned int v22; // [rsp+30h] [rbp-30h] BYREF
  PTOKEN_PRIVILEGES v23; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v24[2]; // [rsp+40h] [rbp-20h] BYREF
  size_t Size; // [rsp+48h] [rbp-18h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v3 = 0;
  TokenHandle = 0;
  v23 = 0;
  LODWORD(Size) = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 || !a2->PrivilegeCount )
    goto LABEL_40;
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
        v10 = (unsigned __int16)LastError | 0x80070000;
      else
        v10 = LastError;
      v22 = v10;
      *(_QWORD *)v24 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {0}",
        (__int64)v24);
    }
    if ( LastError )
    {
      v11 = 57;
LABEL_30:
      v15 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v11,
              (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
              (const char *)(unsigned int)LastError,
              PreviousState);
      goto LABEL_41;
    }
    goto LABEL_40;
  }
  v12 = TokenHandle;
  v13 = 0;
  if ( !a3 )
  {
LABEL_18:
    if ( !AdjustTokenPrivileges(v12, 0, a2, Size, v13, (PDWORD)&Size) )
    {
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
            v19 = (unsigned __int16)LastError | 0x80070000;
          else
            v19 = LastError;
          v22 = v19;
          *(_QWORD *)v24 = &v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v18,
            3,
            (__int64)": {0}",
            (__int64)v24);
        }
        if ( LastError )
        {
          v11 = 90;
          goto LABEL_30;
        }
        goto LABEL_40;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&v23);
      if ( !Windows::AutoNewArrayPtr<unsigned char>::AllocateArray(&v23, (unsigned int)Size) )
      {
        v14 = 79;
        goto LABEL_16;
      }
      v3 = v23;
      memset_0(v23, 0, (unsigned int)Size);
      if ( !AdjustTokenPrivileges(v12, 0, a2, Size, v3, (PDWORD)&Size) )
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
            v17 = (unsigned __int16)LastError | 0x80070000;
          else
            v17 = LastError;
          v22 = v17;
          *(_QWORD *)v24 = &v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v16,
            3,
            (__int64)": {0}",
            (__int64)v24);
        }
        if ( LastError )
        {
          v11 = 86;
          goto LABEL_30;
        }
LABEL_40:
        v15 = 0;
        goto LABEL_41;
      }
    }
    if ( a3 )
    {
      v23 = 0;
      *a3 = v3;
    }
    goto LABEL_40;
  }
  LODWORD(Size) = 1024;
  if ( Windows::AutoNewArrayPtr<unsigned char>::AllocateArray(&v23, 0x400u) )
  {
    v3 = v23;
    memset_0(v23, 0, (unsigned int)Size);
    v13 = v3;
    goto LABEL_18;
  }
  v14 = 66;
LABEL_16:
  v15 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
    (const char *)0x8007000ELL,
    PreviousState);
LABEL_41:
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&v23);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&TokenHandle);
  return v15;
}

```

## disassembly

```asm
0x1400203b8  mov     [rsp-28h+arg_0], rbx
0x1400203bd  push    rbp
0x1400203be  push    rsi
0x1400203bf  push    rdi
0x1400203c0  push    r14
0x1400203c2  push    r15
0x1400203c4  mov     rbp, rsp
0x1400203c7  sub     rsp, 60h
0x1400203cb  mov     rax, cs:__security_cookie
0x1400203d2  xor     rax, rsp
0x1400203d5  mov     [rbp+var_8], rax
0x1400203d9  xor     edi, edi
0x1400203db  mov     [rbp+TokenHandle], 0
0x1400203e3  mov     [rbp+var_28], rdi
0x1400203e7  mov     rsi, r8
0x1400203ea  mov     dword ptr [rbp+Size], edi
0x1400203ed  mov     r14, rdx
0x1400203f0  test    r8, r8
0x1400203f3  jz      short loc_1400203F8
0x1400203f5  mov     [r8], rdi
0x1400203f8  test    r14, r14
0x1400203fb  jz      loc_140020690
0x140020401  cmp     [rdx], edi
0x140020403  jz      loc_140020690
0x140020409  lea     rcx, [rbp+TokenHandle]
0x14002040d  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x140020412  mov     rbx, rax
0x140020415  call    cs:__imp_GetCurrentProcess
0x14002041b  mov     r8, rbx; TokenHandle
0x14002041e  mov     edx, 20028h; DesiredAccess
0x140020423  mov     rcx, rax; ProcessHandle
0x140020426  call    cs:__imp_OpenProcessToken
0x14002042c  test    eax, eax
0x14002042e  jnz     short loc_1400204A6
0x140020430  call    cs:__imp_GetLastError
0x140020436  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002043d  mov     ebx, eax
0x14002043f  test    rcx, rcx
0x140020442  jz      short loc_140020494
0x140020444  mov     edi, 3
0x140020449  lea     r9, aFailedToGetPro_6; "Failed to get process token to set priv"...
0x140020450  mov     r8d, edi
0x140020453  xor     edx, edx
0x140020455  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002045a  test    ebx, ebx
0x14002045c  jg      short loc_140020462
0x14002045e  mov     eax, ebx
0x140020460  jmp     short loc_14002046A
0x140020462  movzx   eax, bx
0x140020465  or      eax, 80070000h
0x14002046a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020471  lea     r9, a0; ": {0}"
0x140020478  mov     [rbp+var_30], eax
0x14002047b  mov     r8d, edi
0x14002047e  lea     rax, [rbp+var_30]
0x140020482  mov     qword ptr [rbp+var_20], rax
0x140020486  lea     rax, [rbp+var_20]
0x14002048a  mov     [rsp+60h+PreviousState], rax
0x14002048f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020494  test    ebx, ebx
0x140020496  jz      loc_140020690
0x14002049c  mov     edx, 39h ; '9'
0x1400204a1  jmp     loc_140020602
0x1400204a6  mov     r15, [rbp+TokenHandle]
0x1400204aa  xor     eax, eax
0x1400204ac  test    rsi, rsi
0x1400204af  jz      short loc_1400204FC
0x1400204b1  mov     edx, 400h
0x1400204b6  lea     rcx, [rbp+var_28]
0x1400204ba  mov     dword ptr [rbp+Size], edx
0x1400204bd  call    ?AllocateArray@?$AutoNewArrayPtr@E@Windows@@QEAAPEAE_K@Z; Windows::AutoNewArrayPtr<uchar>::AllocateArray(unsigned __int64)
0x1400204c2  test    rax, rax
0x1400204c5  jnz     short loc_1400204E7
0x1400204c7  lea     edx, [rax+42h]; void *
0x1400204ca  mov     rcx, [rbp+28h]; this
0x1400204ce  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x1400204d5  mov     ebx, 8007000Eh
0x1400204da  mov     r9d, ebx; char *
0x1400204dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400204e2  jmp     loc_140020692
0x1400204e7  mov     rdi, [rbp+var_28]
0x1400204eb  xor     edx, edx; Val
0x1400204ed  mov     r8d, dword ptr [rbp+Size]; Size
0x1400204f1  mov     rcx, rdi; void *
0x1400204f4  call    memset_0
0x1400204f9  mov     rax, rdi
0x1400204fc  mov     r9d, dword ptr [rbp+Size]; BufferLength
0x140020500  lea     rcx, [rbp+Size]
0x140020504  mov     [rsp+60h+ReturnLength], rcx; ReturnLength
0x140020509  mov     r8, r14; NewState
0x14002050c  mov     rcx, r15; TokenHandle
0x14002050f  mov     [rsp+60h+PreviousState], rax; PreviousState
0x140020514  xor     edx, edx; DisableAllPrivileges
0x140020516  call    cs:__imp_AdjustTokenPrivileges
0x14002051c  test    eax, eax
0x14002051e  jnz     loc_140020680
0x140020524  call    cs:__imp_GetLastError
0x14002052a  mov     ebx, eax
0x14002052c  cmp     eax, 7Ah ; 'z'
0x14002052f  jnz     loc_140020619
0x140020535  lea     rcx, [rbp+var_28]
0x140020539  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x14002053e  mov     edx, dword ptr [rbp+Size]
0x140020541  lea     rcx, [rbp+var_28]
0x140020545  call    ?AllocateArray@?$AutoNewArrayPtr@E@Windows@@QEAAPEAE_K@Z; Windows::AutoNewArrayPtr<uchar>::AllocateArray(unsigned __int64)
0x14002054a  test    rax, rax
0x14002054d  jnz     short loc_140020557
0x14002054f  lea     edx, [rbx-2Bh]
0x140020552  jmp     loc_1400204CA
0x140020557  mov     rdi, [rbp+var_28]
0x14002055b  xor     edx, edx; Val
0x14002055d  mov     r8d, dword ptr [rbp+Size]; Size
0x140020561  mov     rcx, rdi; void *
0x140020564  call    memset_0
0x140020569  mov     r9d, dword ptr [rbp+Size]; BufferLength
0x14002056d  lea     rax, [rbp+Size]
0x140020571  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x140020576  mov     r8, r14; NewState
0x140020579  xor     edx, edx; DisableAllPrivileges
0x14002057b  mov     [rsp+60h+PreviousState], rdi; PreviousState
0x140020580  mov     rcx, r15; TokenHandle
0x140020583  call    cs:__imp_AdjustTokenPrivileges
0x140020589  test    eax, eax
0x14002058b  jnz     loc_140020680
0x140020591  call    cs:__imp_GetLastError
0x140020597  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002059e  mov     ebx, eax
0x1400205a0  test    rcx, rcx
0x1400205a3  jz      short loc_1400205F5
0x1400205a5  mov     edi, 3
0x1400205aa  lea     r9, aFailedToAdjust_0; "Failed to adjust token privileges after"...
0x1400205b1  mov     r8d, edi
0x1400205b4  xor     edx, edx
0x1400205b6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400205bb  test    ebx, ebx
0x1400205bd  jg      short loc_1400205C3
0x1400205bf  mov     eax, ebx
0x1400205c1  jmp     short loc_1400205CB
0x1400205c3  movzx   eax, bx
0x1400205c6  or      eax, 80070000h
0x1400205cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400205d2  lea     r9, a0; ": {0}"
0x1400205d9  mov     [rbp+var_30], eax
0x1400205dc  mov     r8d, edi
0x1400205df  lea     rax, [rbp+var_30]
0x1400205e3  mov     qword ptr [rbp+var_20], rax
0x1400205e7  lea     rax, [rbp+var_20]
0x1400205eb  mov     [rsp+60h+PreviousState], rax; unsigned int
0x1400205f0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400205f5  test    ebx, ebx
0x1400205f7  jz      loc_140020690
0x1400205fd  mov     edx, 56h ; 'V'; void *
0x140020602  mov     rcx, [rbp+28h]; this
0x140020606  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x14002060d  mov     r9d, ebx; char *
0x140020610  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140020615  mov     ebx, eax
0x140020617  jmp     short loc_140020692
0x140020619  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020620  test    rcx, rcx
0x140020623  jz      short loc_140020675
0x140020625  mov     edi, 3
0x14002062a  lea     r9, aFailedToAdjust; "Failed to adjust token privileges."
0x140020631  mov     r8d, edi
0x140020634  xor     edx, edx
0x140020636  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002063b  test    ebx, ebx
0x14002063d  jg      short loc_140020643
0x14002063f  mov     eax, ebx
0x140020641  jmp     short loc_14002064B
0x140020643  movzx   eax, bx
0x140020646  or      eax, 80070000h
0x14002064b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020652  lea     r9, a0; ": {0}"
0x140020659  mov     [rbp+var_30], eax
0x14002065c  mov     r8d, edi
0x14002065f  lea     rax, [rbp+var_30]
0x140020663  mov     qword ptr [rbp+var_20], rax
0x140020667  lea     rax, [rbp+var_20]
0x14002066b  mov     [rsp+60h+PreviousState], rax
0x140020670  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020675  test    ebx, ebx
0x140020677  jz      short loc_140020690
0x140020679  mov     edx, 5Ah ; 'Z'
0x14002067e  jmp     short loc_140020602
0x140020680  test    rsi, rsi
0x140020683  jz      short loc_140020690
0x140020685  mov     [rbp+var_28], 0
0x14002068d  mov     [rsi], rdi
0x140020690  xor     ebx, ebx
0x140020692  lea     rcx, [rbp+var_28]
0x140020696  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x14002069b  lea     rcx, [rbp+TokenHandle]
0x14002069f  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1400206a4  mov     eax, ebx
0x1400206a6  mov     rcx, [rbp+var_8]
0x1400206aa  xor     rcx, rsp; StackCookie
0x1400206ad  call    __security_check_cookie
0x1400206b2  mov     rbx, [rsp+60h+arg_0]
0x1400206ba  add     rsp, 60h
0x1400206be  pop     r15
0x1400206c0  pop     r14
0x1400206c2  pop     rdi
0x1400206c3  pop     rsi
0x1400206c4  pop     rbp
0x1400206c5  retn
```
