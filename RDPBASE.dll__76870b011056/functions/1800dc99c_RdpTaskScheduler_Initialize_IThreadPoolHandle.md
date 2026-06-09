# RdpTaskScheduler::Initialize(IThreadPoolHandle *)

- ea: `0x1800dc99c`
- end: `0x1800dcd1b`
- name: `?Initialize@RdpTaskScheduler@@IEAAJPEAUIThreadPoolHandle@@@Z`
- size: `895`
- prototype: `__int64 __fastcall(PVOID pv, struct IThreadPoolHandle *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800dddd0`
- `0x1800de000`

## callees

- `0x180001aa0`
- `0x1800dc99c`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dca16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcbbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcc73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dca16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcbbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcc73`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800dcc5d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800dcc5d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800dca00`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800dca00`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dcaef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dcaef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800dcba6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800dcba6`

## string_xrefs

- `0x1800dca3a`: `CreateThreadpoolWork failed`
- `0x1800dcb29`: `CreateThreadpoolWork failed`
- `0x1800dca5e`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dcb4d`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dcc04`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dccb7`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dcc93`: `CreateThreadpoolWait failed`
- `0x1800dcbe0`: `CreateThreadpoolTimer failed`

## pseudocode

```c
__int64 __fastcall RdpTaskScheduler::Initialize(_DWORD *pv, struct IThreadPoolHandle *a2)
{
  struct _TP_CALLBACK_ENVIRON_V3 *v2; // rdi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int v6; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ebx
  int *v11; // rdx
  const char **v12; // rax
  PTP_WORK ThreadpoolWork; // rax
  signed int v14; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  signed int v16; // eax
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  const char **v20; // [rsp+40h] [rbp-30h]
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+30h] BYREF
  const char *v26; // [rsp+A8h] [rbp+38h] BYREF

  v2 = (struct _TP_CALLBACK_ENVIRON_V3 *)(pv + 16);
  pv[16] = 3;
  *((_QWORD *)pv + 9) = 0;
  *((_QWORD *)pv + 10) = 0;
  *((_QWORD *)pv + 11) = 0;
  *((_QWORD *)pv + 12) = 0;
  *((_QWORD *)pv + 13) = 0;
  *((_QWORD *)pv + 14) = 0;
  pv[30] = 0;
  pv[31] = 1;
  pv[32] = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)pv + 17) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    if ( a2 )
      *((_QWORD *)pv + 9) = (*(__int64 (__fastcall **)(struct IThreadPoolHandle *))(*(_QWORD *)a2 + 24LL))(a2);
    *((_QWORD *)pv + 10) = *((_QWORD *)pv + 17);
    *((_QWORD *)pv + 11) = 0;
    ThreadpoolWork = CreateThreadpoolWork(RdpTaskScheduler::STATIC_WorkThreadPoolCallback, pv, v2);
    *((_QWORD *)pv + 18) = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(RdpTaskScheduler::STATIC_TimerThreadPoolCallback, pv, v2);
      *((_QWORD *)pv + 19) = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        ThreadpoolWait = CreateThreadpoolWait(RdpTaskScheduler::STATIC_WaitThreadPoolCallback, pv, v2);
        *((_QWORD *)pv + 20) = ThreadpoolWait;
        if ( ThreadpoolWait )
        {
          pv[11] |= 2u;
          return 0;
        }
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v24 = 206;
          v26 = "CreateThreadpoolWait failed";
          v11 = &dword_1801BC35C;
          v23[0] = "Initialize";
          v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
          v21 = "Error condition failed";
          v20 = (const char **)v23;
          v12 = &v21;
          goto LABEL_6;
        }
      }
      else
      {
        v16 = GetLastError();
        v10 = v16;
        if ( v16 > 0 )
          v10 = (unsigned __int16)v16 | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v24 = 200;
          v26 = "CreateThreadpoolTimer failed";
          v11 = &dword_1801BC3AC;
          v23[0] = "Initialize";
          v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
          v21 = "Error condition failed";
          v20 = (const char **)v23;
          v12 = &v21;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v14 = GetLastError();
      v10 = v14;
      if ( v14 > 0 )
        v10 = (unsigned __int16)v14 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v24 = 194;
        v26 = "CreateThreadpoolWork failed";
        v11 = &dword_1801BC3FC;
        v23[0] = "Initialize";
        v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
        v21 = "Error condition failed";
        v20 = (const char **)v23;
        v12 = &v21;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v6 = GetLastError();
    v10 = v6;
    if ( v6 > 0 )
      v10 = (unsigned __int16)v6 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v24 = 179;
      v26 = "CreateThreadpoolWork failed";
      v11 = &dword_1801BC44C;
      v21 = "Initialize";
      v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v23[0] = "Error condition failed";
      v20 = &v21;
      v12 = (const char **)v23;
LABEL_6:
      v25 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v7,
        (_DWORD)v11,
        v8,
        v9,
        (__int64)v12,
        (__int64)&v25,
        (__int64)&v22,
        (__int64)&v24,
        (__int64)v20,
        (__int64)&v26);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800dc99c  mov     [rsp-18h+arg_8], rbx
0x1800dc9a1  push    rbp
0x1800dc9a2  push    rsi
0x1800dc9a3  push    rdi
0x1800dc9a4  mov     rbp, rsp
0x1800dc9a7  sub     rsp, 70h
0x1800dc9ab  lea     rdi, [rcx+40h]
0x1800dc9af  mov     rsi, rdx
0x1800dc9b2  mov     dword ptr [rdi], 3
0x1800dc9b8  mov     rbx, rcx
0x1800dc9bb  mov     qword ptr [rdi+8], 0
0x1800dc9c3  mov     qword ptr [rdi+10h], 0
0x1800dc9cb  mov     qword ptr [rdi+18h], 0
0x1800dc9d3  mov     qword ptr [rdi+20h], 0
0x1800dc9db  mov     qword ptr [rdi+28h], 0
0x1800dc9e3  mov     qword ptr [rdi+30h], 0
0x1800dc9eb  mov     dword ptr [rdi+38h], 0
0x1800dc9f2  mov     dword ptr [rdi+3Ch], 1
0x1800dc9f9  mov     dword ptr [rdi+40h], 48h ; 'H'
0x1800dca00  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800dca06  mov     [rbx+88h], rax
0x1800dca0d  test    rax, rax
0x1800dca10  jnz     loc_1800DCAB7
0x1800dca16  call    cs:__imp_GetLastError
0x1800dca1c  mov     ebx, eax
0x1800dca1e  test    eax, eax
0x1800dca20  jle     short loc_1800DCA2B
0x1800dca22  movzx   ebx, ax
0x1800dca25  or      ebx, 80070000h
0x1800dca2b  mov     eax, cs:CallbackContext
0x1800dca31  cmp     eax, 2
0x1800dca34  jbe     loc_1800DCD09
0x1800dca3a  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x1800dca41  mov     [rbp+arg_0], 0B3h
0x1800dca48  mov     [rbp+arg_18], rax
0x1800dca4c  lea     rdx, dword_1801BC44C
0x1800dca53  lea     rax, aInitialize; "Initialize"
0x1800dca5a  mov     [rbp+var_20], rax
0x1800dca5e  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dca65  mov     [rbp+var_18], rax
0x1800dca69  lea     rax, aErrorCondition; "Error condition failed"
0x1800dca70  mov     [rbp+var_10], rax
0x1800dca74  lea     rax, [rbp+arg_18]
0x1800dca78  mov     [rsp+70h+var_28], rax
0x1800dca7d  lea     rax, [rbp+var_20]
0x1800dca81  mov     [rsp+70h+var_30], rax
0x1800dca86  lea     rax, [rbp+arg_0]
0x1800dca8a  mov     [rsp+70h+var_38], rax
0x1800dca8f  lea     rax, [rbp+var_18]
0x1800dca93  mov     [rsp+70h+var_40], rax
0x1800dca98  lea     rax, [rbp+arg_10]
0x1800dca9c  mov     [rsp+70h+var_48], rax
0x1800dcaa1  lea     rax, [rbp+var_10]
0x1800dcaa5  mov     [rsp+70h+var_50], rax
0x1800dcaaa  mov     [rbp+arg_10], ebx
0x1800dcaad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800dcab2  jmp     loc_1800DCD09
0x1800dcab7  test    rsi, rsi
0x1800dcaba  jz      short loc_1800DCACF
0x1800dcabc  mov     rax, [rsi]
0x1800dcabf  mov     rcx, rsi
0x1800dcac2  mov     rax, [rax+18h]
0x1800dcac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcacb  mov     [rbx+48h], rax
0x1800dcacf  mov     rax, [rbx+88h]
0x1800dcad6  lea     rcx, ?STATIC_WorkThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800dcadd  mov     r8, rdi; pcbe
0x1800dcae0  mov     [rbx+50h], rax
0x1800dcae4  mov     rdx, rbx; pv
0x1800dcae7  mov     qword ptr [rbx+58h], 0
0x1800dcaef  call    cs:__imp_CreateThreadpoolWork
0x1800dcaf5  mov     [rbx+90h], rax
0x1800dcafc  test    rax, rax
0x1800dcaff  jnz     loc_1800DCB99
0x1800dcb05  call    cs:__imp_GetLastError
0x1800dcb0b  mov     ebx, eax
0x1800dcb0d  test    eax, eax
0x1800dcb0f  jle     short loc_1800DCB1A
0x1800dcb11  movzx   ebx, ax
0x1800dcb14  or      ebx, 80070000h
0x1800dcb1a  mov     eax, cs:CallbackContext
0x1800dcb20  cmp     eax, 2
0x1800dcb23  jbe     loc_1800DCD09
0x1800dcb29  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x1800dcb30  mov     [rbp+arg_0], 0C2h
0x1800dcb37  mov     [rbp+arg_18], rax
0x1800dcb3b  lea     rdx, dword_1801BC3FC
0x1800dcb42  lea     rax, aInitialize; "Initialize"
0x1800dcb49  mov     [rbp+var_10], rax
0x1800dcb4d  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dcb54  mov     [rbp+var_18], rax
0x1800dcb58  lea     rax, aErrorCondition; "Error condition failed"
0x1800dcb5f  mov     [rbp+var_20], rax
0x1800dcb63  lea     rax, [rbp+arg_18]
0x1800dcb67  mov     [rsp+70h+var_28], rax
0x1800dcb6c  lea     rax, [rbp+var_10]
0x1800dcb70  mov     [rsp+70h+var_30], rax
0x1800dcb75  lea     rax, [rbp+arg_0]
0x1800dcb79  mov     [rsp+70h+var_38], rax
0x1800dcb7e  lea     rax, [rbp+var_18]
0x1800dcb82  mov     [rsp+70h+var_40], rax
0x1800dcb87  lea     rax, [rbp+arg_10]
0x1800dcb8b  mov     [rsp+70h+var_48], rax
0x1800dcb90  lea     rax, [rbp+var_20]
0x1800dcb94  jmp     loc_1800DCAA5
0x1800dcb99  mov     r8, rdi; pcbe
0x1800dcb9c  lea     rcx, ?STATIC_TimerThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800dcba3  mov     rdx, rbx; pv
0x1800dcba6  call    cs:__imp_CreateThreadpoolTimer
0x1800dcbac  mov     [rbx+98h], rax
0x1800dcbb3  test    rax, rax
0x1800dcbb6  jnz     loc_1800DCC50
0x1800dcbbc  call    cs:__imp_GetLastError
0x1800dcbc2  mov     ebx, eax
0x1800dcbc4  test    eax, eax
0x1800dcbc6  jle     short loc_1800DCBD1
0x1800dcbc8  movzx   ebx, ax
0x1800dcbcb  or      ebx, 80070000h
0x1800dcbd1  mov     eax, cs:CallbackContext
0x1800dcbd7  cmp     eax, 2
0x1800dcbda  jbe     loc_1800DCD09
0x1800dcbe0  lea     rax, aCreatethreadpo_2; "CreateThreadpoolTimer failed"
0x1800dcbe7  mov     [rbp+arg_0], 0C8h
0x1800dcbee  mov     [rbp+arg_18], rax
0x1800dcbf2  lea     rdx, dword_1801BC3AC
0x1800dcbf9  lea     rax, aInitialize; "Initialize"
0x1800dcc00  mov     [rbp+var_10], rax
0x1800dcc04  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dcc0b  mov     [rbp+var_18], rax
0x1800dcc0f  lea     rax, aErrorCondition; "Error condition failed"
0x1800dcc16  mov     [rbp+var_20], rax
0x1800dcc1a  lea     rax, [rbp+arg_18]
0x1800dcc1e  mov     [rsp+70h+var_28], rax
0x1800dcc23  lea     rax, [rbp+var_10]
0x1800dcc27  mov     [rsp+70h+var_30], rax
0x1800dcc2c  lea     rax, [rbp+arg_0]
0x1800dcc30  mov     [rsp+70h+var_38], rax
0x1800dcc35  lea     rax, [rbp+var_18]
0x1800dcc39  mov     [rsp+70h+var_40], rax
0x1800dcc3e  lea     rax, [rbp+arg_10]
0x1800dcc42  mov     [rsp+70h+var_48], rax
0x1800dcc47  lea     rax, [rbp+var_20]
0x1800dcc4b  jmp     loc_1800DCAA5
0x1800dcc50  mov     r8, rdi; pcbe
0x1800dcc53  lea     rcx, ?STATIC_WaitThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x1800dcc5a  mov     rdx, rbx; pv
0x1800dcc5d  call    cs:__imp_CreateThreadpoolWait
0x1800dcc63  mov     [rbx+0A0h], rax
0x1800dcc6a  test    rax, rax
0x1800dcc6d  jnz     loc_1800DCD03
0x1800dcc73  call    cs:__imp_GetLastError
0x1800dcc79  mov     ebx, eax
0x1800dcc7b  test    eax, eax
0x1800dcc7d  jle     short loc_1800DCC88
0x1800dcc7f  movzx   ebx, ax
0x1800dcc82  or      ebx, 80070000h
0x1800dcc88  mov     eax, cs:CallbackContext
0x1800dcc8e  cmp     eax, 2
0x1800dcc91  jbe     short loc_1800DCD09
0x1800dcc93  lea     rax, aCreatethreadpo_0; "CreateThreadpoolWait failed"
0x1800dcc9a  mov     [rbp+arg_0], 0CEh
0x1800dcca1  mov     [rbp+arg_18], rax
0x1800dcca5  lea     rdx, dword_1801BC35C
0x1800dccac  lea     rax, aInitialize; "Initialize"
0x1800dccb3  mov     [rbp+var_10], rax
0x1800dccb7  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dccbe  mov     [rbp+var_18], rax
0x1800dccc2  lea     rax, aErrorCondition; "Error condition failed"
0x1800dccc9  mov     [rbp+var_20], rax
0x1800dcccd  lea     rax, [rbp+arg_18]
0x1800dccd1  mov     [rsp+70h+var_28], rax
0x1800dccd6  lea     rax, [rbp+var_10]
0x1800dccda  mov     [rsp+70h+var_30], rax
0x1800dccdf  lea     rax, [rbp+arg_0]
0x1800dcce3  mov     [rsp+70h+var_38], rax
0x1800dcce8  lea     rax, [rbp+var_18]
0x1800dccec  mov     [rsp+70h+var_40], rax
0x1800dccf1  lea     rax, [rbp+arg_10]
0x1800dccf5  mov     [rsp+70h+var_48], rax
0x1800dccfa  lea     rax, [rbp+var_20]
0x1800dccfe  jmp     loc_1800DCAA5
0x1800dcd03  or      dword ptr [rbx+2Ch], 2
0x1800dcd07  xor     ebx, ebx
0x1800dcd09  mov     eax, ebx
0x1800dcd0b  mov     rbx, [rsp+70h+arg_8]
0x1800dcd13  add     rsp, 70h
0x1800dcd17  pop     rdi
0x1800dcd18  pop     rsi
0x1800dcd19  pop     rbp
0x1800dcd1a  retn
```
