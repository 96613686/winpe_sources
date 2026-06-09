# CallAudioRouting::_CallAudioRoutingManagerToEnableAudio(uint,CellularAudioType)

- ea: `0x1800629f0`
- end: `0x180062b7f`
- name: `?_CallAudioRoutingManagerToEnableAudio@CallAudioRouting@@AEAAJIW4CellularAudioType@@@Z`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180064350`

## callees

- `0x180001348`
- `0x1800042b0`
- `0x180006e94`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x1800629f0`
- `0x180064dac`
- `0x18007f9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062a41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062a41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062a86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062aca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062a86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062aca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062a0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062a0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062a2e`

## string_xrefs

- `0x180062a22`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180062a73`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180062a99`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_CallAudioRoutingManagerToEnableAudio(
        __int64 a1,
        unsigned int a2,
        unsigned int a3)
{
  __int64 v6; // rcx
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  BackTraceCollection *v8; // rcx
  BackTraceCollection *v9; // rcx
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // [rsp+40h] [rbp-20h] BYREF
  struct CallAudioRouting::CellularAudioState *v17; // [rsp+48h] [rbp-18h] BYREF
  int v18; // [rsp+50h] [rbp-10h] BYREF
  const char *v19; // [rsp+58h] [rbp-8h] BYREF

  v7 = (struct _RTL_CRITICAL_SECTION *)(a1 + 88);
  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3280);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v17 = 0;
  if ( (unsigned int)CallAudioRouting::_FindCellularState((CallAudioRouting *)a1, a2, &v17) )
  {
    v11 = (struct _RTL_CRITICAL_SECTION *)(a1 + 88);
    v12 = *((_DWORD *)v17 + 296);
    *((_DWORD *)v17 + 296) = 0;
    LeaveCriticalSection(v11);
    if ( v12 && (unsigned int)dword_1800B3200 > 4 )
    {
      v18 = v12;
      v19 = "CallAudioRouting: Cancelled request to defer disabling of cellular audio";
      v16 = a2;
      LODWORD(v17) = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (int)&unk_1800A9B10,
        v14,
        v15,
        (const unsigned __int16 **)&v19,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v18);
    }
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      LODWORD(v17) = a2;
      v19 = "CallAudioRouting: Enabling cellular audio";
      v16 = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (int)&unk_1800A9AC8,
        v14,
        v15,
        (const unsigned __int16 **)&v19,
        (__int64)&v16,
        (__int64)&v17);
    }
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v8, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3818);
    LeaveCriticalSection(v7);
    BackTraceCollection::Capture(v9, -2147023728);
    Log_HREvent_17(2147943568LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3286);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x1800629f0  mov     [rsp-18h+arg_8], rbx
