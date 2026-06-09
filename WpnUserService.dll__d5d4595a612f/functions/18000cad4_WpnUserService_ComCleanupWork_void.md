# WpnUserService::_ComCleanupWork(void)

- ea: `0x18000cad4`
- end: `0x18000ce02`
- name: `?_ComCleanupWork@WpnUserService@@AEAAXXZ`
- size: `814`
- prototype: `void __fastcall(WpnUserService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a450`

## callees

- `0x180001008`
- `0x1800052d8`
- `0x1800071a8`
- `0x18000a648`
- `0x18000c23c`
- `0x18000cad4`
- `0x18000ce08`
- `0x18000ce58`
- `0x18000cea4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000cba1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000cba1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cd76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cd76`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000cc71`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000cc71`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000cc7a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000cc7a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cdb7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cdb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cda0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cda0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cdae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cdae`

## string_xrefs

- `0x18000cb51`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000cd38`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`

## pseudocode

```c
void __fastcall WpnUserService::_ComCleanupWork(WpnUserService *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, HANDLE *); // rcx
  int v3; // eax
  unsigned int v4; // r8d
  int v5; // eax
  HANDLE v6; // rcx
  void *v7; // rbx
  wil::details *v8; // rcx
  HANDLE Event; // rdi
  unsigned int v10; // r8d
  int LastErrorFailHr; // eax
  __int64 *v12; // r15
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  void *v16; // rdx
  unsigned int v17; // r8d
  const char *v18; // r9
  struct _TP_WORK *v19; // r14
  DWORD LastError; // edi
  __int64 v21; // rcx
  const struct _tlgProvider_t *v22; // rax
  __int64 v23; // rdx
  int v24; // r9d
  const struct _tlgProvider_t *v25; // r8
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rcx
  struct _TP_TIMER *v29; // rbx
  __int64 v30; // [rsp+0h] [rbp-98h] BYREF
  int v31[2]; // [rsp+20h] [rbp-78h]
  __int64 v32; // [rsp+28h] [rbp-70h]
  _QWORD v33[2]; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v34[9]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  HANDLE v36; // [rsp+A8h] [rbp+10h] BYREF
  char *v37; // [rsp+B0h] [rbp+18h] BYREF
  PTP_TIMER pti; // [rsp+B8h] [rbp+20h]

  try
  {
    StartMethodExecutionTimeout();
    v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, HANDLE *))*((_QWORD *)this + 28);
    if ( v2 )
    {
      v36 = 0;
      v3 = (**v2)(v2, &GUID_6d8eaf9b_de6c_480d_82b5_d46c3aa90d12, &v36);
      if ( v3 < 0 )
        wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x108, v4, (const char *)(unsigned int)v3, v31[0]);
      v5 = (*(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)v36 + 40LL))(v36);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x109,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
          (const char *)(unsigned int)v5,
          v31[0]);
      v6 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
    v7 = 0;
    v36 = 0;
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      v7 = Event;
      v36 = Event;
      LastErrorFailHr = 0;
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v8);
    }
    if ( LastErrorFailHr < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10D,
        v10,
        (const char *)(unsigned int)LastErrorFailHr,
        v31[0]);
    v34[0] = v7;
    v34[1] = (char *)this + 200;
    v12 = (__int64 *)((char *)this + 216);
    v34[2] = (char *)this + 216;
    v34[3] = this;
    v33[0] = 0;
    v33[1] = v34;
    v13 = (__int64 *)*((_QWORD *)this + 24);
    v14 = *v13;
    v32 = 0;
    v31[0] = 5;
    v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall *)(struct tagComCallData *), _QWORD *, GUID *))(v14 + 24))(
            v13,
            WpnUserService::RevokeClassFactoryCallback,
            v33,
            &IID_IContextCallback);
    if ( v15 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v16, v17, (const char *)(unsigned int)v15, v31[0]);
    v19 = (struct _TP_WORK *)*((_QWORD *)this + 29);
    if ( v19 )
    {
      LastError = GetLastError();
      WaitForThreadpoolWorkCallbacks(v19, 1);
      CloseThreadpoolWork(v19);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 29) = 0;
    v21 = *v12;
    if ( *v12 )
    {
      *v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    if ( *((_QWORD *)this + 28) )
    {
      v22 = ServiceHostLogging::Provider();
      v25 = v22;
      if ( *(_DWORD *)v22 > 5u )
      {
        v26 = *((_QWORD *)v22 + 3);
        v23 = 0x400000000000LL;
        if ( (*((_QWORD *)v25 + 2) & 0x400000000000LL) != 0 && (v26 & 0x400000000000LL) == v26 )
        {
          v37 = (char *)this + 8;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v25,
            (unsigned int)word_180014A8A,
            (_DWORD)v25,
            v24,
            (__int64)&v37);
        }
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, const struct _tlgProvider_t *))(**((_QWORD **)this + 28) + 72LL))(
              *((_QWORD *)this + 28),
              v23,
              v25);
      if ( v27 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x127,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
          (const char *)(unsigned int)v27,
          v31[0]);
      v28 = *((_QWORD *)this + 28);
      if ( v28 )
      {
        *((_QWORD *)this + 28) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    if ( v7 && !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    v29 = pti;
    if ( pti )
    {
      SetThreadpoolTimer(pti, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v29, 1);
      CloseThreadpoolTimer(v29);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, &v30, v17, v18);
  }
}

