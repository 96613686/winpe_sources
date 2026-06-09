# BdeSvcRegisterPersistentRequestTimerHandler(void)

- ea: `0x18005b934`
- end: `0x18005bce6`
- name: `?BdeSvcRegisterPersistentRequestTimerHandler@@YAJXZ`
- size: `946`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180044a70`
- `0x180045640`
- `0x18005b530`
- `0x18005b6e0`

## callees

- `0x180001fe8`
- `0x180002ad4`
- `0x180004894`
- `0x180009f30`
- `0x180009f60`
- `0x180024a18`
- `0x180024bbc`
- `0x1800261d8`
- `0x180030b08`
- `0x180034070`
- `0x18005b934`
- `0x18006a26c`
- `0x18006a594`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18005ba18`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18005ba18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b9a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b9a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bb93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bb93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bb36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bb36`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005bb26`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005bb26`

## string_xrefs

- `0x18005bb77`: `CreateTimerQueueTimer`

## pseudocode

```c
__int64 BdeSvcRegisterPersistentRequestTimerHandler(void)
{
  const wchar_t *v0; // rsi
  ULONG DueTime; // edi
  signed int PersistentRequestDelayTimerOverride; // ebx
  unsigned int PersistentRequestDelayTimer; // ebx
  __int64 v4; // rax
  HRESULT v5; // eax
  PVOID *v6; // rcx
  ULONG v7; // eax
  signed int LastError; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v12; // [rsp+40h] [rbp-69h] BYREF
  __int64 v13; // [rsp+48h] [rbp-61h] BYREF
  __int64 v14; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-51h] BYREF
  _QWORD v16[2]; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v17[2]; // [rsp+80h] [rbp-29h] BYREF
  ULONG pulResult; // [rsp+90h] [rbp-19h] BYREF
  _QWORD v19[6]; // [rsp+98h] [rbp-11h] BYREF

  LODWORD(v12) = 0;
  pulResult = 0;
  v0 = L"NA";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_8a3f59d54824346350fe913136af4d55_Traceguids);
  EnterCriticalSection(&gBdesvcPersistentReqTimerObjectCS);
  if ( g_persistentRequestTimerRegistered )
  {
    DueTime = 0;
    PersistentRequestDelayTimerOverride = 0;
  }
  else
  {
    PersistentRequestDelayTimerOverride = BdeSvcGetPersistentRequestDelayTimerOverride((int *)&v12, &pulResult);
    if ( PersistentRequestDelayTimerOverride >= 0 && (_DWORD)v12 )
    {
      DueTime = pulResult;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, pulResult);
    }
    else
    {
      PersistentRequestDelayTimer = FveGetPersistentRequestDelayTimer();
      v4 = (unsigned int)(rand() % 300);
      pulResult = v4;
      v5 = ULongLongToULong(1000 * v4, &pulResult);
      if ( v5 >= 0 )
      {
        v7 = pulResult;
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      else
      {
        v0 = L"ULongMult";
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            WPP_8a3f59d54824346350fe913136af4d55_Traceguids,
            (unsigned int)v5);
          v6 = (PVOID *)WPP_GLOBAL_Control;
        }
        v7 = 0;
      }
      DueTime = v7 + PersistentRequestDelayTimer;
      if ( v7 + PersistentRequestDelayTimer < v7 )
      {
        v0 = L"ULongAdd";
        if ( v6 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v6 + 28) & 2) != 0 )
          {
            WPP_SF_d(v6[2], 37, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, 2147942934LL);
            v6 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
            WPP_SF_(v6[2], 38, WPP_8a3f59d54824346350fe913136af4d55_Traceguids);
        }
        PersistentRequestDelayTimerOverride = 0;
        DueTime = FveGetPersistentRequestDelayTimer();
      }
      else
      {
        PersistentRequestDelayTimerOverride = 0;
      }
    }
    BdeSvcDeletePersistentRequestTimer();
    if ( CreateTimerQueueTimer(&g_hPersistentReqTimer, 0, BdeSvcPersistentRequestTimerHandler, 0, DueTime, 0, 0x10u) )
    {
      g_persistentRequestTimerRegistered = 1;
      FveResetPersistentRequestDelayTimer();
    }
    else
    {
      LastError = GetLastError();
      PersistentRequestDelayTimerOverride = LastError;
      if ( LastError > 0 )
        PersistentRequestDelayTimerOverride = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          WPP_8a3f59d54824346350fe913136af4d55_Traceguids,
          (unsigned int)PersistentRequestDelayTimerOverride);
      v0 = L"CreateTimerQueueTimer";
    }
  }
  LeaveCriticalSection(&gBdesvcPersistentReqTimerObjectCS);
  if ( PersistentRequestDelayTimerOverride < 0 )
  {
    v16[0] = 0;
    memset(v15, 0, sizeof(v15));
    pulResult = PersistentRequestDelayTimerOverride;
    v19[2] = L"hr";
    v19[3] = L"HRESULT";
    v19[4] = &pulResult;
    v19[5] = 4;
    v19[0] = v17;
    v19[1] = v17;
    v17[0] = v19;
    v17[1] = v19;
    v16[1] = FVEAPI_RP_TIMER_CREATION_FAILED;
    FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v15, (struct _FVEAPI_EVENT_DATA_COLLECTION *)v16);
    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v15);
    if ( (unsigned int)dword_18009A348 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
      {
        v13 = 0x1000000;
        v14 = (__int64)v0;
        pulResult = DueTime;
        LODWORD(v12) = PersistentRequestDelayTimerOverride;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          (int)&dword_18009A348,
          (int)&dword_18008DE5C,
          v9,
          v10,
          (__int64)&v12,
          (__int64)&pulResult,
          (const unsigned __int16 **)&v14,
          (__int64)&v13);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      WPP_8a3f59d54824346350fe913136af4d55_Traceguids,
      (unsigned int)PersistentRequestDelayTimerOverride);
  return (unsigned int)PersistentRequestDelayTimerOverride;
}

