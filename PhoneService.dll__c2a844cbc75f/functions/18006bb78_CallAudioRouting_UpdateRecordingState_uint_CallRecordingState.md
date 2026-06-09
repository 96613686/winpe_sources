# CallAudioRouting::_UpdateRecordingState(uint,CallRecordingState)

- ea: `0x18006bb78`
- end: `0x18006c05d`
- name: `?_UpdateRecordingState@CallAudioRouting@@AEAAJIW4CallRecordingState@@@Z`
- size: `1253`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005c000`
- `0x18005c2d8`
- `0x18005c5b0`
- `0x18005c7dc`
- `0x18005ca30`
- `0x18005e600`
- `0x18005f650`
- `0x18005f730`
- `0x18005f810`
- `0x180060380`
- `0x180061800`
- `0x180064f80`
- `0x180065238`
- `0x180068010`
- `0x180068cc0`
- `0x180069e40`

## callees

- `0x1800042b0`
- `0x180006e94`
- `0x180057fcc`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x180064dac`
- `0x18006bb78`
- `0x18007f9ec`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006bbdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006bbdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bc24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bda4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006be62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bc24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bda4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006be62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006bba4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006bbc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006bba4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006bbc9`

## string_xrefs

- `0x18006bbbd`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006bc11`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006bd86`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006bfc4`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_UpdateRecordingState(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v6; // rcx
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  BackTraceCollection *v8; // rcx
  struct CallAudioRouting::CellularAudioState *v10; // rdx
  const char *v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // rsi
  __int64 v14; // r14
  __int64 v15; // r15
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // r12d
  bool v24; // zf
  unsigned int v25; // eax
  bool v26; // zf
  struct CallAudioRouting::CellularAudioState *v27; // r8
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  BackTraceCollection *v31; // rcx
  unsigned int v32; // r12d
  unsigned int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  unsigned int v37; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v38; // [rsp+48h] [rbp-38h] BYREF
  int v39; // [rsp+50h] [rbp-30h] BYREF
  struct CallAudioRouting::CellularAudioState *v40; // [rsp+58h] [rbp-28h] BYREF
  const char *v41; // [rsp+60h] [rbp-20h] BYREF
  int v42; // [rsp+68h] [rbp-18h]
  struct CallAudioRouting::CellularAudioState *v43; // [rsp+70h] [rbp-10h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-8h]

  v37 = a2;
  v43 = (struct CallAudioRouting::CellularAudioState *)a1;
  v38 = a2;
  v7 = (struct _RTL_CRITICAL_SECTION *)(a1 + 88);
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 88);
  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1518);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v40 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState((CallAudioRouting *)a1, a2, &v40) )
  {
    BackTraceCollection::Capture(v8, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1524);
    LeaveCriticalSection(v7);
    return 2147943568LL;
  }
  v10 = v40;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = *((_DWORD *)v40 + 8);
  v39 = v16;
  if ( !v16 )
  {
    v33 = a3 - 1;
    goto LABEL_44;
  }
  v17 = v16 - 2;
  if ( !v17 )
  {
    v23 = 0;
    v24 = a3 == 3;
    goto LABEL_41;
  }
  v18 = v17 - 1;
  if ( !v18 )
  {
    v25 = a3 - 2;
    goto LABEL_16;
  }
  v19 = v18 - 1;
  if ( v19 )
  {
    v20 = v19 - 1;
    if ( !v20 )
    {
LABEL_15:
      v25 = a3 - 4;
LABEL_16:
      v26 = (v25 & 0xFFFFFFFD) == 0;
      goto LABEL_17;
    }
    v21 = v20 - 1;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = 0;
        if ( v22 != 1 )
          goto LABEL_47;
        v24 = a3 == 2;
LABEL_41:
        LOBYTE(v23) = v24;
        if ( !v23 )
          goto LABEL_47;
        goto LABEL_19;
      }
      goto LABEL_15;
    }
    v33 = a3 - 7;
