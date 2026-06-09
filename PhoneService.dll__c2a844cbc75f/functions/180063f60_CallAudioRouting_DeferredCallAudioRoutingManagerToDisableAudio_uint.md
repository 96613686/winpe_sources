# CallAudioRouting::_DeferredCallAudioRoutingManagerToDisableAudio(uint)

- ea: `0x180063f60`
- end: `0x1800640be`
- name: `?_DeferredCallAudioRoutingManagerToDisableAudio@CallAudioRouting@@AEAAJI@Z`
- size: `350`
- prototype: `__int64 __fastcall(CallAudioRouting *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001348`
- `0x180006e94`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x18006253c`
- `0x180063f60`
- `0x180064dac`
- `0x18007f9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063fa5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063fa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063fec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064031`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063fec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064031`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063f71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063f92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063f71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063f92`

## string_xrefs

- `0x180063f86`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180063fd9`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180063fff`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_DeferredCallAudioRoutingManagerToDisableAudio(
        CallAudioRouting *this,
        unsigned int a2)
{
  __int64 v4; // rcx
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  BackTraceCollection *v6; // rcx
  unsigned int v7; // ebx
  BackTraceCollection *v8; // rcx
  __int64 v9; // r9
  unsigned int v11; // esi
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // eax
  BackTraceCollection *v16; // rcx
  struct CallAudioRouting::CellularAudioState *v17; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v18; // [rsp+48h] [rbp-30h] BYREF
  const char *v19; // [rsp+50h] [rbp-28h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3331);
    if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v17 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState(this, a2, &v17) )
  {
    v7 = -2147023728;
    BackTraceCollection::Capture(v6, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3818);
    LeaveCriticalSection(v5);
    BackTraceCollection::Capture(v8, -2147023728);
    v9 = 3339;
LABEL_6:
    Log_HREvent_17(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v9);
    return v7;
  }
  v11 = *((_DWORD *)v17 + 296);
  *((_DWORD *)v17 + 296) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( v11 )
  {
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      v18 = a2;
      v19 = "CallAudioRouting: Performing deferred request to disable cellular audio";
      LODWORD(v17) = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (int)&byte_1800A9A77,
        v13,
        v14,
        (const unsigned __int16 **)&v19,
        (__int64)&v17,
        (__int64)&v18);
    }
    v15 = CallAudioRouting::_CallAudioRoutingManagerToDisableAudio(this, a2, v11, 0);
    v7 = v15;
    if ( v15 < 0 )
    {
      BackTraceCollection::Capture(v16, v15);
      v9 = 3354;
      goto LABEL_6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180063f60  mov     [rsp+arg_10], rbx
0x180063f65  push    rbp
0x180063f66  push    rsi
0x180063f67  push    rdi
0x180063f68  sub     rsp, 60h
0x180063f6c  mov     ebp, edx
0x180063f6e  mov     rbx, rcx
0x180063f71  call    cs:__imp_GetCurrentThreadId
0x180063f77  lea     rdi, [rbx+58h]
0x180063f7b  cmp     [rdi+10h], eax
0x180063f7e  jnz     short loc_180063FA2
0x180063f80  mov     r8d, 0D03h
0x180063f86  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180063f8d  call    Log_AssertionEvent_9
0x180063f92  call    cs:__imp_GetCurrentThreadId
0x180063f98  cmp     [rbx+68h], eax
0x180063f9b  jnz     short loc_180063FA2
0x180063f9d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180063fa2  mov     rcx, rdi; lpCriticalSection
0x180063fa5  call    cs:__imp_EnterCriticalSection
0x180063fab  lea     r8, [rsp+78h+var_38]; struct CallAudioRouting::CellularAudioState **
0x180063fb0  mov     [rsp+78h+var_38], 0
0x180063fb9  mov     edx, ebp; unsigned int
0x180063fbb  mov     rcx, rbx; this
0x180063fbe  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x180063fc3  test    eax, eax
0x180063fc5  jnz     short loc_180064019
0x180063fc7  mov     ebx, 80070490h
0x180063fcc  mov     edx, ebx; int
0x180063fce  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180063fd3  mov     r9d, 0EEAh
0x180063fd9  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180063fe0  xor     edx, edx
0x180063fe2  mov     ecx, ebx
0x180063fe4  call    Log_HREvent_17
0x180063fe9  mov     rcx, rdi; lpCriticalSection
0x180063fec  call    cs:__imp_LeaveCriticalSection
0x180063ff2  mov     edx, ebx; int
0x180063ff4  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180063ff9  mov     r9d, 0D0Bh
0x180063fff  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064006  mov     edx, 1
0x18006400b  mov     ecx, ebx
0x18006400d  call    Log_HREvent_17
0x180064012  mov     eax, ebx
0x180064014  jmp     loc_1800640AE
0x180064019  mov     rax, [rsp+78h+var_38]
0x18006401e  mov     rcx, rdi; lpCriticalSection
0x180064021  mov     esi, [rax+4A0h]
0x180064027  mov     dword ptr [rax+4A0h], 0
0x180064031  call    cs:__imp_LeaveCriticalSection
0x180064037  test    esi, esi
0x180064039  jz      short loc_1800640AC
0x18006403b  mov     eax, cs:dword_1800B3200
0x180064041  cmp     eax, 4
0x180064044  jbe     short loc_180064084
0x180064046  lea     rax, aCallaudiorouti_12; "CallAudioRouting: Performing deferred r"...
0x18006404d  mov     [rsp+78h+var_30], ebp
0x180064051  mov     [rsp+78h+var_28], rax
0x180064056  lea     rdx, byte_1800A9A77
0x18006405d  lea     rax, [rsp+78h+var_30]
0x180064062  mov     dword ptr [rsp+78h+var_38], esi
0x180064066  mov     [rsp+78h+var_48], rax
0x18006406b  lea     rax, [rsp+78h+var_38]
0x180064070  mov     [rsp+78h+var_50], rax
0x180064075  lea     rax, [rsp+78h+var_28]
0x18006407a  mov     [rsp+78h+var_58], rax
0x18006407f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180064084  xor     r9d, r9d
0x180064087  mov     r8d, esi
0x18006408a  mov     edx, ebp
0x18006408c  mov     rcx, rbx
0x18006408f  call    ?_CallAudioRoutingManagerToDisableAudio@CallAudioRouting@@AEAAJIW4CellularAudioType@@H@Z; CallAudioRouting::_CallAudioRoutingManagerToDisableAudio(uint,CellularAudioType,int)
0x180064094  mov     ebx, eax
0x180064096  test    eax, eax
0x180064098  jns     short loc_1800640AC
0x18006409a  mov     edx, eax; int
0x18006409c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800640a1  mov     r9d, 0D1Ah
0x1800640a7  jmp     loc_180063FFF
0x1800640ac  xor     eax, eax
0x1800640ae  mov     rbx, [rsp+78h+arg_10]
0x1800640b6  add     rsp, 60h
0x1800640ba  pop     rdi
0x1800640bb  pop     rsi
0x1800640bc  pop     rbp
0x1800640bd  retn
```