```

## disassembly

```asm
0x18005b934  push    rbp
0x18005b936  push    rbx
0x18005b937  push    rsi
0x18005b938  push    rdi
0x18005b939  push    r12
0x18005b93b  push    r15
0x18005b93d  lea     rbp, [rsp-2Fh]
0x18005b942  sub     rsp, 0D8h
0x18005b949  mov     rax, cs:__security_cookie
0x18005b950  xor     rax, rsp
0x18005b953  mov     [rbp+57h+var_38], rax
0x18005b957  mov     dword ptr [rbp+57h+var_C0], 0
0x18005b95e  mov     [rbp+57h+pulResult], 0
0x18005b965  lea     rsi, aNa; "NA"
0x18005b96c  lea     r15, WPP_GLOBAL_Control
0x18005b973  lea     r12, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005b97a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b981  cmp     rcx, r15
0x18005b984  jz      short loc_18005B99D
0x18005b986  test    byte ptr [rcx+1Ch], 20h
0x18005b98a  jz      short loc_18005B99D
0x18005b98c  mov     edx, 22h ; '"'
0x18005b991  mov     r8, r12
0x18005b994  mov     rcx, [rcx+10h]
0x18005b998  call    WPP_SF_
0x18005b99d  lea     rcx, ?gBdesvcPersistentReqTimerObjectCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005b9a4  call    cs:__imp_EnterCriticalSection
0x18005b9ab  nop     dword ptr [rax+rax+00h]
0x18005b9b0  cmp     cs:?g_persistentRequestTimerRegistered@@3_NA, 0; bool g_persistentRequestTimerRegistered
0x18005b9b7  jz      short loc_18005B9C2
0x18005b9b9  xor     edi, edi
0x18005b9bb  xor     ebx, ebx
0x18005b9bd  jmp     loc_18005BB8C
0x18005b9c2  lea     rdx, [rbp+57h+pulResult]; unsigned int *
0x18005b9c6  lea     rcx, [rbp+57h+var_C0]; int *
0x18005b9ca  call    ?BdeSvcGetPersistentRequestDelayTimerOverride@@YAJPEAHPEAK@Z; BdeSvcGetPersistentRequestDelayTimerOverride(int *,ulong *)
0x18005b9cf  mov     ebx, eax
0x18005b9d1  test    eax, eax
0x18005b9d3  js      short loc_18005BA11
0x18005b9d5  cmp     dword ptr [rbp+57h+var_C0], 0
0x18005b9d9  jz      short loc_18005BA11
0x18005b9db  mov     edi, [rbp+57h+pulResult]
0x18005b9de  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b9e5  cmp     rcx, r15
0x18005b9e8  jz      loc_18005BAFA
0x18005b9ee  test    byte ptr [rcx+1Ch], 8
0x18005b9f2  jz      loc_18005BAFA
0x18005b9f8  mov     edx, 23h ; '#'
0x18005b9fd  mov     r9d, edi
0x18005ba00  mov     r8, r12
0x18005ba03  mov     rcx, [rcx+10h]
0x18005ba07  call    WPP_SF_d
0x18005ba0c  jmp     loc_18005BAFA
0x18005ba11  call    ?FveGetPersistentRequestDelayTimer@@YAKXZ; FveGetPersistentRequestDelayTimer(void)
0x18005ba16  mov     ebx, eax
0x18005ba18  call    cs:__imp_rand
0x18005ba1f  nop     dword ptr [rax+rax+00h]
0x18005ba24  mov     ecx, eax
0x18005ba26  mov     eax, 1B4E81B5h
0x18005ba2b  imul    ecx
0x18005ba2d  sar     edx, 5
0x18005ba30  mov     eax, edx
0x18005ba32  shr     eax, 1Fh
0x18005ba35  add     edx, eax
0x18005ba37  imul    eax, edx, 12Ch
0x18005ba3d  sub     ecx, eax
0x18005ba3f  mov     eax, ecx
0x18005ba41  mov     [rbp+57h+pulResult], eax
0x18005ba44  imul    rcx, rax, 3E8h; ullOperand
0x18005ba4b  lea     rdx, [rbp+57h+pulResult]; pulResult
0x18005ba4f  call    ULongLongToULong
0x18005ba54  test    eax, eax
0x18005ba56  jns     short loc_18005BA90
0x18005ba58  lea     rsi, aUlongmult; "ULongMult"
0x18005ba5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba66  cmp     rcx, r15
0x18005ba69  jz      short loc_18005BA8C
0x18005ba6b  test    byte ptr [rcx+1Ch], 2
0x18005ba6f  jz      short loc_18005BA8C
0x18005ba71  mov     edx, 24h ; '$'
0x18005ba76  mov     r9d, eax
0x18005ba79  mov     r8, r12
0x18005ba7c  mov     rcx, [rcx+10h]
0x18005ba80  call    WPP_SF_d
0x18005ba85  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba8c  xor     eax, eax
0x18005ba8e  jmp     short loc_18005BA9A
0x18005ba90  mov     eax, [rbp+57h+pulResult]
0x18005ba93  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba9a  lea     edi, [rax+rbx]
0x18005ba9d  cmp     edi, eax
0x18005ba9f  jb      short loc_18005BAA5
0x18005baa1  xor     ebx, ebx
0x18005baa3  jmp     short loc_18005BAFA
0x18005baa5  lea     rsi, aUlongadd; "ULongAdd"
0x18005baac  cmp     rcx, r15
0x18005baaf  jz      short loc_18005BAF1
0x18005bab1  test    byte ptr [rcx+1Ch], 2
0x18005bab5  jz      short loc_18005BAD5
0x18005bab7  mov     edx, 25h ; '%'
0x18005babc  mov     r9d, 80070216h
0x18005bac2  mov     r8, r12
0x18005bac5  mov     rcx, [rcx+10h]
0x18005bac9  call    WPP_SF_d
0x18005bace  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bad5  cmp     rcx, r15
0x18005bad8  jz      short loc_18005BAF1
0x18005bada  test    byte ptr [rcx+1Ch], 8
0x18005bade  jz      short loc_18005BAF1
0x18005bae0  mov     edx, 26h ; '&'
0x18005bae5  mov     r8, r12
0x18005bae8  mov     rcx, [rcx+10h]
0x18005baec  call    WPP_SF_
0x18005baf1  xor     ebx, ebx
0x18005baf3  call    ?FveGetPersistentRequestDelayTimer@@YAKXZ; FveGetPersistentRequestDelayTimer(void)
0x18005baf8  mov     edi, eax
0x18005bafa  call    ?BdeSvcDeletePersistentRequestTimer@@YAXXZ; BdeSvcDeletePersistentRequestTimer(void)
0x18005baff  mov     [rsp+100h+Flags], 10h; Flags
0x18005bb07  mov     [rsp+100h+Period], 0; Period
0x18005bb0f  mov     [rsp+100h+DueTime], edi; DueTime
0x18005bb13  xor     r9d, r9d; Parameter
0x18005bb16  lea     r8, ?BdeSvcPersistentRequestTimerHandler@@YAXPEAXE@Z; Callback
0x18005bb1d  xor     edx, edx; TimerQueue
0x18005bb1f  lea     rcx, ?g_hPersistentReqTimer@@3PEAXEA; phNewTimer
0x18005bb26  call    cs:__imp_CreateTimerQueueTimer
0x18005bb2d  nop     dword ptr [rax+rax+00h]
0x18005bb32  test    eax, eax
0x18005bb34  jnz     short loc_18005BB80
0x18005bb36  call    cs:__imp_GetLastError
0x18005bb3d  nop     dword ptr [rax+rax+00h]
0x18005bb42  mov     ebx, eax
0x18005bb44  test    eax, eax
0x18005bb46  jle     short loc_18005BB51
0x18005bb48  movzx   ebx, ax
0x18005bb4b  or      ebx, 80070000h
0x18005bb51  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb58  cmp     rcx, r15
0x18005bb5b  jz      short loc_18005BB77
0x18005bb5d  test    byte ptr [rcx+1Ch], 2
0x18005bb61  jz      short loc_18005BB77
0x18005bb63  mov     edx, 27h ; '''
0x18005bb68  mov     r9d, ebx
0x18005bb6b  mov     r8, r12
0x18005bb6e  mov     rcx, [rcx+10h]
0x18005bb72  call    WPP_SF_d
0x18005bb77  lea     rsi, aCreatetimerque; "CreateTimerQueueTimer"
0x18005bb7e  jmp     short loc_18005BB8C
0x18005bb80  mov     cs:?g_persistentRequestTimerRegistered@@3_NA, 1; bool g_persistentRequestTimerRegistered
0x18005bb87  call    ?FveResetPersistentRequestDelayTimer@@YAXXZ; FveResetPersistentRequestDelayTimer(void)
0x18005bb8c  lea     rcx, ?gBdesvcPersistentReqTimerObjectCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005bb93  call    cs:__imp_LeaveCriticalSection
0x18005bb9a  nop     dword ptr [rax+rax+00h]
0x18005bb9f  test    ebx, ebx
0x18005bba1  jns     loc_18005BCA1
0x18005bba7  mov     [rbp+57h+var_90], 0
0x18005bbaf  mov     [rbp+57h+var_A8], 0
0x18005bbb7  mov     [rbp+57h+var_A0], 0
0x18005bbbf  mov     [rbp+57h+var_98], 0
0x18005bbc7  mov     [rbp+57h+pulResult], ebx
0x18005bbca  lea     rax, aHr; "hr"
0x18005bbd1  lea     rcx, aHresult; "HRESULT"
0x18005bbd8  lea     rdx, [rbp+57h+pulResult]
0x18005bbdc  mov     [rbp+57h+var_58], rax
0x18005bbe0  mov     [rbp+57h+var_50], rcx
0x18005bbe4  mov     [rbp+57h+var_48], rdx
0x18005bbe8  mov     [rbp+57h+var_40], 4
0x18005bbf0  lea     rax, [rbp+57h+var_80]
0x18005bbf4  mov     [rbp+57h+var_68], rax
0x18005bbf8  lea     rax, [rbp+57h+var_80]
0x18005bbfc  mov     [rbp+57h+var_60], rax
0x18005bc00  lea     rax, [rbp+57h+var_68]
0x18005bc04  mov     [rbp+57h+var_80], rax
0x18005bc08  lea     rax, [rbp+57h+var_68]
0x18005bc0c  mov     [rbp+57h+var_78], rax
0x18005bc10  lea     rax, FVEAPI_RP_TIMER_CREATION_FAILED
0x18005bc17  mov     [rbp+57h+var_88], rax
0x18005bc1b  lea     rdx, [rbp+57h+var_90]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x18005bc1f  lea     rcx, [rbp+57h+var_A8]; this
0x18005bc23  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x18005bc28  nop
0x18005bc29  lea     rcx, [rbp+57h+var_A8]; this
0x18005bc2d  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x18005bc32  nop
0x18005bc33  mov     eax, cs:dword_18009A348
0x18005bc39  cmp     eax, 5
0x18005bc3c  jbe     short loc_18005BCA1
0x18005bc3e  mov     rdx, 400000000000h
0x18005bc48  lea     rcx, dword_18009A348
0x18005bc4f  call    _tlgKeywordOn
0x18005bc54  test    al, al
0x18005bc56  jz      short loc_18005BCA1
0x18005bc58  mov     [rbp+57h+var_B8], 1000000h
0x18005bc60  mov     [rbp+57h+var_B0], rsi
0x18005bc64  mov     [rbp+57h+pulResult], edi
0x18005bc67  mov     dword ptr [rbp+57h+var_C0], ebx
0x18005bc6a  lea     rax, [rbp+57h+var_B8]
0x18005bc6e  mov     [rsp+100h+var_C8], rax; __int64
0x18005bc73  lea     rax, [rbp+57h+var_B0]
0x18005bc77  mov     qword ptr [rsp+100h+Flags], rax; __int64
0x18005bc7c  lea     rax, [rbp+57h+pulResult]
0x18005bc80  mov     qword ptr [rsp+100h+Period], rax; __int64
0x18005bc85  lea     rax, [rbp+57h+var_C0]
0x18005bc89  mov     qword ptr [rsp+100h+DueTime], rax; __int64
0x18005bc8e  lea     rdx, dword_18008DE5C
0x18005bc95  lea     rcx, dword_18009A348; int
0x18005bc9c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18005bca1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bca8  cmp     rcx, r15
0x18005bcab  jz      short loc_18005BCC7
0x18005bcad  test    byte ptr [rcx+1Ch], 20h
0x18005bcb1  jz      short loc_18005BCC7
0x18005bcb3  mov     edx, 28h ; '('
0x18005bcb8  mov     r9d, ebx
0x18005bcbb  mov     r8, r12
0x18005bcbe  mov     rcx, [rcx+10h]
0x18005bcc2  call    WPP_SF_d
0x18005bcc7  mov     eax, ebx
0x18005bcc9  mov     rcx, [rbp+57h+var_38]
0x18005bccd  xor     rcx, rsp; StackCookie
0x18005bcd0  call    __security_check_cookie
0x18005bcd5  add     rsp, 0D8h
0x18005bcdc  pop     r15
0x18005bcde  pop     r12
0x18005bce0  pop     rdi
0x18005bce1  pop     rsi
0x18005bce2  pop     rbx
0x18005bce3  pop     rbp
0x18005bce4  retn
```
