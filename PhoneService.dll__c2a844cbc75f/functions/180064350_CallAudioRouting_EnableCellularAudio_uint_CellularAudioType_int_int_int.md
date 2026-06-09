# CallAudioRouting::_EnableCellularAudio(uint,CellularAudioType,int,int,int)

- ea: `0x180064350`
- end: `0x1800646ff`
- name: `?_EnableCellularAudio@CallAudioRouting@@AEAAXIW4CellularAudioType@@HHH@Z`
- size: `943`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800640d0`

## callees

- `0x1800042b0`
- `0x180006e94`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x18006253c`
- `0x1800629f0`
- `0x180064350`
- `0x180064dac`
- `0x1800683d0`
- `0x180069d48`
- `0x18007f9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800643bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064536`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800645db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800643bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064536`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800645db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800643fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006457c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800645a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064625`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800646ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800643fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006457c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800645a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064625`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800646ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006437a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006439e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006437a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006439e`

## string_xrefs

- `0x180064384`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180064505`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180064569`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180064588`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180064612`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800646ba`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
void __fastcall CallAudioRouting::_EnableCellularAudio(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6)
{
  __int64 v10; // rcx
  BackTraceCollection *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rcx
  struct CallAudioRouting::CellularAudioState *v14; // rax
  unsigned int v15; // r15d
  bool v16; // zf
  BOOL v17; // r13d
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // r13d
  int v22; // eax
  BackTraceCollection *v23; // rcx
  BOOL v24; // r13d
  unsigned int v25; // r15d
  int v26; // eax
  BackTraceCollection *v27; // rcx
  struct CallAudioRouting::CellularAudioState *v28; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v30; // [rsp+4Ch] [rbp-34h] BYREF
  BOOL v31; // [rsp+50h] [rbp-30h]
  unsigned int v32; // [rsp+54h] [rbp-2Ch]
  int v33; // [rsp+58h] [rbp-28h]
  struct CallAudioRouting::CellularAudioState *v34; // [rsp+60h] [rbp-20h] BYREF
  const unsigned __int16 *v35[3]; // [rsp+68h] [rbp-18h] BYREF

  LODWORD(v28) = a4;
  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v10, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1302);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v32 = a4 == 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v34 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState((CallAudioRouting *)a1, a2, &v34) )
  {
    BackTraceCollection::Capture(v11, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3818);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    v12 = 1322;
LABEL_6:
    v13 = 2147943568LL;
LABEL_7:
    Log_HREvent_17(v13, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v12);
    return;
  }
  v14 = v34;
  v15 = *((_DWORD *)v34 + 1);
  LODWORD(v34) = *((_DWORD *)v34 + 4);
  v16 = *((_DWORD *)v14 + 2) == 0;
  v31 = v15 != a3;
  v33 = *((_DWORD *)v14 + 3);
  v17 = v16 || !a3;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  if ( v15 == a3 && !a6 )
  {
    v24 = v31;
    goto LABEL_40;
  }
  if ( !v17 )
  {
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      v35[0] = (const unsigned __int16 *)"CallAudioRouting: Handover in progress, cellular audio type change not allowed [executorIndex=";
      v30 = a3;
      v29 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v18,
        (int)&dword_1800A9F5C,
        v19,
        v20,
        v35,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v28);
    }
    v24 = 0;
    goto LABEL_40;
  }
  if ( v15 && v15 != a3 )
  {
    if ( !a5 || a3 )
    {
      v21 = 0;
      if ( (unsigned int)dword_1800B3200 > 4 )
      {
        v29 = a3;
        v35[0] = (const unsigned __int16 *)"CallAudioRouting: An audio type change prevented deferring of audio disable.";
        v30 = a2;
        LODWORD(v28) = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v18,
          (int)byte_1800A9FC5,
          v19,
          v20,
          v35,
          (__int64)&v28,
          (__int64)&v30,
          (__int64)&v29);
      }
    }
    else
    {
      v21 = 1;
    }
    v22 = CallAudioRouting::_CallAudioRoutingManagerToDisableAudio(a1, a2, v15, v21);
    if ( v22 < 0 )
    {
      v12 = 1357;
LABEL_24:
      v13 = (unsigned int)v22;
      goto LABEL_7;
    }
  }
  if ( a3 )
  {
    v22 = CallAudioRouting::_CallAudioRoutingManagerToEnableAudio(a1, a2, a3);
    if ( v22 < 0 )
    {
      v12 = 1362;
      goto LABEL_24;
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v28 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState((CallAudioRouting *)a1, a2, &v28) )
  {
    BackTraceCollection::Capture(v23, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3818);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    v12 = 1368;
    goto LABEL_6;
  }
  *((_DWORD *)v28 + 1) = a3;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v24 = v31;
  if ( v15 == a3 )
  {
LABEL_40:
    v25 = v32;
    if ( v33 == v32 )
      return;
    goto LABEL_32;
  }
  v25 = v32;
LABEL_32:
  if ( a3 )
  {
    v26 = CallAudioRouting::_SetCellularLocalHold(a1, a2, a3, v25);
    if ( v26 < 0 )
    {
      Log_HREvent_17(
        (unsigned int)v26,
        1,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp",
        1396);
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
      v28 = 0;
      if ( !(unsigned int)CallAudioRouting::_FindCellularState((CallAudioRouting *)a1, a2, &v28) )
      {
        BackTraceCollection::Capture(v27, -2147023728);
        Log_HREvent_17(
          2147943568LL,
          0,
          "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp",
          3818);
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
        v12 = 1392;
        goto LABEL_6;
      }
      *((_DWORD *)v28 + 3) = v25;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    }
  }
  if ( v24 || v33 != v25 )
    CallAudioRouting::_MuteCellularAudio((CallAudioRouting *)a1, a2, (int)v34);
}

```

