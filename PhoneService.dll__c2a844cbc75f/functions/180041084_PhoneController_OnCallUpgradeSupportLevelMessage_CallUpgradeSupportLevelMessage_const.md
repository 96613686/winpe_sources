# PhoneController::_OnCallUpgradeSupportLevelMessage(CallUpgradeSupportLevelMessage const *)

- ea: `0x180041084`
- end: `0x180041850`
- name: `?_OnCallUpgradeSupportLevelMessage@PhoneController@@IEAAJPEBVCallUpgradeSupportLevelMessage@@@Z`
- size: `1996`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct CallUpgradeSupportLevelMessage *)`
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800454bc`

## callees

- `0x180004370`
- `0x180006e94`
- `0x18001de50`
- `0x18001f514`
- `0x18002c574`
- `0x18002c580`
- `0x18003178c`
- `0x18003617c`
- `0x180036b60`
- `0x18003b9f0`
- `0x18003f550`
- `0x180041084`
- `0x180047a48`
- `0x180048b54`
- `0x180048c34`
- `0x18004ef10`
- `0x18004f420`
- `0x180051e44`
- `0x1800524c8`
- `0x180071114`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800412c4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800412c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004161e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180041712`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004161e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180041712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041677`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180041669`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180041669`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800416b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800417b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800416b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800417b3`

## string_xrefs

- `0x18004113f`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041179`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800411bd`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800411ef`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnCallUpgradeSupportLevelMessage(PhoneController *this, const struct _GUID *a2)
{
  int v4; // eax
  BackTraceCollection *v5; // rcx
  unsigned int v6; // r12d
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdi
  BackTraceCollection *v12; // rcx
  int v13; // eax
  BackTraceCollection *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int Data1; // ecx
  __int64 v18; // rbx
  unsigned int v19; // ecx
  __int64 v20; // rcx
  HRESULT v21; // eax
  BackTraceCollection *v22; // rcx
  unsigned int v23; // esi
  __int64 v24; // r9
  int AudioRouting; // eax
  BackTraceCollection *v26; // rcx
  int v27; // eax
  BackTraceCollection *v28; // rcx
  __int64 v29; // r9
  int v30; // eax
  BackTraceCollection *v31; // rcx
  int v32; // eax
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  int PhoneLine; // eax
  BackTraceCollection *v37; // rcx
  __int64 v38; // rsi
  int LineInfo; // eax
  BackTraceCollection *v40; // rcx
  __int64 v41; // rcx
  signed int LastError; // eax
  BackTraceCollection *v43; // rcx
  unsigned int v44; // r15d
  __int64 v45; // rcx
  int v46; // eax
  _WORD *v47; // rcx
  int v48; // eax
  __int128 v50; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v51; // [rsp+50h] [rbp-B0h]
  __int128 v52; // [rsp+60h] [rbp-A0h]
  WCHAR Buffer[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR lpBuffer[4]; // [rsp+78h] [rbp-88h] BYREF
  GUID pguid; // [rsp+80h] [rbp-80h] BYREF
  LPCRITICAL_SECTION v56[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v57[1340]; // [rsp+D0h] [rbp-30h] BYREF
  char v58; // [rsp+60Ch] [rbp+50Ch] BYREF
  va_list Arguments[2]; // [rsp+720h] [rbp+620h] BYREF

  memset_0(v56, 0, sizeof(v56));
  AutoLockWithWatchdog::AutoLockWithWatchdog(
    (AutoLockWithWatchdog *)v56,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 224),
    "PhoneController::_OnCallUpgradeSupportLevelMessage");
  v4 = PhoneController::_CheckControllerActive(this);
  v6 = 0;
  v7 = v4;
  if ( v4 < 0 )
  {
    BackTraceCollection::Capture(v5, v4);
    v8 = 7605;
    v9 = 1;
LABEL_5:
    Log_HREvent_7(v7, v9, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v8);
    goto LABEL_81;
  }
  v10 = *((_QWORD *)this + 12);
  *(_DWORD *)lpBuffer = *(_DWORD *)a2[3].Data4;
  *(_QWORD *)Buffer = 0;
  PhoneCallStorage::FindCall(v10, Buffer, lpBuffer, 0);
  v11 = *(_QWORD *)Buffer;
  if ( !*(_QWORD *)Buffer )
  {
    v8 = 7609;
    v9 = 0;
    v7 = -2147023728;
    goto LABEL_5;
  }
  v12 = (BackTraceCollection *)*(unsigned int *)(*(_QWORD *)Buffer + 3040LL);
  if ( (((_DWORD)v12 - 1) & 0xFFFFFFFA) == 0 && (_DWORD)v12 != 6 )
  {
    v7 = -2147019873;
    BackTraceCollection::Capture(v12, -2147019873);
    Log_HREvent_7(2147947423LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7612);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    goto LABEL_81;
  }
  v13 = PhoneController::_SetCallUpgradeInfo(this, (const unsigned int *)lpBuffer);
  v7 = v13;
  if ( v13 < 0 )
  {
    BackTraceCollection::Capture(v14, v13);
    Log_HREvent_7(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7615);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    goto LABEL_81;
  }
  *(_QWORD *)Buffer = 0;
  CallInfo::GetPhoneLine((CallInfo *)v11, (struct PhoneLine **)Buffer);
  Data1 = a2[3].Data1;
  v18 = *(_QWORD *)Buffer;
  if ( Data1 )
  {
    v19 = Data1 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( (_DWORD)v20 )
      {
        if ( (_DWORD)v20 != 1 )
        {
          Log_AssertionEvent_3(v20, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7736);
          MicrosoftTelemetryAssertTriggeredNoArgs();
          goto LABEL_76;
        }
        if ( (unsigned int)dword_1800B3238 > 5
          && (qword_1800B3248 & 0x200000000000LL) != 0
          && (qword_1800B3250 & 0x200000000000LL) == qword_1800B3250 )
        {
          *(_QWORD *)Buffer = 2048;
          *(_DWORD *)lpBuffer = *(_DWORD *)(v11 + 3068);
          Arguments[0] = "AppDeterminedUpgrade";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (int)&dword_1800B3238,
            (int)&word_1800A7B06,
            v15,
            v16,
            (const unsigned __int16 **)Arguments,
            (__int64)lpBuffer,
            (__int64)Buffer);
        }
      }
      pguid = 0;
      v21 = CoCreateGuid(&pguid);
      v23 = v21;
      if ( v21 < 0 )
      {
        BackTraceCollection::Capture(v22, v21);
        v24 = 7684;
LABEL_22:
        Log_HREvent_7(v23, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v24);
        goto LABEL_50;
      }
      *(_DWORD *)lpBuffer = 0;
      *(GUID *)(v11 + 6768) = pguid;
      AudioRouting = PhoneController::_GetAudioRouting(this, (enum CallAudioRoutingEndpoint *)lpBuffer, 0, 0);
      v23 = AudioRouting;
      if ( AudioRouting < 0 )
      {
        BackTraceCollection::Capture(v26, AudioRouting);
        v24 = 7690;
        goto LABEL_22;
      }
      if ( *(_DWORD *)lpBuffer == 1 )
      {
        v27 = PhoneController::_SetAudioRoutingEndpoint((__int64)this, 2u);
        v23 = v27;
        if ( v27 < 0 )
        {
          BackTraceCollection::Capture(v28, v27);
          v29 = 7694;
          goto LABEL_28;
        }
      }
      v50 = 0;
      v51 = 0;
      v52 = 0;
      PhoneController::_ComputeCallCounts(this, 1, (struct PH_PHONE_CALL_COUNTS *)&v50, 0);
      if ( HIDWORD(v51) <= 1 )
      {
        v32 = PhoneController::_InitiateVideoCallUpgrade(this);
        v23 = v32;
        if ( v32 < 0 )
        {
          BackTraceCollection::Capture(v31, v32);
          v29 = 7706;
LABEL_28:
          Log_HREvent_7(v23, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v29);
          if ( v18 )
            goto LABEL_51;
          goto LABEL_52;
        }
        if ( a2[3].Data1 == 2 && (unsigned int)dword_1800B3238 > 5 )
        {
          v31 = (BackTraceCollection *)qword_1800B3250;
          if ( (qword_1800B3248 & 0x200000000000LL) != 0 && (qword_1800B3250 & 0x200000000000LL) == qword_1800B3250 )
          {
            Arguments[0] = (va_list)2048;
            *(_DWORD *)lpBuffer = *(_DWORD *)(v11 + 3068);
            *(_QWORD *)Buffer = "SeamlessUpgrade";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              (int)&dword_1800B3238,
              (int)&unk_1800A7AC0,
              v33,
              v34,
              (const unsigned __int16 **)Buffer,
              (__int64)lpBuffer,
              (__int64)Arguments);
          }
        }
      }
      else
      {
        PhoneController::CallUpgradeInfo::SetPendingConfirmation((PhoneController *)((char *)this + 632), 1);
        *(_OWORD *)Arguments = *(_OWORD *)(v18 + 88);
        v30 = PhoneController::_SendDeferredControllerMessage((__int64)this, 52, (__int128 *)Arguments, 0, 0);
        if ( v30 < 0 )
          Log_HREvent_7(
            (unsigned int)v30,
            0,
            "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
            7702);
      }
      if ( a2[3].Data1 == 3 )
      {
        v35 = 12;
      }
      else
      {
        if ( a2[3].Data1 != 2 )
        {
          Log_AssertionEvent_3(v31, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7730);
          MicrosoftTelemetryAssertTriggeredNoArgs();
          goto LABEL_76;
        }
        v35 = 10;
      }
    }
    else
    {
      PhoneController::CallUpgradeInfo::SetPendingConfirmation((PhoneController *)((char *)this + 632), 1);
      v35 = 9;
    }
    CallInfo::SetCallUpgradeState(v11, v35);