0x1800629f5  mov     [rsp-18h+arg_10], rsi
0x1800629fa  push    rbp
0x1800629fb  push    rdi
0x1800629fc  push    r14
0x1800629fe  mov     rbp, rsp
0x180062a01  sub     rsp, 60h
0x180062a05  mov     r14d, r8d
0x180062a08  mov     esi, edx
0x180062a0a  mov     rdi, rcx
0x180062a0d  call    cs:__imp_GetCurrentThreadId
0x180062a13  lea     rbx, [rdi+58h]
0x180062a17  cmp     [rbx+10h], eax
0x180062a1a  jnz     short loc_180062A3E
0x180062a1c  mov     r8d, 0CD0h
0x180062a22  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180062a29  call    Log_AssertionEvent_9
0x180062a2e  call    cs:__imp_GetCurrentThreadId
0x180062a34  cmp     [rdi+68h], eax
0x180062a37  jnz     short loc_180062A3E
0x180062a39  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180062a3e  mov     rcx, rbx; lpCriticalSection
0x180062a41  call    cs:__imp_EnterCriticalSection
0x180062a47  lea     r8, [rbp+var_18]; struct CallAudioRouting::CellularAudioState **
0x180062a4b  mov     [rbp+var_18], 0
0x180062a53  mov     edx, esi; unsigned int
0x180062a55  mov     rcx, rdi; this
0x180062a58  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x180062a5d  test    eax, eax
0x180062a5f  jnz     short loc_180062AB3
0x180062a61  mov     edi, 80070490h
0x180062a66  mov     edx, edi; int
0x180062a68  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180062a6d  mov     r9d, 0EEAh
0x180062a73  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180062a7a  xor     edx, edx
0x180062a7c  mov     ecx, edi
0x180062a7e  call    Log_HREvent_17
0x180062a83  mov     rcx, rbx; lpCriticalSection
0x180062a86  call    cs:__imp_LeaveCriticalSection
0x180062a8c  mov     edx, edi; int
0x180062a8e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180062a93  mov     r9d, 0CD6h
0x180062a99  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180062aa0  mov     edx, 1
0x180062aa5  mov     ecx, edi
0x180062aa7  call    Log_HREvent_17
0x180062aac  mov     eax, edi
0x180062aae  jmp     loc_180062B6A
0x180062ab3  mov     rax, [rbp+var_18]
0x180062ab7  mov     rcx, rbx; lpCriticalSection
0x180062aba  mov     edi, [rax+4A0h]
0x180062ac0  mov     dword ptr [rax+4A0h], 0
0x180062aca  call    cs:__imp_LeaveCriticalSection
0x180062ad0  test    edi, edi
0x180062ad2  jz      short loc_180062B24
0x180062ad4  mov     eax, cs:dword_1800B3200
0x180062ada  cmp     eax, 4
0x180062add  jbe     short loc_180062B24
0x180062adf  lea     rax, aCallaudiorouti_21; "CallAudioRouting: Cancelled request to "...
0x180062ae6  mov     [rbp+var_10], edi
0x180062ae9  mov     [rbp+var_8], rax
0x180062aed  lea     rdx, unk_1800A9B10
0x180062af4  lea     rax, [rbp+var_10]
0x180062af8  mov     [rbp+var_20], esi
0x180062afb  mov     [rsp+60h+var_28], rax
0x180062b00  lea     rax, [rbp+var_20]
0x180062b04  mov     [rsp+60h+var_30], rax
0x180062b09  lea     rax, [rbp+var_18]
0x180062b0d  mov     [rsp+60h+var_38], rax
0x180062b12  lea     rax, [rbp+var_8]
0x180062b16  mov     [rsp+60h+var_40], rax
0x180062b1b  mov     dword ptr [rbp+var_18], r14d
0x180062b1f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180062b24  mov     eax, cs:dword_1800B3200
0x180062b2a  cmp     eax, 4
0x180062b2d  jbe     short loc_180062B68
0x180062b2f  lea     rax, aCallaudiorouti_8; "CallAudioRouting: Enabling cellular aud"...
0x180062b36  mov     dword ptr [rbp+var_18], esi
0x180062b39  mov     [rbp+var_8], rax
0x180062b3d  lea     rdx, unk_1800A9AC8
0x180062b44  lea     rax, [rbp+var_18]
0x180062b48  mov     [rbp+var_20], r14d
0x180062b4c  mov     [rsp+60h+var_30], rax
0x180062b51  lea     rax, [rbp+var_20]
0x180062b55  mov     [rsp+60h+var_38], rax
0x180062b5a  lea     rax, [rbp+var_8]
0x180062b5e  mov     [rsp+60h+var_40], rax
0x180062b63  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180062b68  xor     eax, eax
0x180062b6a  lea     r11, [rsp+60h+var_s0]
0x180062b6f  mov     rbx, [r11+28h]
0x180062b73  mov     rsi, [r11+30h]
0x180062b77  mov     rsp, r11
0x180062b7a  pop     r14
0x180062b7c  pop     rdi
0x180062b7d  pop     rbp
0x180062b7e  retn
```