```

## disassembly

```asm
0x18000cad4  mov     rax, rsp
0x18000cad7  push    rbx
0x18000cad8  push    rsi
0x18000cad9  push    rdi
0x18000cada  push    r14
0x18000cadc  push    r15
0x18000cade  sub     rsp, 70h
0x18000cae2  mov     rsi, rcx
0x18000cae5  lea     rcx, [rax+20h]
0x18000cae9  call    ?StartMethodExecutionTimeout@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; StartMethodExecutionTimeout(void)
0x18000caee  nop
0x18000caef  mov     rcx, [rsi+0E0h]
0x18000caf6  test    rcx, rcx
0x18000caf9  jz      loc_18000CB89
0x18000caff  mov     [rsp+98h+arg_8], 0
0x18000cb0b  mov     rax, [rcx]
0x18000cb0e  lea     r8, [rsp+98h+arg_8]
0x18000cb16  lea     rdx, _GUID_6d8eaf9b_de6c_480d_82b5_d46c3aa90d12
0x18000cb1d  mov     rax, [rax]
0x18000cb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb25  nop
0x18000cb26  test    eax, eax
0x18000cb28  js      loc_18000CDCA
0x18000cb2e  mov     rcx, [rsp+98h+arg_8]
0x18000cb36  mov     rax, [rcx]
0x18000cb39  mov     rax, [rax+28h]
0x18000cb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb42  mov     rcx, [rsp+98h]; this
0x18000cb4a  test    eax, eax
0x18000cb4c  jns     short loc_18000CB63
0x18000cb4e  mov     r9d, eax; char *
0x18000cb51  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000cb58  mov     edx, 109h; void *
0x18000cb5d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000cb62  nop
0x18000cb63  mov     rcx, [rsp+98h+arg_8]
0x18000cb6b  test    rcx, rcx
0x18000cb6e  jz      short loc_18000CB89
0x18000cb70  mov     [rsp+98h+arg_8], 0
0x18000cb7c  mov     rax, [rcx]
0x18000cb7f  mov     rax, [rax+10h]
0x18000cb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb88  nop
0x18000cb89  xor     ebx, ebx
0x18000cb8b  mov     [rsp+98h+arg_8], rbx
0x18000cb93  xor     edx, edx; lpName
0x18000cb95  xor     ecx, ecx; lpEventAttributes
0x18000cb97  mov     r9d, 1F0003h; dwDesiredAccess
0x18000cb9d  lea     r8d, [rbx+1]; dwFlags
0x18000cba1  call    cs:__imp_CreateEventExW
0x18000cba7  mov     rdi, rax
0x18000cbaa  test    rax, rax
0x18000cbad  jz      short loc_18000CBC4
0x18000cbaf  call    cs:__imp_GetLastError
0x18000cbb5  mov     rbx, rdi
0x18000cbb8  mov     [rsp+98h+arg_8], rbx
0x18000cbc0  xor     eax, eax
0x18000cbc2  jmp     short loc_18000CBC9
0x18000cbc4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000cbc9  mov     rcx, [rsp+98h]; this
0x18000cbd1  test    eax, eax
0x18000cbd3  js      loc_18000CDE0
0x18000cbd9  mov     [rsp+98h+var_48], rbx
0x18000cbde  lea     rax, [rsi+0C8h]
0x18000cbe5  mov     [rsp+98h+var_40], rax
0x18000cbea  lea     r15, [rsi+0D8h]
0x18000cbf1  mov     [rsp+98h+var_38], r15
0x18000cbf6  mov     [rsp+98h+var_30], rsi
0x18000cbfb  mov     [rsp+98h+var_58], 0
0x18000cc04  lea     rax, [rsp+98h+var_48]
0x18000cc09  mov     [rsp+98h+var_50], rax
0x18000cc0e  mov     rcx, [rsi+0C0h]
0x18000cc15  mov     rax, [rcx]
0x18000cc18  mov     [rsp+98h+var_70], 0
0x18000cc21  mov     [rsp+98h+var_78], 5; int
0x18000cc29  lea     r9, IID_IContextCallback
0x18000cc30  lea     r8, [rsp+98h+var_58]
0x18000cc35  lea     rdx, ?RevokeClassFactoryCallback@WpnUserService@@SAJPEAUtagComCallData@@@Z; WpnUserService::RevokeClassFactoryCallback(tagComCallData *)
0x18000cc3c  mov     rax, [rax+18h]
0x18000cc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc45  mov     rcx, [rsp+98h]; this
0x18000cc4d  test    eax, eax
0x18000cc4f  js      loc_18000CDED
0x18000cc55  mov     r14, [rsi+0E8h]
0x18000cc5c  test    r14, r14
0x18000cc5f  jz      short loc_18000CC88
0x18000cc61  call    cs:__imp_GetLastError
0x18000cc67  mov     edi, eax
0x18000cc69  mov     edx, 1; fCancelPendingCallbacks
0x18000cc6e  mov     rcx, r14; pwk
0x18000cc71  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000cc77  mov     rcx, r14; pwk
0x18000cc7a  call    cs:__imp_CloseThreadpoolWork
0x18000cc80  mov     ecx, edi; dwErrCode
0x18000cc82  call    cs:__imp_SetLastError
0x18000cc88  mov     qword ptr [rsi+0E8h], 0
0x18000cc93  mov     rcx, [r15]
0x18000cc96  test    rcx, rcx
0x18000cc99  jz      short loc_18000CCAF
0x18000cc9b  mov     qword ptr [r15], 0
0x18000cca2  mov     rax, [rcx]
0x18000cca5  mov     rax, [rax+10h]
0x18000cca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccae  nop
0x18000ccaf  cmp     qword ptr [rsi+0E0h], 0
0x18000ccb7  jz      loc_18000CD6E
0x18000ccbd  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000ccc2  mov     r8, rax
0x18000ccc5  mov     ecx, [rax]
0x18000ccc7  cmp     ecx, 5
0x18000ccca  jbe     short loc_18000CD16
0x18000cccc  mov     rax, [rax+18h]
0x18000ccd0  mov     rcx, [r8+10h]
0x18000ccd4  mov     rdx, 400000000000h
0x18000ccde  test    rdx, rcx
0x18000cce1  jz      short loc_18000CD16
0x18000cce3  mov     rcx, rax
0x18000cce6  and     rcx, rdx
0x18000cce9  cmp     rcx, rax
0x18000ccec  jnz     short loc_18000CD16
0x18000ccee  lea     rax, [rsi+8]
0x18000ccf2  mov     [rsp+98h+arg_10], rax
0x18000ccfa  lea     rax, [rsp+98h+arg_10]
0x18000cd02  mov     qword ptr [rsp+98h+var_78], rax; int
0x18000cd07  lea     rdx, word_180014A8A
0x18000cd0e  mov     rcx, r8
0x18000cd11  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000cd16  mov     rcx, [rsi+0E0h]
0x18000cd1d  mov     rax, [rcx]
0x18000cd20  mov     rax, [rax+48h]
0x18000cd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd29  mov     rcx, [rsp+98h]; this
0x18000cd31  test    eax, eax
0x18000cd33  jns     short loc_18000CD4A
0x18000cd35  mov     r9d, eax; char *
0x18000cd38  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000cd3f  mov     edx, 127h; void *
0x18000cd44  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000cd49  nop
0x18000cd4a  mov     rcx, [rsi+0E0h]
0x18000cd51  test    rcx, rcx
0x18000cd54  jz      short loc_18000CD6E
0x18000cd56  mov     qword ptr [rsi+0E0h], 0
0x18000cd61  mov     rax, [rcx]
0x18000cd64  mov     rax, [rax+10h]
0x18000cd68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd6d  nop
0x18000cd6e  test    rbx, rbx
0x18000cd71  jz      short loc_18000CD88
0x18000cd73  mov     rcx, rbx; hObject
0x18000cd76  call    cs:__imp_CloseHandle
0x18000cd7c  mov     rcx, [rsp+98h]; this
0x18000cd84  test    eax, eax
0x18000cd86  jz      short loc_18000CDF6
0x18000cd88  mov     rbx, [rsp+98h+pti]
0x18000cd90  test    rbx, rbx
0x18000cd93  jz      short loc_18000CDBE
0x18000cd95  xor     r9d, r9d; msWindowLength
0x18000cd98  xor     r8d, r8d; msPeriod
0x18000cd9b  xor     edx, edx; pftDueTime
0x18000cd9d  mov     rcx, rbx; pti
0x18000cda0  call    cs:__imp_SetThreadpoolTimer
0x18000cda6  mov     edx, 1; fCancelPendingCallbacks
0x18000cdab  mov     rcx, rbx; pti
0x18000cdae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cdb4  mov     rcx, rbx; pti
0x18000cdb7  call    cs:__imp_CloseThreadpoolTimer
0x18000cdbd  nop
0x18000cdbe  add     rsp, 70h
0x18000cdc2  pop     r15
0x18000cdc4  pop     r14
0x18000cdc6  pop     rdi
0x18000cdc7  pop     rsi
0x18000cdc8  pop     rbx
0x18000cdc9  retn
0x18000cdca  mov     rcx, [rsp+98h]; this
0x18000cdd2  mov     r9d, eax; char *
0x18000cdd5  mov     edx, 108h; void *
0x18000cdda  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cde0  mov     r9d, eax; char *
0x18000cde3  mov     edx, 10Dh; void *
0x18000cde8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cded  mov     r9d, eax; char *
0x18000cdf0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000cdf6  mov     edx, 0A0Bh; void *
0x18000cdfb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