LABEL_76:
    v48 = (*(__int64 (__fastcall **)(PhoneController *))(*(_QWORD *)this + 872LL))(this);
    if ( v48 < 0 )
      Log_HREvent_7((unsigned int)v48, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7739);
LABEL_78:
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v7 = v6;
    goto LABEL_81;
  }
  *(_QWORD *)Buffer = 0;
  memset_0(v57, 0, 0x650u);
  PhoneLine = PhoneLineStorage::GetPhoneLine(*((PhoneLineStorage **)this + 19), a2 + 2, (struct PhoneLine **)Buffer, 0);
  v23 = PhoneLine;
  if ( PhoneLine < 0 )
  {
    BackTraceCollection::Capture(v37, PhoneLine);
    Log_HREvent_7(v23, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7629);
    if ( *(_QWORD *)Buffer )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Buffer + 16LL))(*(_QWORD *)Buffer);
LABEL_50:
    if ( v18 )
LABEL_51:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_52:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v7 = v23;
    goto LABEL_81;
  }
  v38 = *(_QWORD *)Buffer;
  LineInfo = PhoneLine::GetLineInfo(*(PhoneLine **)Buffer, (struct PH_PROVIDERLINEINFO *)v57);
  v6 = LineInfo;
  if ( LineInfo < 0 )
  {
    BackTraceCollection::Capture(v40, LineInfo);
    Log_HREvent_7(v6, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7630);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_78;
  }
  Arguments[0] = (va_list)(v11 + 24);
  v6 = 0;
  Arguments[1] = &v58;
  *(_QWORD *)lpBuffer = 0;
  *(_QWORD *)Buffer = 0;
  if ( !LoadStringW(g_hInstRes, 0x2795u, Buffer, 0) )
  {
    Log_AssertionEvent_3(v41, "onecoreuap\\internal\\net\\inc\\phoneutil.h", 125);
    __int2c();
  }
  if ( FormatMessageW(0x2500u, *(LPCVOID *)Buffer, 0, 0, lpBuffer, 0, Arguments) )
  {
    *(_QWORD *)Buffer = 0;
    if ( !LoadStringW(g_hInstRes, 0x2794u, Buffer, 0) )
    {
      Log_AssertionEvent_3(v45, "onecoreuap\\internal\\net\\inc\\phoneutil.h", 125);
      __int2c();
    }
    pguid = *(GUID *)(v18 + 88);
    v46 = PhoneController::_SendDeferredControllerMessage(
            (__int64)this,
            53,
            (__int128 *)&pguid,
            *(__int64 *)lpBuffer,
            *(__int64 *)Buffer);
    if ( v46 < 0 )
      Log_HREvent_7((unsigned int)v46, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7650);
    *((_DWORD *)this + 158) = 0;
    *((_DWORD *)this + 163) = 0;
    *(GUID *)((char *)this + 636) = GUID_00000000_0000_0000_0000_000000000000;
    v47 = (_WORD *)*((_QWORD *)this + 82);
    *((_QWORD *)this + 83) = v47;
    *v47 = 0;
    CallInfo::SetCallUpgradeState(v11, 7);
    if ( *(_QWORD *)lpBuffer )
      LocalFree(*(HLOCAL *)lpBuffer);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_76;
  }
  LastError = GetLastError();
  v44 = LastError;
  if ( LastError > 0 )
    v44 = (unsigned __int16)LastError | 0x80070000;
  BackTraceCollection::Capture(v43, v44);
  Log_HREvent_7(v44, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7647);
  if ( *(_QWORD *)lpBuffer )
    LocalFree(*(HLOCAL *)lpBuffer);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v7 = v44;