## disassembly

```asm
0x180064350  mov     [rsp-38h+arg_18], rbx
0x180064355  push    rbp
0x180064356  push    rsi
0x180064357  push    rdi
0x180064358  push    r12
0x18006435a  push    r13
0x18006435c  push    r14
0x18006435e  push    r15
0x180064360  mov     rbp, rsp
0x180064363  sub     rsp, 80h
0x18006436a  mov     edi, r9d
0x18006436d  mov     dword ptr [rbp+var_40], r9d
0x180064371  mov     ebx, r8d
0x180064374  mov     r12d, edx
0x180064377  mov     r14, rcx
0x18006437a  call    cs:__imp_GetCurrentThreadId
0x180064380  lea     rsi, [r14+58h]
0x180064384  lea     r15, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006438b  cmp     [rsi+10h], eax
0x18006438e  jnz     short loc_1800643AF
0x180064390  mov     r8d, 516h
0x180064396  mov     rdx, r15
0x180064399  call    Log_AssertionEvent_9
0x18006439e  call    cs:__imp_GetCurrentThreadId
0x1800643a4  cmp     [r14+68h], eax
0x1800643a8  jnz     short loc_1800643AF
0x1800643aa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800643af  xor     eax, eax
0x1800643b1  mov     rcx, rsi; lpCriticalSection
0x1800643b4  test    edi, edi
0x1800643b6  setz    al
0x1800643b9  mov     [rbp+var_2C], eax
0x1800643bc  call    cs:__imp_EnterCriticalSection
0x1800643c2  lea     r8, [rbp+var_20]; struct CallAudioRouting::CellularAudioState **
0x1800643c6  mov     [rbp+var_20], 0
0x1800643ce  mov     edx, r12d; unsigned int
0x1800643d1  mov     rcx, r14; this
0x1800643d4  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x1800643d9  test    eax, eax
0x1800643db  jnz     short loc_18006441E
0x1800643dd  mov     ebx, 80070490h
0x1800643e2  mov     edx, ebx; int
0x1800643e4  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800643e9  mov     r9d, 0EEAh
0x1800643ef  mov     r8, r15
0x1800643f2  xor     edx, edx
0x1800643f4  mov     ecx, ebx
0x1800643f6  call    Log_HREvent_17
0x1800643fb  mov     rcx, rsi; lpCriticalSection
0x1800643fe  call    cs:__imp_LeaveCriticalSection
0x180064404  mov     r9d, 52Ah
0x18006440a  mov     r8, r15
0x18006440d  mov     edx, 1
0x180064412  mov     ecx, ebx
0x180064414  call    Log_HREvent_17
0x180064419  jmp     loc_1800646E4
0x18006441e  mov     rax, [rbp+var_20]
0x180064422  mov     edi, 1
0x180064427  mov     ecx, [rax+10h]
0x18006442a  mov     r15d, [rax+4]
0x18006442e  mov     dword ptr [rbp+var_20], ecx
0x180064431  xor     ecx, ecx
0x180064433  cmp     r15d, ebx
0x180064436  setnz   cl
0x180064439  cmp     dword ptr [rax+8], 0
0x18006443d  mov     [rbp+var_30], ecx
0x180064440  mov     ecx, [rax+0Ch]
0x180064443  mov     [rbp+var_28], ecx
0x180064446  jz      short loc_180064451
0x180064448  test    ebx, ebx
0x18006444a  jz      short loc_180064451
0x18006444c  xor     r13d, r13d
0x18006444f  jmp     short loc_180064454
0x180064451  mov     r13d, edi
0x180064454  mov     rcx, rsi; lpCriticalSection
0x180064457  call    cs:__imp_LeaveCriticalSection
0x18006445d  cmp     r15d, ebx
0x180064460  jnz     short loc_18006446C
0x180064462  cmp     [rbp+arg_28], 0
0x180064466  jz      loc_18006468E
0x18006446c  test    r13d, r13d
0x18006446f  jz      loc_180064636
0x180064475  test    r15d, r15d
0x180064478  jz      loc_180064515
0x18006447e  cmp     r15d, ebx
0x180064481  jz      loc_180064515
0x180064487  cmp     [rbp+arg_20], 0
0x18006448b  jz      short loc_180064496
0x18006448d  test    ebx, ebx
0x18006448f  jnz     short loc_180064496
0x180064491  mov     r13d, edi
0x180064494  jmp     short loc_1800644EA
0x180064496  mov     eax, cs:dword_1800B3200
0x18006449c  xor     r13d, r13d
0x18006449f  cmp     eax, 4
0x1800644a2  jbe     short loc_1800644EA
0x1800644a4  lea     rax, aCallaudiorouti_5; "CallAudioRouting: An audio type change "...
0x1800644ab  mov     [rbp+var_38], ebx
0x1800644ae  mov     [rbp+var_18], rax
0x1800644b2  lea     rdx, byte_1800A9FC5
0x1800644b9  lea     rax, [rbp+var_38]
0x1800644bd  mov     [rbp+var_34], r12d
0x1800644c1  mov     [rsp+80h+var_48], rax
0x1800644c6  lea     rax, [rbp+var_34]
0x1800644ca  mov     [rsp+80h+var_50], rax
0x1800644cf  lea     rax, [rbp+var_40]
0x1800644d3  mov     [rsp+80h+var_58], rax
0x1800644d8  lea     rax, [rbp+var_18]
0x1800644dc  mov     [rsp+80h+var_60], rax
0x1800644e1  mov     dword ptr [rbp+var_40], r15d
0x1800644e5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800644ea  mov     r9d, r13d
0x1800644ed  mov     r8d, r15d
0x1800644f0  mov     edx, r12d
0x1800644f3  mov     rcx, r14
0x1800644f6  call    ?_CallAudioRoutingManagerToDisableAudio@CallAudioRouting@@AEAAJIW4CellularAudioType@@H@Z; CallAudioRouting::_CallAudioRoutingManagerToDisableAudio(uint,CellularAudioType,int)
0x1800644fb  test    eax, eax
0x1800644fd  jns     short loc_180064515
0x1800644ff  mov     r9d, 54Dh
0x180064505  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006450c  mov     edx, edi
0x18006450e  mov     ecx, eax
0x180064510  jmp     loc_180064414
0x180064515  test    ebx, ebx
0x180064517  jz      short loc_180064533
0x180064519  mov     r8d, ebx
0x18006451c  mov     edx, r12d
0x18006451f  mov     rcx, r14
0x180064522  call    ?_CallAudioRoutingManagerToEnableAudio@CallAudioRouting@@AEAAJIW4CellularAudioType@@@Z; CallAudioRouting::_CallAudioRoutingManagerToEnableAudio(uint,CellularAudioType)
0x180064527  test    eax, eax
0x180064529  jns     short loc_180064533
0x18006452b  mov     r9d, 552h
0x180064531  jmp     short loc_180064505
0x180064533  mov     rcx, rsi; lpCriticalSection
0x180064536  call    cs:__imp_EnterCriticalSection
0x18006453c  lea     r8, [rbp+var_40]; struct CallAudioRouting::CellularAudioState **
0x180064540  mov     [rbp+var_40], 0
0x180064548  mov     edx, r12d; unsigned int
0x18006454b  mov     rcx, r14; this
0x18006454e  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x180064553  test    eax, eax
0x180064555  jnz     short loc_180064596
0x180064557  mov     ebx, 80070490h
0x18006455c  mov     edx, ebx; int
0x18006455e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180064563  mov     r9d, 0EEAh
0x180064569  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064570  xor     edx, edx
0x180064572  mov     ecx, ebx
0x180064574  call    Log_HREvent_17
0x180064579  mov     rcx, rsi; lpCriticalSection
0x18006457c  call    cs:__imp_LeaveCriticalSection
0x180064582  mov     r9d, 558h
0x180064588  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006458f  mov     edx, edi
0x180064591  jmp     loc_180064412
0x180064596  mov     rax, [rbp+var_40]
0x18006459a  mov     rcx, rsi; lpCriticalSection
0x18006459d  mov     [rax+4], ebx
0x1800645a0  call    cs:__imp_LeaveCriticalSection
0x1800645a6  mov     r13d, [rbp+var_30]
0x1800645aa  cmp     r15d, ebx
0x1800645ad  jz      loc_180064692
0x1800645b3  mov     r15d, [rbp+var_2C]
0x1800645b7  test    ebx, ebx
0x1800645b9  jz      loc_1800646CA
0x1800645bf  mov     r9d, r15d
0x1800645c2  mov     r8d, ebx
0x1800645c5  mov     edx, r12d
0x1800645c8  mov     rcx, r14
0x1800645cb  call    ?_SetCellularLocalHold@CallAudioRouting@@AEAAJIW4CellularAudioType@@H@Z; CallAudioRouting::_SetCellularLocalHold(uint,CellularAudioType,int)
0x1800645d0  test    eax, eax
0x1800645d2  js      loc_1800646B4
0x1800645d8  mov     rcx, rsi; lpCriticalSection
0x1800645db  call    cs:__imp_EnterCriticalSection
0x1800645e1  lea     r8, [rbp+var_40]; struct CallAudioRouting::CellularAudioState **
0x1800645e5  mov     [rbp+var_40], 0
0x1800645ed  mov     edx, r12d; unsigned int
0x1800645f0  mov     rcx, r14; this
0x1800645f3  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x1800645f8  test    eax, eax
0x1800645fa  jnz     loc_1800646A1
0x180064600  mov     ebx, 80070490h
0x180064605  mov     edx, ebx; int
0x180064607  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006460c  mov     r9d, 0EEAh
0x180064612  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064619  xor     edx, edx
0x18006461b  mov     ecx, ebx
0x18006461d  call    Log_HREvent_17
0x180064622  mov     rcx, rsi; lpCriticalSection
0x180064625  call    cs:__imp_LeaveCriticalSection
0x18006462b  mov     r9d, 570h
0x180064631  jmp     loc_180064588
0x180064636  mov     eax, cs:dword_1800B3200
0x18006463c  cmp     eax, 4
0x18006463f  jbe     short loc_180064689
0x180064641  mov     eax, dword ptr [rbp+var_40]
0x180064644  lea     rdx, dword_1800A9F5C
0x18006464b  mov     dword ptr [rbp+var_40], eax
0x18006464e  lea     rax, aCallaudiorouti_0; "CallAudioRouting: Handover in progress,"...
0x180064655  mov     [rbp+var_18], rax
0x180064659  lea     rax, [rbp+var_40]
0x18006465d  mov     [rsp+80h+var_48], rax
0x180064662  lea     rax, [rbp+var_34]
0x180064666  mov     [rsp+80h+var_50], rax
0x18006466b  lea     rax, [rbp+var_38]
0x18006466f  mov     [rsp+80h+var_58], rax
0x180064674  lea     rax, [rbp+var_18]
0x180064678  mov     [rsp+80h+var_60], rax
0x18006467d  mov     [rbp+var_34], ebx
0x180064680  mov     [rbp+var_38], r12d
0x180064684  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180064689  xor     r13d, r13d
0x18006468c  jmp     short loc_180064692
0x18006468e  mov     r13d, [rbp+var_30]
0x180064692  mov     r15d, [rbp+var_2C]
0x180064696  cmp     [rbp+var_28], r15d
0x18006469a  jz      short loc_1800646E4
0x18006469c  jmp     loc_1800645B7
0x1800646a1  mov     rax, [rbp+var_40]
0x1800646a5  mov     rcx, rsi; lpCriticalSection
0x1800646a8  mov     [rax+0Ch], r15d
0x1800646ac  call    cs:__imp_LeaveCriticalSection
0x1800646b2  jmp     short loc_1800646CA
0x1800646b4  mov     r9d, 574h
0x1800646ba  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800646c1  mov     edx, edi
0x1800646c3  mov     ecx, eax
0x1800646c5  call    Log_HREvent_17
0x1800646ca  test    r13d, r13d
0x1800646cd  jnz     short loc_1800646D5
0x1800646cf  cmp     [rbp+var_28], r15d
0x1800646d3  jz      short loc_1800646E4
0x1800646d5  mov     r8d, dword ptr [rbp+var_20]; int
0x1800646d9  mov     edx, r12d; unsigned int
0x1800646dc  mov     rcx, r14; this
0x1800646df  call    ?_MuteCellularAudio@CallAudioRouting@@AEAAXIH@Z; CallAudioRouting::_MuteCellularAudio(uint,int)
0x1800646e4  mov     rbx, [rsp+80h+arg_18]
0x1800646ec  add     rsp, 80h
0x1800646f3  pop     r15
0x1800646f5  pop     r14
0x1800646f7  pop     r13
0x1800646f9  pop     r12
0x1800646fb  pop     rdi
0x1800646fc  pop     rsi
0x1800646fd  pop     rbp
0x1800646fe  retn
```
