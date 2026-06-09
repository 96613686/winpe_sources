# CallAudioRouting::_CallAudioRoutingManagerToDisableAudio(uint,CellularAudioType,int)

- ea: `0x18006253c`
- end: `0x180062783`
- name: `?_CallAudioRoutingManagerToDisableAudio@CallAudioRouting@@AEAAJIW4CellularAudioType@@H@Z`
- size: `583`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800622b0`
- `0x180063f60`
- `0x180064350`
- `0x180068010`

## callees

- `0x180001348`
- `0x180006e94`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x18006253c`
- `0x180064dac`
- `0x18007f9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062598`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800625e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062630`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800626cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800626f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800625e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062630`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800626cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800626f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062585`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062585`

## string_xrefs

- `0x18006256b`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_CallAudioRoutingManagerToDisableAudio(__int64 a1, int a2, int a3, int a4)
{
  __int64 v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  int CellularState; // eax
  BackTraceCollection *v11; // rcx
  BackTraceCollection *v12; // rcx
  __int64 v13; // r9
  int v15; // edx
  int v16; // esi
  __int64 v17; // r8
  __int64 v18; // r9
  BackTraceCollection *v19; // rcx
  struct CallAudioRouting::CellularAudioState *v20; // [rsp+40h] [rbp-20h] BYREF
  int v21; // [rsp+48h] [rbp-18h] BYREF
  const unsigned __int16 *v22[2]; // [rsp+50h] [rbp-10h] BYREF

  v9 = (struct _RTL_CRITICAL_SECTION *)(a1 + 88);
  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3366);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v20 = 0;
  CellularState = CallAudioRouting::_FindCellularState((CallAudioRouting *)a1, a2, &v20);
  if ( !a4 )
  {
    if ( !CellularState )
    {
      BackTraceCollection::Capture(v11, -2147023728);
      Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3818);
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
      BackTraceCollection::Capture(v19, -2147023728);
      v13 = 3402;
      goto LABEL_7;
    }
    *((_DWORD *)v20 + 296) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    goto LABEL_19;
  }
  if ( !CellularState )
  {
    BackTraceCollection::Capture(v11, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3818);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    BackTraceCollection::Capture(v12, -2147023728);
    v13 = 3383;
LABEL_7:
    Log_HREvent_17(2147943568LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v13);
    return 2147943568LL;
  }
  v15 = *((_DWORD *)v20 + 8);
  if ( (unsigned int)(v15 - 4) <= 1 || (v16 = 0, v15 == 8) )
  {
    *((_DWORD *)v20 + 296) = a3;
    v16 = 1;
  }
  LeaveCriticalSection(v9);
  if ( !v16 )
  {
LABEL_19:
    if ( (unsigned int)dword_1800B3200 > 4
      && (qword_1800B3210 & 0x200000000000LL) != 0
      && (qword_1800B3218 & 0x200000000000LL) == qword_1800B3218 )
    {
      LODWORD(v20) = a2;
      v22[0] = (const unsigned __int16 *)"[CellularAudio] Disabling cellular audio";
      v21 = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        0x200000000000LL,
        (int)&byte_1800A99E7,
        v17,
        v18,
        v22,
        (__int64)&v21,
        (__int64)&v20);
    }
    return 0;
  }
  if ( (unsigned int)dword_1800B3200 > 4
    && (qword_1800B3210 & 0x200000000000LL) != 0
    && (qword_1800B3218 & 0x200000000000LL) == qword_1800B3218 )
  {
    v21 = a2;
    v22[0] = (const unsigned __int16 *)"CallRecording: Deferred request to disable cellular audio";
    LODWORD(v20) = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      0x200000000000LL,
      (int)&unk_1800A9A30,
      v17,
      v18,
      v22,
      (__int64)&v20,
      (__int64)&v21);
  }
  return 0;
}