LABEL_81:
  AutoLockWithWatchdog::~AutoLockWithWatchdog(v56);
  return v7;
}

```

## disassembly

```asm
0x180041084  mov     [rsp-8+arg_10], rbx
0x180041089  push    rbp
0x18004108a  push    rsi
0x18004108b  push    rdi
0x18004108c  push    r12
0x18004108e  push    r13
0x180041090  push    r14
0x180041092  push    r15
0x180041094  lea     rbp, [rsp-640h]
0x18004109c  sub     rsp, 740h
0x1800410a3  mov     rax, cs:__security_cookie
0x1800410aa  xor     rax, rsp
0x1800410ad  mov     [rbp+670h+var_40], rax
0x1800410b4  mov     r13, rdx
0x1800410b7  mov     r15, rcx
0x1800410ba  xor     edx, edx; Val
0x1800410bc  lea     rcx, [rbp+670h+var_6E0]; void *
0x1800410c0  lea     r8d, [rdx+40h]; Size
0x1800410c4  call    memset_0
0x1800410c9  lea     rdx, [r15+0E0h]; struct utl::recursive_mutex *
0x1800410d0  lea     r8, aPhonecontrolle_134; "PhoneController::_OnCallUpgradeSupportL"...
0x1800410d7  lea     rcx, [rbp+670h+var_6E0]; this
0x1800410db  call    ??0AutoLockWithWatchdog@@QEAA@PEAVrecursive_mutex@utl@@PEBD@Z; AutoLockWithWatchdog::AutoLockWithWatchdog(utl::recursive_mutex *,char const *)
0x1800410e0  mov     rcx, r15; this
0x1800410e3  call    ?_CheckControllerActive@PhoneController@@IEAAJXZ; PhoneController::_CheckControllerActive(void)
0x1800410e8  xor     r12d, r12d
0x1800410eb  mov     ebx, eax
0x1800410ed  test    eax, eax
0x1800410ef  jns     short loc_180041105
0x1800410f1  mov     edx, eax; int
0x1800410f3  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800410f8  mov     r9d, 1DB5h
0x1800410fe  lea     edx, [r12+1]
0x180041103  jmp     short loc_18004113F
0x180041105  mov     eax, [r13+38h]
0x180041109  lea     r8, [rsp+770h+var_6F8]
0x18004110e  mov     rcx, [r15+60h]
0x180041112  lea     rdx, [rsp+770h+Buffer]
0x180041117  xor     r9d, r9d
0x18004111a  mov     dword ptr [rsp+770h+var_6F8], eax
0x18004111e  mov     qword ptr [rsp+770h+Buffer], r12
0x180041123  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(uint const &,ISecurityToken *)
0x180041128  mov     rdi, qword ptr [rsp+770h+Buffer]
0x18004112d  test    rdi, rdi
0x180041130  jnz     short loc_180041152
0x180041132  mov     r9d, 1DB9h
0x180041138  xor     edx, edx
0x18004113a  mov     ebx, 80070490h
0x18004113f  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180041146  mov     ecx, ebx
0x180041148  call    Log_HREvent_7
0x18004114d  jmp     loc_18004181B
0x180041152  mov     ecx, [rdi+0BE0h]; this
0x180041158  lea     eax, [rcx-1]
0x18004115b  test    eax, 0FFFFFFFAh
0x180041160  jnz     short loc_18004119D
0x180041162  cmp     ecx, 6
0x180041165  jz      short loc_18004119D
0x180041167  mov     ebx, 8007139Fh
0x18004116c  mov     edx, ebx; int
0x18004116e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180041173  mov     r9d, 1DBCh
0x180041179  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180041180  xor     edx, edx
0x180041182  mov     ecx, ebx
0x180041184  call    Log_HREvent_7
0x180041189  mov     rax, [rdi]
0x18004118c  mov     rax, [rax+10h]
0x180041190  mov     rcx, rdi
0x180041193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041198  jmp     loc_18004181B
0x18004119d  lea     rdx, [rsp+770h+var_6F8]; unsigned int *
0x1800411a2  mov     rcx, r15; this
0x1800411a5  call    ?_SetCallUpgradeInfo@PhoneController@@IEAAJAEBI@Z; PhoneController::_SetCallUpgradeInfo(uint const &)
0x1800411aa  mov     ebx, eax
0x1800411ac  test    eax, eax
0x1800411ae  jns     short loc_1800411D9
0x1800411b0  mov     edx, eax; int
0x1800411b2  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800411b7  mov     r9d, 1DBFh
0x1800411bd  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800411c4  mov     edx, 1
0x1800411c9  mov     ecx, ebx
0x1800411cb  call    Log_HREvent_7
0x1800411d0  mov     rcx, [rdi]
0x1800411d3  mov     rax, [rcx+10h]
0x1800411d7  jmp     short loc_180041190
0x1800411d9  lea     rdx, [rsp+770h+Buffer]; struct PhoneLine **
0x1800411de  mov     qword ptr [rsp+770h+Buffer], r12
0x1800411e3  mov     rcx, rdi; this
0x1800411e6  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x1800411eb  mov     ecx, [r13+30h]
0x1800411ef  lea     r14, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800411f6  mov     rbx, qword ptr [rsp+770h+Buffer]
0x1800411fb  test    ecx, ecx
0x1800411fd  jz      loc_180041502
0x180041203  sub     ecx, 1
0x180041206  jz      loc_1800414DF
0x18004120c  mov     rdx, 200000000000h
0x180041216  sub     ecx, 1
0x180041219  jz      loc_1800412B9
0x18004121f  cmp     ecx, 1
0x180041222  jz      short loc_18004123C
0x180041224  mov     r8d, 1E38h
0x18004122a  mov     rdx, r14
0x18004122d  call    Log_AssertionEvent_3
0x180041232  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180041237  jmp     loc_1800417CD
0x18004123c  mov     eax, cs:dword_1800B3238
0x180041242  cmp     eax, 5
0x180041245  jbe     short loc_1800412B9
0x180041247  mov     rcx, cs:qword_1800B3250
0x18004124e  mov     rax, cs:qword_1800B3248
0x180041255  test    rdx, rax
0x180041258  jz      short loc_1800412B9
0x18004125a  mov     rax, rcx
0x18004125d  and     rax, rdx
0x180041260  cmp     rax, rcx
0x180041263  jnz     short loc_1800412B9
0x180041265  mov     qword ptr [rsp+770h+Buffer], 800h
0x18004126e  lea     rdx, word_1800A7B06
0x180041275  mov     eax, [rdi+0BFCh]
0x18004127b  lea     rcx, dword_1800B3238; int
0x180041282  mov     dword ptr [rsp+770h+var_6F8], eax
0x180041286  lea     rax, aAppdeterminedu; "AppDeterminedUpgrade"
0x18004128d  mov     [rbp+670h+var_50], rax
0x180041294  lea     rax, [rsp+770h+Buffer]
0x180041299  mov     [rsp+770h+Arguments], rax; __int64
0x18004129e  lea     rax, [rsp+770h+var_6F8]
0x1800412a3  mov     qword ptr [rsp+770h+nSize], rax; __int64
0x1800412a8  lea     rax, [rbp+670h+var_50]
0x1800412af  mov     [rsp+770h+lpBuffer], rax; __int64
0x1800412b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800412b9  xorps   xmm0, xmm0
0x1800412bc  lea     rcx, [rbp+670h+pguid]; pguid
0x1800412c0  movups  xmmword ptr [rbp+670h+pguid.Data1], xmm0
0x1800412c4  call    cs:__imp_CoCreateGuid
0x1800412ca  mov     esi, eax
0x1800412cc  test    eax, eax
0x1800412ce  jns     short loc_1800412F1
0x1800412d0  mov     edx, eax; int
0x1800412d2  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800412d7  mov     r9d, 1E04h
0x1800412dd  mov     r8, r14
0x1800412e0  mov     edx, 1
0x1800412e5  mov     ecx, esi
0x1800412e7  call    Log_HREvent_7
0x1800412ec  jmp     loc_180041568
0x1800412f1  movups  xmm0, xmmword ptr [rbp+670h+pguid.Data1]
0x1800412f5  xor     r9d, r9d; int *
0x1800412f8  mov     dword ptr [rsp+770h+var_6F8], r12d
0x1800412fd  xor     r8d, r8d; enum CallAudioRoutingPaths *
0x180041300  lea     rdx, [rsp+770h+var_6F8]; enum CallAudioRoutingEndpoint *
0x180041305  mov     rcx, r15; this
0x180041308  movdqu  xmmword ptr [rdi+1A70h], xmm0
0x180041310  call    ?_GetAudioRouting@PhoneController@@IEAAJPEAW4CallAudioRoutingEndpoint@@PEAW4CallAudioRoutingPaths@@PEAH@Z; PhoneController::_GetAudioRouting(CallAudioRoutingEndpoint *,CallAudioRoutingPaths *,int *)
0x180041315  mov     esi, eax
0x180041317  test    eax, eax
0x180041319  jns     short loc_18004132A
0x18004131b  mov     edx, eax; int
0x18004131d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180041322  mov     r9d, 1E0Ah
0x180041328  jmp     short loc_1800412DD
0x18004132a  cmp     dword ptr [rsp+770h+var_6F8], 1
0x18004132f  jnz     short loc_180041375
0x180041331  mov     edx, 2
0x180041336  mov     rcx, r15
0x180041339  call    ?_SetAudioRoutingEndpoint@PhoneController@@IEAAJW4CallAudioRoutingEndpoint@@@Z; PhoneController::_SetAudioRoutingEndpoint(CallAudioRoutingEndpoint)
0x18004133e  mov     esi, eax
0x180041340  test    eax, eax
0x180041342  jns     short loc_180041375
0x180041344  mov     edx, eax; int
0x180041346  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004134b  mov     r9d, 1E0Eh
0x180041351  mov     r8, r14
0x180041354  mov     edx, 1
0x180041359  mov     ecx, esi
0x18004135b  call    Log_HREvent_7
0x180041360  test    rbx, rbx
0x180041363  jz      loc_18004157C
0x180041369  mov     rcx, [rbx]
0x18004136c  mov     rax, [rcx+10h]
0x180041370  jmp     loc_180041574
0x180041375  xorps   xmm0, xmm0
0x180041378  lea     r8, [rsp+770h+var_730]; struct PH_PHONE_CALL_COUNTS *
0x18004137d  xor     r9d, r9d; struct ISecurityToken *
0x180041380  mov     rcx, r15; this
0x180041383  movups  [rsp+770h+var_730], xmm0
0x180041388  movups  [rsp+770h+var_720], xmm0
0x18004138d  lea     edx, [r9+1]; int
0x180041391  movups  [rsp+770h+var_710], xmm0
0x180041396  call    ?_ComputeCallCounts@PhoneController@@IEAAXHPEAUPH_PHONE_CALL_COUNTS@@PEAUISecurityToken@@@Z; PhoneController::_ComputeCallCounts(int,PH_PHONE_CALL_COUNTS *,ISecurityToken *)
0x18004139b  cmp     dword ptr [rsp+770h+var_720+0Ch], 1
0x1800413a0  jbe     short loc_1800413F9
0x1800413a2  lea     rcx, [r15+278h]; this
0x1800413a9  mov     edx, 1; int
0x1800413ae  call    ?SetPendingConfirmation@CallUpgradeInfo@PhoneController@@QEAAXH@Z; PhoneController::CallUpgradeInfo::SetPendingConfirmation(int)
0x1800413b3  movups  xmm0, xmmword ptr [rbx+58h]
0x1800413b7  xor     r9d, r9d
0x1800413ba  mov     [rsp+770h+lpBuffer], r12
0x1800413bf  lea     r8, [rbp+670h+var_50]
0x1800413c6  mov     rcx, r15
0x1800413c9  movdqu  xmmword ptr [rbp+670h+var_50], xmm0
0x1800413d1  lea     edx, [r9+34h]
0x1800413d5  call    ?_SendDeferredControllerMessage@PhoneController@@IEAAJW4tagPH_MSG@@AEBU_GUID@@PEBG2@Z; PhoneController::_SendDeferredControllerMessage(tagPH_MSG,_GUID const &,ushort const *,ushort const *)
0x1800413da  test    eax, eax
0x1800413dc  jns     loc_1800414AB
0x1800413e2  mov     r9d, 1E16h
0x1800413e8  mov     r8, r14
0x1800413eb  xor     edx, edx
0x1800413ed  mov     ecx, eax
0x1800413ef  call    Log_HREvent_7
0x1800413f4  jmp     loc_1800414AB
0x1800413f9  mov     rcx, r15; this
0x1800413fc  call    ?_InitiateVideoCallUpgrade@PhoneController@@IEAAJXZ; PhoneController::_InitiateVideoCallUpgrade(void)
0x180041401  mov     esi, eax
0x180041403  test    eax, eax
0x180041405  jns     short loc_180041419
0x180041407  mov     edx, eax; int
0x180041409  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004140e  mov     r9d, 1E1Ah
0x180041414  jmp     loc_180041351
0x180041419  cmp     dword ptr [r13+30h], 2
0x18004141e  jnz     loc_1800414AB
0x180041424  mov     eax, cs:dword_1800B3238
0x18004142a  cmp     eax, 5
0x18004142d  jbe     short loc_1800414AB
0x18004142f  mov     rcx, cs:qword_1800B3250
0x180041436  mov     rdx, 200000000000h
0x180041440  mov     rax, cs:qword_1800B3248
0x180041447  test    rdx, rax
0x18004144a  jz      short loc_1800414AB
0x18004144c  mov     rax, rcx
0x18004144f  and     rax, rdx
0x180041452  cmp     rax, rcx
0x180041455  jnz     short loc_1800414AB
0x180041457  mov     [rbp+670h+var_50], 800h
0x180041462  lea     rdx, unk_1800A7AC0
0x180041469  mov     eax, [rdi+0BFCh]
0x18004146f  lea     rcx, dword_1800B3238; int
0x180041476  mov     dword ptr [rsp+770h+var_6F8], eax
0x18004147a  lea     rax, aSeamlessupgrad; "SeamlessUpgrade"
0x180041481  mov     qword ptr [rsp+770h+Buffer], rax
0x180041486  lea     rax, [rbp+670h+var_50]
0x18004148d  mov     [rsp+770h+Arguments], rax; __int64
0x180041492  lea     rax, [rsp+770h+var_6F8]
0x180041497  mov     qword ptr [rsp+770h+nSize], rax; __int64
0x18004149c  lea     rax, [rsp+770h+Buffer]
0x1800414a1  mov     [rsp+770h+lpBuffer], rax; __int64
0x1800414a6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800414ab  cmp     dword ptr [r13+30h], 3
0x1800414b0  jnz     short loc_1800414B9
0x1800414b2  mov     edx, 0Ch
0x1800414b7  jmp     short loc_1800414F5
0x1800414b9  cmp     dword ptr [r13+30h], 2
0x1800414be  jnz     short loc_1800414C7
0x1800414c0  mov     edx, 0Ah
0x1800414c5  jmp     short loc_1800414F5
0x1800414c7  mov     r8d, 1E32h
0x1800414cd  mov     rdx, r14
0x1800414d0  call    Log_AssertionEvent_3
0x1800414d5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800414da  jmp     loc_1800417CD
0x1800414df  lea     rcx, [r15+278h]; this
0x1800414e6  mov     edx, 1; int
0x1800414eb  call    ?SetPendingConfirmation@CallUpgradeInfo@PhoneController@@QEAAXH@Z; PhoneController::CallUpgradeInfo::SetPendingConfirmation(int)
0x1800414f0  mov     edx, 9
0x1800414f5  mov     rcx, rdi
0x1800414f8  call    ?SetCallUpgradeState@CallInfo@@QEAAXW4CallUpgradeState@@@Z; CallInfo::SetCallUpgradeState(CallUpgradeState)
0x1800414fd  jmp     loc_1800417CD
0x180041502  xor     edx, edx; Val
0x180041504  mov     qword ptr [rsp+770h+Buffer], r12
0x180041509  mov     r8d, 650h; Size
0x18004150f  lea     rcx, [rbp+670h+var_6A0]; void *
0x180041513  call    memset_0
0x180041518  mov     rcx, [r15+98h]; this
0x18004151f  lea     rdx, [r13+20h]; struct _GUID *
0x180041523  xor     r9d, r9d; struct ISecurityToken *
0x180041526  lea     r8, [rsp+770h+Buffer]; struct PhoneLine **
0x18004152b  call    ?GetPhoneLine@PhoneLineStorage@@QEAAJAEBU_GUID@@PEAPEAVPhoneLine@@PEAUISecurityToken@@@Z; PhoneLineStorage::GetPhoneLine(_GUID const &,PhoneLine * *,ISecurityToken *)
0x180041530  mov     esi, eax
0x180041532  test    eax, eax
0x180041534  jns     short loc_180041592
0x180041536  mov     edx, eax; int
0x180041538  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004153d  mov     r9d, 1DCDh
0x180041543  mov     r8, r14
0x180041546  mov     edx, 1
0x18004154b  mov     ecx, esi
0x18004154d  call    Log_HREvent_7
0x180041552  mov     rcx, qword ptr [rsp+770h+Buffer]
0x180041557  test    rcx, rcx
0x18004155a  jz      short loc_180041568
0x18004155c  mov     rax, [rcx]
0x18004155f  mov     rax, [rax+10h]
0x180041563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041568  test    rbx, rbx
0x18004156b  jz      short loc_18004157C
0x18004156d  mov     rax, [rbx]
0x180041570  mov     rax, [rax+10h]
  ... truncated ...
```