LABEL_44:
    if ( v33 <= 1 )
      goto LABEL_18;
LABEL_45:
    v23 = 0;
    goto LABEL_47;
  }
  if ( a3 == 5 )
    goto LABEL_18;
  v26 = a3 == 8;
LABEL_17:
  if ( !v26 )
    goto LABEL_45;
LABEL_18:
  v23 = 1;
LABEL_19:
  v27 = v43;
  *((_DWORD *)v40 + 8) = a3;
  v28 = (const unsigned __int16 *)*((_QWORD *)v27 + 10);
  v41 = (const char *)v28;
  if ( v28 )
  {
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v28 + 8LL))(v28);
    v10 = v40;
    v27 = v43;
    v11 = v41;
  }
  if ( a3 == 2 )
  {
    v15 = *((_QWORD *)v10 + 8);
    *((_QWORD *)v10 + 8) = 0;
    v14 = *((_QWORD *)v10 + 5);
    *((_QWORD *)v10 + 5) = 0;
    v13 = *((_QWORD *)v10 + 7);
    *((_QWORD *)v10 + 7) = 0;
    v12 = *((_QWORD *)v10 + 6);
    *((_QWORD *)v10 + 6) = 0;
    if ( *((_DWORD *)v10 + 296) )
    {
      v42 = 0;
      v41 = (const char *)CallAudioRouting::_DeferredCallAudioRoutingManagerToDisableAudio;
      v29 = *(_QWORD *)v27;
      v40 = v27;
      (*(void (__fastcall **)(struct CallAudioRouting::CellularAudioState *))(v29 + 8))(v27);
      v30 = QueueAsyncWorkItem_ATL::CComPtr_CallAudioRouting__long____cdecl_CallAudioRouting::___unsigned_int__unsigned_int___(
              *((_QWORD *)v43 + 27),
              &v40,
              &v41,
              &v38);
      v31 = v40;
      v37 = v30;
      if ( v40 )
      {
        (*(void (__fastcall **)(struct CallAudioRouting::CellularAudioState *))(*(_QWORD *)v40 + 16LL))(v40);
        v30 = v37;
      }
      if ( v30 < 0 )
      {
        BackTraceCollection::Capture(v31, v30);
        v32 = v37;
        Log_HREvent_17(v37, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1586);
        LeaveCriticalSection(lpCriticalSection);
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        if ( v11 )
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v11 + 16LL))(v11);
        return v32;
      }
      v37 = v38;
    }
  }
LABEL_47:
  LeaveCriticalSection(lpCriticalSection);
  if ( !v23 )
  {
    if ( (unsigned int)dword_1800B3200 > 2
      && (qword_1800B3210 & 0x200000000000LL) != 0
      && (qword_1800B3218 & 0x200000000000LL) == qword_1800B3218 )
    {
      v41 = "CallRecording: INVALID state change";
      v38 = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_1800B3218,
        (int)word_1800A9E22,
        v35,
        v36,
        (const unsigned __int16 **)&v41,
        (__int64)&v37,
        (__int64)&v39,
        (__int64)&v38);
    }
    v32 = -2147418113;
    Log_HREvent_17(2147549183LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1620);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v11 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v11 + 16LL))(v11);
    return v32;
  }
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v41 = "CallAudioRouting: CallRecording VALID state change";
    v38 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v34,
      (int)&unk_1800A9E80,
      v35,
      v36,
      (const unsigned __int16 **)&v41,
      (__int64)&v37,
      (__int64)&v39,
      (__int64)&v38);
  }
  if ( v11 )
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v11 + 24LL))(v11);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v11 )
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v11 + 16LL))(v11);
  return 0;
}

