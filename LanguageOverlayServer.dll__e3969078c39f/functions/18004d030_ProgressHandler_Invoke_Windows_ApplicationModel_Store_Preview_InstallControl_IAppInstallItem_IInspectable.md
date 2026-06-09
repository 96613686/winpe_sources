# ProgressHandler::Invoke(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *,IInspectable *)

- ea: `0x18004d030`
- end: `0x18004d430`
- name: `?Invoke@ProgressHandler@@UEAAJPEAUIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(ProgressHandler *__hidden this, struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *, struct IInspectable *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003a00`
- `0x180009084`
- `0x1800120b0`
- `0x18004d030`
- `0x18004f19c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004d176`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004d1a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004d176`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004d1a2`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18004d245`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18004d245`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18004d28b`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18004d28b`
- `msvcp_win!_Mtx_unlock` at `0x18004d2e7`
- `msvcp_win!_Mtx_unlock` at `0x18004d2e7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004d2bc`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004d2d8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004d2bc`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004d2d8`
- `msvcp_win!_Mtx_lock` at `0x18004d2ad`
- `msvcp_win!_Mtx_lock` at `0x18004d2ad`

## string_xrefs

- `0x18004d07e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004d0d5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004d12c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004d1ee`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004d25c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004d299`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004d352`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004d3aa`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProgressHandler::Invoke(
        HANDLE *this,
        struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *a2,
        struct IInspectable *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int *v12; // rdx
  BOOL v13; // eax
  const char *v14; // r9
  wil::details::in1diag3 *v15; // rcx
  __int64 v16; // rdx
  BOOL v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  BOOL v20; // eax
  unsigned int v21; // r14d
  const char *v22; // r9
  HANDLE v23; // rbx
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // esi
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  int lpArgToCompletionRoutine; // [rsp+20h] [rbp-40h]
  __int64 v32; // [rsp+30h] [rbp-30h] BYREF
  int v33; // [rsp+38h] [rbp-28h] BYREF
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp-20h] BYREF
  double v35; // [rsp+48h] [rbp-18h] BYREF
  __int64 v36; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v32 = 0;
  v4 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *, __int64 *))(*(_QWORD *)a2 + 80LL))(
         a2,
         &v32);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v4,
      lpArgToCompletionRoutine);
    v6 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v5;
  }
  v33 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 48LL))(v32, &v33);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v8,
      lpArgToCompletionRoutine);
    v9 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v5;
  }
  v35 = 0.0;
  v10 = (*(__int64 (__fastcall **)(__int64, double *))(*(_QWORD *)v32 + 72LL))(v32, &v35);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v10,
      lpArgToCompletionRoutine);
    v11 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v5;
  }
  v12 = (int *)(this + 25);
  if ( v33 == 6 )
  {
    *v12 = 0;
    v13 = SetEvent(this[23]);
    v15 = retaddr;
    if ( !v13 )
    {
      v16 = 70;
LABEL_26:
      wil::details::in1diag3::_Log_GetLastError(
        v15,
        (void *)v16,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
        v14);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  if ( v33 != 7 )
  {
    if ( v33 == 9 )
    {
      *((_DWORD *)this + 51) = (int)v35;
      v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 80LL))(v32, v12);
      v5 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v18,
          lpArgToCompletionRoutine);
        v19 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        return v5;
      }
      DueTime.QuadPart = -1200000000;
      v20 = SetWaitableTimer(this[24], &DueTime, 0, 0, 0, 1);
      v15 = retaddr;
      if ( v20 )
        goto LABEL_55;
      v16 = 184;
      goto LABEL_26;
    }
    v21 = (int)v35;
    if ( *v12 < 0 && v21 > *((_DWORD *)this + 51) )
    {
      *v12 = 0;
      if ( !CancelWaitableTimer(this[24]) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
          v22);
    }
    if ( _Mtx_lock((_Mtx_t)(this + 2)) )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    if ( *((_DWORD *)this + 23) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 23) = 2147483646;
      std::_Throw_Cpp_error(6);
      __debugbreak();
    }
    v23 = this[12];
    _Mtx_unlock((_Mtx_t)(this + 2));
    if ( !v23 )
      goto LABEL_55;
    if ( v33 )
    {
      switch ( v33 )
      {
        case 1:
        case 2:
          v24 = 1;
          goto LABEL_46;
        case 3:
        case 4:
          v24 = 2;
          goto LABEL_46;
        case 5:
          v24 = 3;
          goto LABEL_46;
      }
    }
    v24 = 0;
LABEL_46:
    DueTime.QuadPart = 0;
    v25 = (*(__int64 (__fastcall **)(__int64, LARGE_INTEGER *))(*(_QWORD *)v32 + 64LL))(v32, &DueTime);
    v26 = v25;
    if ( v25 >= 0 )
    {
      v36 = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 56LL))(v32, &v36);
      v26 = v28;
      if ( v28 >= 0 )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProgressHandler::_NotifyProgressChanged)(
          this,
          v21,
          v24,
          (LARGE_INTEGER)DueTime.QuadPart,
          v36);
        goto LABEL_55;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v28,
        lpArgToCompletionRoutine);
      v29 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v25,
        lpArgToCompletionRoutine);
      v27 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
    }
    return v26;
  }
  *v12 = -2147467260;
  v17 = SetEvent(this[23]);
  v15 = retaddr;
  if ( !v17 )
  {
    v16 = 75;
    goto LABEL_26;
  }
LABEL_55:
  v30 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  return 0;
}

```