```

## disassembly

```asm
0x18006253c  mov     [rsp-28h+arg_8], rbx
0x180062541  mov     [rsp-28h+arg_10], rsi
0x180062546  push    rbp
0x180062547  push    rdi
0x180062548  push    r13
0x18006254a  push    r14
0x18006254c  push    r15
0x18006254e  mov     rbp, rsp
0x180062551  sub     rsp, 60h
0x180062555  mov     r15d, r9d
0x180062558  mov     edi, r8d
0x18006255b  mov     r14d, edx
0x18006255e  mov     rsi, rcx
0x180062561  call    cs:__imp_GetCurrentThreadId
0x180062567  lea     rbx, [rsi+58h]
0x18006256b  lea     r13, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180062572  cmp     [rbx+10h], eax
0x180062575  jnz     short loc_180062595
0x180062577  mov     r8d, 0D26h
0x18006257d  mov     rdx, r13
0x180062580  call    Log_AssertionEvent_9
0x180062585  call    cs:__imp_GetCurrentThreadId
0x18006258b  cmp     [rsi+68h], eax
0x18006258e  jnz     short loc_180062595
0x180062590  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180062595  mov     rcx, rbx; lpCriticalSection
0x180062598  call    cs:__imp_EnterCriticalSection
0x18006259e  lea     r8, [rbp+var_20]; struct CallAudioRouting::CellularAudioState **
0x1800625a2  mov     [rbp+var_20], 0
0x1800625aa  mov     edx, r14d; unsigned int
0x1800625ad  mov     rcx, rsi; this
0x1800625b0  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x1800625b5  test    r15d, r15d
0x1800625b8  jz      loc_1800626A8
0x1800625be  test    eax, eax
0x1800625c0  jnz     short loc_18006260C
0x1800625c2  mov     edi, 80070490h
0x1800625c7  mov     edx, edi; int
0x1800625c9  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800625ce  mov     r9d, 0EEAh
0x1800625d4  mov     r8, r13
0x1800625d7  xor     edx, edx
0x1800625d9  mov     ecx, edi
0x1800625db  call    Log_HREvent_17
0x1800625e0  mov     rcx, rbx; lpCriticalSection
0x1800625e3  call    cs:__imp_LeaveCriticalSection
0x1800625e9  mov     edx, edi; int
0x1800625eb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800625f0  mov     r9d, 0D37h
0x1800625f6  mov     r8, r13
0x1800625f9  mov     edx, 1
0x1800625fe  mov     ecx, edi
0x180062600  call    Log_HREvent_17
0x180062605  mov     eax, edi
0x180062607  jmp     loc_18006276A
0x18006260c  mov     rcx, [rbp+var_20]
0x180062610  mov     edx, [rcx+20h]
0x180062613  lea     eax, [rdx-4]
0x180062616  cmp     eax, 1
0x180062619  jbe     short loc_180062622
0x18006261b  xor     esi, esi
0x18006261d  cmp     edx, 8
0x180062620  jnz     short loc_18006262D
0x180062622  mov     [rcx+4A0h], edi
0x180062628  mov     esi, 1
0x18006262d  mov     rcx, rbx; lpCriticalSection
0x180062630  call    cs:__imp_LeaveCriticalSection
0x180062636  test    esi, esi
0x180062638  jz      loc_1800626FC
0x18006263e  mov     eax, cs:dword_1800B3200
0x180062644  cmp     eax, 4
0x180062647  jbe     loc_180062768
0x18006264d  mov     rdx, cs:qword_1800B3218
0x180062654  mov     rcx, 200000000000h
0x18006265e  mov     rax, cs:qword_1800B3210
0x180062665  test    rcx, rax
0x180062668  jz      loc_180062768
0x18006266e  mov     rax, rdx
0x180062671  and     rax, rcx
0x180062674  cmp     rax, rdx
0x180062677  jnz     loc_180062768
0x18006267d  lea     rax, aCallrecordingD; "CallRecording: Deferred request to disa"...
0x180062684  mov     [rbp+var_18], r14d
0x180062688  mov     [rbp+var_10], rax
0x18006268c  lea     rdx, unk_1800A9A30
0x180062693  lea     rax, [rbp+var_18]
0x180062697  mov     dword ptr [rbp+var_20], edi
0x18006269a  mov     [rsp+60h+var_30], rax
0x18006269f  lea     rax, [rbp+var_20]
0x1800626a3  jmp     loc_180062755
0x1800626a8  test    eax, eax
0x1800626aa  jnz     short loc_1800626E5
0x1800626ac  mov     edi, 80070490h
0x1800626b1  mov     edx, edi; int
0x1800626b3  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800626b8  mov     r9d, 0EEAh
0x1800626be  mov     r8, r13
0x1800626c1  xor     edx, edx
0x1800626c3  mov     ecx, edi
0x1800626c5  call    Log_HREvent_17
0x1800626ca  mov     rcx, rbx; lpCriticalSection
0x1800626cd  call    cs:__imp_LeaveCriticalSection
0x1800626d3  mov     edx, edi; int
0x1800626d5  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800626da  mov     r9d, 0D4Ah
0x1800626e0  jmp     loc_1800625F6
0x1800626e5  mov     rax, [rbp+var_20]
0x1800626e9  mov     rcx, rbx; lpCriticalSection
0x1800626ec  mov     dword ptr [rax+4A0h], 0
0x1800626f6  call    cs:__imp_LeaveCriticalSection
0x1800626fc  mov     eax, cs:dword_1800B3200
0x180062702  cmp     eax, 4
0x180062705  jbe     short loc_180062768
0x180062707  mov     rdx, cs:qword_1800B3218
0x18006270e  mov     rcx, 200000000000h
0x180062718  mov     rax, cs:qword_1800B3210
0x18006271f  test    rcx, rax
0x180062722  jz      short loc_180062768
0x180062724  mov     rax, rdx
0x180062727  and     rax, rcx
0x18006272a  cmp     rax, rdx
0x18006272d  jnz     short loc_180062768
0x18006272f  lea     rax, aCellularaudioD; "[CellularAudio] Disabling cellular audi"...
0x180062736  mov     dword ptr [rbp+var_20], r14d
0x18006273a  mov     [rbp+var_10], rax
0x18006273e  lea     rdx, byte_1800A99E7
0x180062745  lea     rax, [rbp+var_20]
0x180062749  mov     [rbp+var_18], edi
0x18006274c  mov     [rsp+60h+var_30], rax
0x180062751  lea     rax, [rbp+var_18]
0x180062755  mov     [rsp+60h+var_38], rax
0x18006275a  lea     rax, [rbp+var_10]
0x18006275e  mov     [rsp+60h+var_40], rax
0x180062763  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180062768  xor     eax, eax
0x18006276a  lea     r11, [rsp+60h+var_s0]
0x18006276f  mov     rbx, [r11+38h]
0x180062773  mov     rsi, [r11+40h]
0x180062777  mov     rsp, r11
0x18006277a  pop     r15
0x18006277c  pop     r14
0x18006277e  pop     r13
0x180062780  pop     rdi
0x180062781  pop     rbp
0x180062782  retn
```