```

## disassembly

```asm
0x18006bb78  mov     [rsp-38h+arg_10], rbx
0x18006bb7d  push    rbp
0x18006bb7e  push    rsi
0x18006bb7f  push    rdi
0x18006bb80  push    r12
0x18006bb82  push    r13
0x18006bb84  push    r14
0x18006bb86  push    r15
0x18006bb88  mov     rbp, rsp
0x18006bb8b  sub     rsp, 80h
0x18006bb92  mov     r13d, r8d
0x18006bb95  mov     [rbp+var_40], edx
0x18006bb98  mov     esi, edx
0x18006bb9a  mov     [rbp+var_10], rcx
0x18006bb9e  mov     rbx, rcx
0x18006bba1  mov     [rbp+var_38], edx
0x18006bba4  call    cs:__imp_GetCurrentThreadId
0x18006bbaa  lea     rdi, [rbx+58h]
0x18006bbae  mov     [rbp+lpCriticalSection], rdi
0x18006bbb2  cmp     [rdi+10h], eax
0x18006bbb5  jnz     short loc_18006BBD9
0x18006bbb7  mov     r8d, 5EEh
0x18006bbbd  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006bbc4  call    Log_AssertionEvent_9
0x18006bbc9  call    cs:__imp_GetCurrentThreadId
0x18006bbcf  cmp     [rbx+68h], eax
0x18006bbd2  jnz     short loc_18006BBD9
0x18006bbd4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006bbd9  mov     rcx, rdi; lpCriticalSection
0x18006bbdc  call    cs:__imp_EnterCriticalSection
0x18006bbe2  lea     r8, [rbp+var_28]; struct CallAudioRouting::CellularAudioState **
0x18006bbe6  mov     [rbp+var_28], 0
0x18006bbee  mov     edx, esi; unsigned int
0x18006bbf0  mov     rcx, rbx; this
0x18006bbf3  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x18006bbf8  xor     r9d, r9d
0x18006bbfb  test    eax, eax
0x18006bbfd  jnz     short loc_18006BC31
0x18006bbff  mov     ebx, 80070490h
0x18006bc04  mov     edx, ebx; int
0x18006bc06  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006bc0b  mov     r9d, 5F4h
0x18006bc11  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006bc18  xor     edx, edx
0x18006bc1a  mov     ecx, ebx
0x18006bc1c  call    Log_HREvent_17
0x18006bc21  mov     rcx, rdi; lpCriticalSection
0x18006bc24  call    cs:__imp_LeaveCriticalSection
0x18006bc2a  mov     eax, ebx
0x18006bc2c  jmp     loc_18006C042
0x18006bc31  mov     rdx, [rbp+var_28]
0x18006bc35  mov     rbx, r9
0x18006bc38  mov     rdi, r9
0x18006bc3b  mov     rsi, r9
0x18006bc3e  mov     r14, r9
0x18006bc41  mov     r15, r9
0x18006bc44  mov     r8d, 1
0x18006bc4a  mov     ecx, [rdx+20h]
0x18006bc4d  mov     [rbp+var_30], ecx
0x18006bc50  test    ecx, ecx
0x18006bc52  jz      loc_18006BE46
0x18006bc58  sub     ecx, 2
0x18006bc5b  jz      loc_18006BE31
0x18006bc61  sub     ecx, r8d
0x18006bc64  jz      loc_18006BE28
0x18006bc6a  sub     ecx, r8d
0x18006bc6d  jz      loc_18006BE15
0x18006bc73  sub     ecx, r8d
0x18006bc76  jz      short loc_18006BC9B
0x18006bc78  sub     ecx, r8d
0x18006bc7b  jz      loc_18006BE0F
0x18006bc81  sub     ecx, r8d
0x18006bc84  jz      short loc_18006BC9B
0x18006bc86  mov     r12d, r9d
0x18006bc89  cmp     ecx, r8d
0x18006bc8c  jnz     loc_18006BE5E
0x18006bc92  cmp     r13d, 2
0x18006bc96  jmp     loc_18006BE38
0x18006bc9b  lea     eax, [r13-4]
0x18006bc9f  test    eax, 0FFFFFFFDh
0x18006bca4  jnz     loc_18006BE53
0x18006bcaa  mov     r12d, r8d
0x18006bcad  mov     r8, [rbp+var_10]
0x18006bcb1  mov     [rdx+20h], r13d
0x18006bcb5  mov     rcx, [r8+50h]
0x18006bcb9  mov     [rbp+var_20], rcx
0x18006bcbd  test    rcx, rcx
0x18006bcc0  jz      short loc_18006BCDD
0x18006bcc2  mov     rax, [rcx]
0x18006bcc5  mov     rax, [rax+8]
0x18006bcc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bcce  mov     rdx, [rbp+var_28]
0x18006bcd2  xor     r9d, r9d
0x18006bcd5  mov     r8, [rbp+var_10]
0x18006bcd9  mov     rbx, [rbp+var_20]
0x18006bcdd  cmp     r13d, 2
0x18006bce1  jnz     loc_18006BE5E
0x18006bce7  mov     r15, [rdx+40h]
0x18006bceb  mov     [rdx+40h], r9
0x18006bcef  mov     r14, [rdx+28h]
0x18006bcf3  mov     [rdx+28h], r9
0x18006bcf7  mov     rsi, [rdx+38h]
0x18006bcfb  mov     [rdx+38h], r9
0x18006bcff  mov     rdi, [rdx+30h]
0x18006bd03  mov     [rdx+30h], r9
0x18006bd07  cmp     [rdx+4A0h], r9d
0x18006bd0e  jz      loc_18006BE5E
0x18006bd14  lea     rax, ?_DeferredCallAudioRoutingManagerToDisableAudio@CallAudioRouting@@AEAAJI@Z; CallAudioRouting::_DeferredCallAudioRoutingManagerToDisableAudio(uint)
0x18006bd1b  mov     [rbp+var_18], r9d
0x18006bd1f  mov     [rbp+var_20], rax
0x18006bd23  mov     rcx, r8
0x18006bd26  mov     eax, [rbp+var_14]
0x18006bd29  mov     [rbp+var_14], eax
0x18006bd2c  mov     rax, [r8]
0x18006bd2f  mov     [rbp+var_28], r8
0x18006bd33  mov     rax, [rax+8]
0x18006bd37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd3c  mov     rcx, [rbp+var_10]
0x18006bd40  lea     r9, [rbp+var_38]
0x18006bd44  lea     r8, [rbp+var_20]
0x18006bd48  lea     rdx, [rbp+var_28]
0x18006bd4c  mov     rcx, [rcx+0D8h]
0x18006bd53  call    QueueAsyncWorkItem_ATL__CComPtr_CallAudioRouting__long____cdecl_CallAudioRouting_____unsigned_int__unsigned_int___
0x18006bd58  mov     rcx, [rbp+var_28]
0x18006bd5c  mov     [rbp+var_40], eax
0x18006bd5f  test    rcx, rcx
0x18006bd62  jz      short loc_18006BD73
0x18006bd64  mov     r8, [rcx]
0x18006bd67  mov     rax, [r8+10h]
0x18006bd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd70  mov     eax, [rbp+var_40]
0x18006bd73  test    eax, eax
0x18006bd75  jns     loc_18006BE58
0x18006bd7b  mov     edx, eax; int
0x18006bd7d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006bd82  mov     r12d, [rbp+var_40]
0x18006bd86  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006bd8d  mov     r9d, 632h
0x18006bd93  mov     edx, 1
0x18006bd98  mov     ecx, r12d
0x18006bd9b  call    Log_HREvent_17
0x18006bda0  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18006bda4  call    cs:__imp_LeaveCriticalSection
0x18006bdaa  test    r15, r15
0x18006bdad  jz      short loc_18006BDBE
0x18006bdaf  mov     rax, [r15]
0x18006bdb2  mov     rcx, r15
0x18006bdb5  mov     rax, [rax+10h]
0x18006bdb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bdbe  test    r14, r14
0x18006bdc1  jz      short loc_18006BDD2
0x18006bdc3  mov     rax, [r14]
0x18006bdc6  mov     rcx, r14
0x18006bdc9  mov     rax, [rax+10h]
0x18006bdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bdd2  test    rsi, rsi
0x18006bdd5  jz      short loc_18006BDE6
0x18006bdd7  mov     rax, [rsi]
0x18006bdda  mov     rcx, rsi
0x18006bddd  mov     rax, [rax+10h]
0x18006bde1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bde6  test    rdi, rdi
0x18006bde9  jz      short loc_18006BDFA
0x18006bdeb  mov     rax, [rdi]
0x18006bdee  mov     rcx, rdi
0x18006bdf1  mov     rax, [rax+10h]
0x18006bdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bdfa  test    rbx, rbx
0x18006bdfd  jz      loc_18006C03F
0x18006be03  mov     rax, [rbx]
0x18006be06  mov     rax, [rax+10h]
0x18006be0a  jmp     loc_18006C037
0x18006be0f  lea     eax, [r13-7]
0x18006be13  jmp     short loc_18006BE4A
0x18006be15  cmp     r13d, 5
0x18006be19  jz      loc_18006BCAA
0x18006be1f  cmp     r13d, 8
0x18006be23  jmp     loc_18006BCA4
0x18006be28  lea     eax, [r13-2]
0x18006be2c  jmp     loc_18006BC9F
0x18006be31  mov     r12d, r9d
0x18006be34  cmp     r13d, 3
0x18006be38  setz    r12b
0x18006be3c  test    r12d, r12d
0x18006be3f  jz      short loc_18006BE5E
0x18006be41  jmp     loc_18006BCAD
0x18006be46  lea     eax, [r13-1]
0x18006be4a  cmp     eax, r8d
0x18006be4d  jbe     loc_18006BCAA
0x18006be53  mov     r12d, r9d
0x18006be56  jmp     short loc_18006BE5E
0x18006be58  mov     eax, [rbp+var_38]
0x18006be5b  mov     [rbp+var_40], eax
0x18006be5e  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18006be62  call    cs:__imp_LeaveCriticalSection
0x18006be68  mov     eax, cs:dword_1800B3200
0x18006be6e  test    r12d, r12d
0x18006be71  jz      loc_18006BF46
0x18006be77  cmp     eax, 4
0x18006be7a  jbe     short loc_18006BEC7
0x18006be7c  mov     eax, [rbp+var_30]
0x18006be7f  lea     rdx, unk_1800A9E80
0x18006be86  mov     [rbp+var_30], eax
0x18006be89  mov     eax, [rbp+var_40]
0x18006be8c  mov     [rbp+var_40], eax
0x18006be8f  lea     rax, aCallaudiorouti; "CallAudioRouting: CallRecording VALID s"...
0x18006be96  mov     [rbp+var_20], rax
0x18006be9a  lea     rax, [rbp+var_38]
0x18006be9e  mov     [rsp+80h+var_48], rax
0x18006bea3  lea     rax, [rbp+var_30]
0x18006bea7  mov     [rsp+80h+var_50], rax
0x18006beac  lea     rax, [rbp+var_40]
0x18006beb0  mov     [rsp+80h+var_58], rax
0x18006beb5  lea     rax, [rbp+var_20]
0x18006beb9  mov     [rsp+80h+var_60], rax
0x18006bebe  mov     [rbp+var_38], r13d
0x18006bec2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006bec7  test    rbx, rbx
0x18006beca  jz      short loc_18006BEDB
0x18006becc  mov     rax, [rbx]
0x18006becf  mov     rcx, rbx
0x18006bed2  mov     rax, [rax+18h]
0x18006bed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bedb  test    r15, r15
0x18006bede  jz      short loc_18006BEEF
0x18006bee0  mov     rax, [r15]
0x18006bee3  mov     rcx, r15
0x18006bee6  mov     rax, [rax+10h]
0x18006beea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006beef  test    r14, r14
0x18006bef2  jz      short loc_18006BF03
0x18006bef4  mov     rax, [r14]
0x18006bef7  mov     rcx, r14
0x18006befa  mov     rax, [rax+10h]
0x18006befe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf03  test    rsi, rsi
0x18006bf06  jz      short loc_18006BF17
0x18006bf08  mov     rax, [rsi]
0x18006bf0b  mov     rcx, rsi
0x18006bf0e  mov     rax, [rax+10h]
0x18006bf12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf17  test    rdi, rdi
0x18006bf1a  jz      short loc_18006BF2B
0x18006bf1c  mov     rax, [rdi]
0x18006bf1f  mov     rcx, rdi
0x18006bf22  mov     rax, [rax+10h]
0x18006bf26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf2b  test    rbx, rbx
0x18006bf2e  jz      short loc_18006BF3F
0x18006bf30  mov     rax, [rbx]
0x18006bf33  mov     rcx, rbx
0x18006bf36  mov     rax, [rax+10h]
0x18006bf3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf3f  xor     eax, eax
0x18006bf41  jmp     loc_18006C042
0x18006bf46  cmp     eax, 2
0x18006bf49  jbe     short loc_18006BFBE
0x18006bf4b  mov     rcx, cs:qword_1800B3218
0x18006bf52  mov     rdx, 200000000000h
0x18006bf5c  mov     rax, cs:qword_1800B3210
0x18006bf63  test    rdx, rax
0x18006bf66  jz      short loc_18006BFBE
0x18006bf68  mov     rax, rcx
0x18006bf6b  and     rax, rdx
0x18006bf6e  cmp     rax, rcx
0x18006bf71  jnz     short loc_18006BFBE
0x18006bf73  mov     eax, [rbp+var_30]
0x18006bf76  lea     rdx, word_1800A9E22
0x18006bf7d  mov     [rbp+var_30], eax
0x18006bf80  mov     eax, [rbp+var_40]
0x18006bf83  mov     [rbp+var_40], eax
0x18006bf86  lea     rax, aCallrecordingI; "CallRecording: INVALID state change"
0x18006bf8d  mov     [rbp+var_20], rax
0x18006bf91  lea     rax, [rbp+var_38]
0x18006bf95  mov     [rsp+80h+var_48], rax
0x18006bf9a  lea     rax, [rbp+var_30]
0x18006bf9e  mov     [rsp+80h+var_50], rax
0x18006bfa3  lea     rax, [rbp+var_40]
0x18006bfa7  mov     [rsp+80h+var_58], rax
0x18006bfac  lea     rax, [rbp+var_20]
0x18006bfb0  mov     [rsp+80h+var_60], rax
0x18006bfb5  mov     [rbp+var_38], r13d
0x18006bfb9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006bfbe  mov     r12d, 8000FFFFh
0x18006bfc4  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006bfcb  mov     ecx, r12d
0x18006bfce  mov     r9d, 654h
0x18006bfd4  xor     edx, edx
0x18006bfd6  call    Log_HREvent_17
0x18006bfdb  test    r15, r15
0x18006bfde  jz      short loc_18006BFEF
0x18006bfe0  mov     rax, [r15]
0x18006bfe3  mov     rcx, r15
0x18006bfe6  mov     rax, [rax+10h]
0x18006bfea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bfef  test    r14, r14
0x18006bff2  jz      short loc_18006C003
0x18006bff4  mov     rax, [r14]
0x18006bff7  mov     rcx, r14
0x18006bffa  mov     rax, [rax+10h]
  ... truncated ...
```