## disassembly

```asm
0x18004d030  mov     [rsp-28h+arg_10], rbx
0x18004d035  push    rbp
0x18004d036  push    rsi
0x18004d037  push    rdi
0x18004d038  push    r14
0x18004d03a  push    r15
0x18004d03c  mov     rbp, rsp
0x18004d03f  sub     rsp, 60h
0x18004d043  mov     rax, cs:__security_cookie
0x18004d04a  xor     rax, rsp
0x18004d04d  mov     [rbp+var_8], rax
0x18004d051  mov     r8, rdx
0x18004d054  mov     rdi, rcx
0x18004d057  xor     r15d, r15d
0x18004d05a  mov     [rbp+var_30], r15
0x18004d05e  mov     rax, [rdx]
0x18004d061  lea     rdx, [rbp+var_30]
0x18004d065  mov     rcx, r8
0x18004d068  mov     rax, [rax+50h]
0x18004d06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d071  mov     ebx, eax
0x18004d073  test    eax, eax
0x18004d075  jns     short loc_18004D0B0
0x18004d077  mov     rcx, [rbp+28h]; this
0x18004d07b  mov     r9d, eax; char *
0x18004d07e  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004d085  lea     edx, [r15+3Bh]; void *
0x18004d089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d08e  nop
0x18004d08f  mov     rcx, [rbp+var_30]
0x18004d093  test    rcx, rcx
0x18004d096  jz      short loc_18004D0A9
0x18004d098  mov     [rbp+var_30], r15
0x18004d09c  mov     rax, [rcx]
0x18004d09f  mov     rax, [rax+10h]
0x18004d0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0a8  nop
0x18004d0a9  mov     eax, ebx
0x18004d0ab  jmp     loc_18004D410
0x18004d0b0  mov     [rbp+var_28], r15d
0x18004d0b4  mov     rcx, [rbp+var_30]
0x18004d0b8  mov     rax, [rcx]
0x18004d0bb  lea     rdx, [rbp+var_28]
0x18004d0bf  mov     rax, [rax+30h]
0x18004d0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0c8  mov     ebx, eax
0x18004d0ca  test    eax, eax
0x18004d0cc  jns     short loc_18004D103
0x18004d0ce  mov     rcx, [rbp+28h]; this
0x18004d0d2  mov     r9d, eax; char *
0x18004d0d5  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004d0dc  mov     edx, 3Eh ; '>'; void *
0x18004d0e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d0e6  nop
0x18004d0e7  mov     rcx, [rbp+var_30]
0x18004d0eb  test    rcx, rcx
0x18004d0ee  jz      short loc_18004D101
0x18004d0f0  mov     [rbp+var_30], r15
0x18004d0f4  mov     rax, [rcx]
0x18004d0f7  mov     rax, [rax+10h]
0x18004d0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d100  nop
0x18004d101  jmp     short loc_18004D0A9
0x18004d103  xorps   xmm0, xmm0
0x18004d106  movsd   [rbp+var_18], xmm0
0x18004d10b  mov     rcx, [rbp+var_30]
0x18004d10f  mov     rax, [rcx]
0x18004d112  lea     rdx, [rbp+var_18]
0x18004d116  mov     rax, [rax+48h]
0x18004d11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d11f  mov     ebx, eax
0x18004d121  test    eax, eax
0x18004d123  jns     short loc_18004D15D
0x18004d125  mov     rcx, [rbp+28h]; this
0x18004d129  mov     r9d, eax; char *
0x18004d12c  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004d133  mov     edx, 41h ; 'A'; void *
0x18004d138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d13d  nop
0x18004d13e  mov     rcx, [rbp+var_30]
0x18004d142  test    rcx, rcx
0x18004d145  jz      short loc_18004D158
0x18004d147  mov     [rbp+var_30], r15
0x18004d14b  mov     rax, [rcx]
0x18004d14e  mov     rax, [rax+10h]
0x18004d152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d157  nop
0x18004d158  jmp     loc_18004D0A9
0x18004d15d  lea     rdx, [rdi+0C8h]
0x18004d164  mov     eax, [rbp+var_28]
0x18004d167  cmp     eax, 6
0x18004d16a  jnz     short loc_18004D190
0x18004d16c  mov     [rdx], r15d
0x18004d16f  mov     rcx, [rdi+0B8h]; hEvent
0x18004d176  call    cs:__imp_SetEvent
0x18004d17c  mov     rcx, [rbp+28h]
0x18004d180  test    eax, eax
0x18004d182  jnz     loc_18004D3F4
0x18004d188  lea     edx, [rax+46h]
0x18004d18b  jmp     loc_18004D25C
0x18004d190  cmp     eax, 7
0x18004d193  jnz     short loc_18004D1BC
0x18004d195  mov     dword ptr [rdx], 80004004h
0x18004d19b  mov     rcx, [rdi+0B8h]; hEvent
0x18004d1a2  call    cs:__imp_SetEvent
0x18004d1a8  mov     rcx, [rbp+28h]
0x18004d1ac  test    eax, eax
0x18004d1ae  jnz     loc_18004D3F4
0x18004d1b4  lea     edx, [rax+4Bh]
0x18004d1b7  jmp     loc_18004D25C
0x18004d1bc  cmp     eax, 9
0x18004d1bf  jnz     loc_18004D26D
0x18004d1c5  cvttsd2si rax, [rbp+var_18]
0x18004d1cb  mov     [rdi+0CCh], eax
0x18004d1d1  mov     rcx, [rbp+var_30]
0x18004d1d5  mov     rax, [rcx]
0x18004d1d8  mov     rax, [rax+50h]
0x18004d1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1e1  mov     ebx, eax
0x18004d1e3  test    eax, eax
0x18004d1e5  jns     short loc_18004D21F
0x18004d1e7  mov     rcx, [rbp+28h]; this
0x18004d1eb  mov     r9d, eax; char *
0x18004d1ee  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004d1f5  mov     edx, 51h ; 'Q'; void *
0x18004d1fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d1ff  nop
0x18004d200  mov     rcx, [rbp+var_30]
0x18004d204  test    rcx, rcx
0x18004d207  jz      short loc_18004D21A
0x18004d209  mov     [rbp+var_30], r15
0x18004d20d  mov     rax, [rcx]
0x18004d210  mov     rax, [rax+10h]
0x18004d214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d219  nop
0x18004d21a  jmp     loc_18004D0A9
0x18004d21f  mov     qword ptr [rbp+DueTime], 0FFFFFFFFB8797400h
0x18004d227  mov     [rsp+60h+fResume], 1; fResume
0x18004d22f  mov     [rsp+60h+lpArgToCompletionRoutine], r15; lpArgToCompletionRoutine
0x18004d234  xor     r9d, r9d; pfnCompletionRoutine
0x18004d237  xor     r8d, r8d; lPeriod
0x18004d23a  lea     rdx, [rbp+DueTime]; lpDueTime
0x18004d23e  mov     rcx, [rdi+0C0h]; hTimer
0x18004d245  call    cs:__imp_SetWaitableTimer
0x18004d24b  mov     rcx, [rbp+28h]; this
0x18004d24f  test    eax, eax
0x18004d251  jnz     loc_18004D3F4
0x18004d257  mov     edx, 0B8h; void *
0x18004d25c  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004d263  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18004d268  jmp     loc_18004D3F4
0x18004d26d  cvttsd2si r14, [rbp+var_18]
0x18004d273  cmp     [rdx], r15d
0x18004d276  jge     short loc_18004D2A9
0x18004d278  cmp     r14d, [rdi+0CCh]
0x18004d27f  jbe     short loc_18004D2A9
0x18004d281  mov     [rdx], r15d
0x18004d284  mov     rcx, [rdi+0C0h]; hTimer
0x18004d28b  call    cs:__imp_CancelWaitableTimer
0x18004d291  mov     rcx, [rbp+28h]; this
0x18004d295  test    eax, eax
0x18004d297  jnz     short loc_18004D2A9
0x18004d299  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004d2a0  lea     edx, [rax+5Ch]; void *
0x18004d2a3  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18004d2a8  nop
0x18004d2a9  lea     rcx, [rdi+10h]; _Mtx_t
0x18004d2ad  call    cs:__imp__Mtx_lock
0x18004d2b3  test    eax, eax
0x18004d2b5  jz      short loc_18004D2C3
0x18004d2b7  mov     ecx, 5
0x18004d2bc  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004d2c2  int     3; Trap to Debugger
0x18004d2c3  cmp     dword ptr [rdi+5Ch], 7FFFFFFFh
0x18004d2ca  jnz     short loc_18004D2DF
0x18004d2cc  mov     dword ptr [rdi+5Ch], 7FFFFFFEh
0x18004d2d3  mov     ecx, 6
0x18004d2d8  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004d2de  int     3; Trap to Debugger
0x18004d2df  mov     rbx, [rdi+60h]
0x18004d2e3  lea     rcx, [rdi+10h]; _Mtx_t
0x18004d2e7  call    cs:__imp__Mtx_unlock
0x18004d2ed  nop
0x18004d2ee  test    rbx, rbx
0x18004d2f1  jz      loc_18004D3F4
0x18004d2f7  mov     ecx, [rbp+var_28]
0x18004d2fa  test    ecx, ecx
0x18004d2fc  jz      short loc_18004D32A
0x18004d2fe  sub     ecx, 1
0x18004d301  jz      short loc_18004D323
0x18004d303  sub     ecx, 1
0x18004d306  jz      short loc_18004D323
0x18004d308  sub     ecx, 1
0x18004d30b  jz      short loc_18004D31C
0x18004d30d  sub     ecx, 1
0x18004d310  jz      short loc_18004D31C
0x18004d312  cmp     ecx, 1
0x18004d315  jnz     short loc_18004D32A
0x18004d317  lea     ebx, [rcx+2]
0x18004d31a  jmp     short loc_18004D32D
0x18004d31c  mov     ebx, 2
0x18004d321  jmp     short loc_18004D32D
0x18004d323  mov     ebx, 1
0x18004d328  jmp     short loc_18004D32D
0x18004d32a  mov     ebx, r15d
0x18004d32d  mov     qword ptr [rbp+DueTime], r15
0x18004d331  mov     rcx, [rbp+var_30]
0x18004d335  mov     rax, [rcx]
0x18004d338  lea     rdx, [rbp+DueTime]
0x18004d33c  mov     rax, [rax+40h]
0x18004d340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d345  mov     esi, eax
0x18004d347  test    eax, eax
0x18004d349  jns     short loc_18004D385
0x18004d34b  mov     rcx, [rbp+28h]; this
0x18004d34f  mov     r9d, eax; char *
0x18004d352  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004d359  mov     edx, 64h ; 'd'; void *
0x18004d35e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d363  nop
0x18004d364  mov     rcx, [rbp+var_30]
0x18004d368  test    rcx, rcx
0x18004d36b  jz      short loc_18004D37E
0x18004d36d  mov     [rbp+var_30], r15
0x18004d371  mov     rax, [rcx]
0x18004d374  mov     rax, [rax+10h]
0x18004d378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d37d  nop
0x18004d37e  mov     eax, esi
0x18004d380  jmp     loc_18004D410
0x18004d385  mov     [rbp+var_10], r15
0x18004d389  mov     rcx, [rbp+var_30]
0x18004d38d  mov     rax, [rcx]
0x18004d390  lea     rdx, [rbp+var_10]
0x18004d394  mov     rax, [rax+38h]
0x18004d398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d39d  mov     esi, eax
0x18004d39f  test    eax, eax
0x18004d3a1  jns     short loc_18004D3D8
0x18004d3a3  mov     rcx, [rbp+28h]; this
0x18004d3a7  mov     r9d, eax; char *
0x18004d3aa  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004d3b1  mov     edx, 67h ; 'g'; void *
0x18004d3b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d3bb  nop
0x18004d3bc  mov     rcx, [rbp+var_30]
0x18004d3c0  test    rcx, rcx
0x18004d3c3  jz      short loc_18004D3D6
0x18004d3c5  mov     [rbp+var_30], r15
0x18004d3c9  mov     rax, [rcx]
0x18004d3cc  mov     rax, [rax+10h]
0x18004d3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3d5  nop
0x18004d3d6  jmp     short loc_18004D37E
0x18004d3d8  mov     rax, [rbp+var_10]
0x18004d3dc  mov     [rsp+60h+lpArgToCompletionRoutine], rax
0x18004d3e1  mov     r9, qword ptr [rbp+DueTime]
0x18004d3e5  mov     r8d, ebx
0x18004d3e8  mov     edx, r14d
0x18004d3eb  mov     rcx, rdi
0x18004d3ee  call    ?_NotifyProgressChanged@ProgressHandler@@AEAAXIW4LanguagePackInstallProgressState@@_K1@Z; ProgressHandler::_NotifyProgressChanged(uint,LanguagePackInstallProgressState,unsigned __int64,unsigned __int64)
0x18004d3f3  nop
0x18004d3f4  mov     rcx, [rbp+var_30]
0x18004d3f8  test    rcx, rcx
0x18004d3fb  jz      short loc_18004D40E
0x18004d3fd  mov     [rbp+var_30], r15
0x18004d401  mov     rax, [rcx]
0x18004d404  mov     rax, [rax+10h]
0x18004d408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d40d  nop
0x18004d40e  xor     eax, eax
0x18004d410  mov     rcx, [rbp+var_8]
0x18004d414  xor     rcx, rsp; StackCookie
0x18004d417  call    __security_check_cookie
0x18004d41c  mov     rbx, [rsp+60h+arg_10]
0x18004d424  add     rsp, 60h
0x18004d428  pop     r15
0x18004d42a  pop     r14
0x18004d42c  pop     rdi
0x18004d42d  pop     rsi
0x18004d42e  pop     rbp
0x18004d42f  retn
```
