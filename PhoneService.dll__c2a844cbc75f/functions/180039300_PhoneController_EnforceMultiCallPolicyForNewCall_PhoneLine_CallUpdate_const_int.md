# PhoneController::_EnforceMultiCallPolicyForNewCall(PhoneLine *,CallUpdate const &,int *)

- ea: `0x180039300`
- end: `0x18003974d`
- name: `?_EnforceMultiCallPolicyForNewCall@PhoneController@@IEAAJPEAVPhoneLine@@AEBUCallUpdate@@PEAH@Z`
- size: `1101`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, struct PhoneLine *, const struct CallUpdate *, int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180041858`

## callees

- `0x180006e94`
- `0x18002c574`
- `0x18002c580`
- `0x180036b60`
- `0x180038264`
- `0x180039300`
- `0x18003de48`
- `0x18003fc04`
- `0x180046a20`
- `0x1800497b0`
- `0x18004b114`
- `0x18004ef10`
- `0x18005292c`
- `0x180053254`
- `0x1800536ac`
- `0x180070bb0`
- `0x18007f9ec`
- `0x18008d936`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039333`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039356`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800393f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039333`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039356`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800393f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039414`

## string_xrefs

- `0x180039339`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180039512`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_EnforceMultiCallPolicyForNewCall(
        PhoneController *this,
        struct PhoneLine *a2,
        const struct CallUpdate *a3,
        int *a4)
{
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  CallInfo *v12; // rbx
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r12
  int IsTwoIncomingCallsFromVoipAndBluetoothLines; // eax
  __int128 v18; // xmm1
  int v19; // r13d
  int v20; // eax
  __int64 v21; // rax
  CallInfo *v22; // rcx
  int v23; // eax
  BackTraceCollection *v24; // rcx
  unsigned int v25; // ebx
  unsigned int v27; // eax
  int v28; // ecx
  PhoneController *v29; // rcx
  __int64 v30; // rcx
  struct CallInfo *v31; // rdx
  struct CallInfo **v32; // rax
  struct CallInfo *v33; // rbx
  int v34; // eax
  BackTraceCollection *v35; // rcx
  __int128 Buf2; // [rsp+30h] [rbp-49h] BYREF
  __int128 v37; // [rsp+40h] [rbp-39h] BYREF
  __int128 v38; // [rsp+50h] [rbp-29h]
  __int128 v39; // [rsp+60h] [rbp-19h]
  __int128 Buf1; // [rsp+70h] [rbp-9h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1170);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  *a4 = 0;
  if ( *((_DWORD *)this + 78) && *((_DWORD *)a3 + 190) == 1 && (PhoneLine::GetCapabilities(a2) & 0x40) == 0 )
  {
    v9 = PhoneController::_RejectIncomingForError(this, a2, a3, 2);
    if ( v9 < 0 )
      Log_HREvent_7((unsigned int)v9, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1182);
    *a4 = 1;
  }
  v10 = *((unsigned int *)a3 + 190);
  if ( (_DWORD)v10 != 1 )
  {
    if ( (_DWORD)v10 == 5 )
      return 0;
    if ( (*((_DWORD *)a3 + 2) & 0x400000) != 0 && *((_DWORD *)a3 + 625) )
    {
      if ( (_DWORD)v10 != 2 )
      {
        Log_AssertionEvent_3(v10, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1246);
        if ( *((_DWORD *)a3 + 190) != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      return 0;
    }
    v37 = 0;
    v38 = 0;
    v39 = 0;
    PhoneController::_ComputeCallCounts(this, 1, (struct PH_PHONE_CALL_COUNTS *)&v37, 0);
    if ( (unsigned int)(v38 + HIDWORD(v38)) < 2 )
    {
      if ( (_DWORD)v38 + (_DWORD)v37 + DWORD1(v38) != 1 )
        return 0;
      v27 = *((_DWORD *)a3 + 190);
      if ( v27 > 6 )
        return 0;
      v28 = 77;
      if ( !_bittest(&v28, v27)
        || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calling_Fix_BluetoothAudioRoutingMultiCallPolicy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calling_Fix_BluetoothAudioRoutingMultiCallPolicy>::GetImpl'::`2'::impl)
        && PhoneController::_ShouldSkipMultiCallPolicyForBluetoothHfp(v29, a2) )
      {
        return 0;
      }
      v30 = *((_QWORD *)this + 12);
      *(_QWORD *)&Buf1 = 0;
      PhoneCallStorage::GetActiveCall(v30, &Buf1);
      v31 = (struct CallInfo *)Buf1;
      if ( !(_QWORD)Buf1 )
      {
        v32 = (struct CallInfo **)PhoneCallStorage::FindCallByState(*((_QWORD *)this + 12), &Buf2, 2, 0);
        v31 = (struct CallInfo *)Buf1;
        v33 = *v32;
        if ( (struct CallInfo *)Buf1 != *v32 )
        {
          if ( v33 )
          {
            (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v33 + 8LL))(*v32);
            v31 = (struct CallInfo *)Buf1;
          }
          if ( v31 )
            (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v31 + 16LL))(v31);
          v31 = v33;
          *(_QWORD *)&Buf1 = v33;
        }
        if ( (_QWORD)Buf2 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Buf2 + 16LL))(Buf2);
          v31 = (struct CallInfo *)Buf1;
        }
      }
      v34 = PhoneController::_HoldOrEndCall(this, v31);
      v25 = v34;
      if ( v34 >= 0 )
      {
        v22 = (CallInfo *)Buf1;
        if ( (_QWORD)Buf1 )
        {
          v21 = *(_QWORD *)Buf1;
          goto LABEL_57;
        }
        return 0;
      }
      BackTraceCollection::Capture(v35, v34);
      Log_HREvent_7(v25, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1282);
      if ( (_QWORD)Buf1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Buf1 + 16LL))(Buf1);
    }
    else
    {
      v23 = PhoneController::_EndActiveOrFirstHeldCall(this);
      v25 = v23;
      if ( v23 >= 0 )
        return 0;
      BackTraceCollection::Capture(v24, v23);
      Log_HREvent_7(v25, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1259);
    }
    return v25;
  }
  v11 = *((_QWORD *)this + 12);
  *(_QWORD *)&Buf1 = 0;
  PhoneCallStorage::FindCallByState(v11, &Buf1, 1, 0);
  v12 = (CallInfo *)Buf1;
  if ( (_QWORD)Buf1 )
  {
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
    {
      Log_AssertionEvent_3(v13, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1598);
      if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v14 = PhoneCallStorage::GetCallCountByState(*((_QWORD *)this + 12), 1);
    if ( v14 <= 2 )
    {
      if ( v14 <= 1 )
      {
        if ( v14 != 1 )
        {
          Log_AssertionEvent_3(v15, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1204);
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        *(_QWORD *)&Buf1 = 0;
        CallInfo::GetPhoneLine(v12, (struct PhoneLine **)&Buf1);
        v16 = Buf1;
        IsTwoIncomingCallsFromVoipAndBluetoothLines = _IsTwoIncomingCallsFromVoipAndBluetoothLines(
                                                        (struct PhoneLine *)Buf1,
                                                        a2);
        v18 = *(_OWORD *)(v16 + 88);
        v19 = IsTwoIncomingCallsFromVoipAndBluetoothLines;
        Buf2 = *(_OWORD *)((char *)a2 + 88);
        Buf1 = v18;
        if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
        {
          Buf2 = *(_OWORD *)(v16 + 112);
          if ( !memcmp_0(&Buf2, &CellularLineType, 0x10u) )
          {
            Buf2 = *((_OWORD *)a2 + 7);
            if ( !memcmp_0(&Buf2, &CellularLineType, 0x10u) )
              goto LABEL_27;
          }
        }
        if ( v19 )
          goto LABEL_27;
      }
    }
    else
    {
      Log_AssertionEvent_3(v15, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1604);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v20 = PhoneController::_RejectIncomingForError(this, a2, a3, 1);
    if ( v20 < 0 )
      Log_HREvent_7((unsigned int)v20, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1223);
    *a4 = 1;
LABEL_27:
    v21 = *(_QWORD *)v12;
    v22 = v12;
LABEL_57:
    (*(void (__fastcall **)(CallInfo *))(v21 + 16))(v22);
  }
  return 0;
}

```

## disassembly

```asm
0x180039300  push    rbp
0x180039302  push    rbx
0x180039303  push    rsi
0x180039304  push    rdi
0x180039305  push    r12
0x180039307  push    r13
0x180039309  push    r14
0x18003930b  push    r15
0x18003930d  lea     rbp, [rsp-1Fh]
0x180039312  sub     rsp, 98h
0x180039319  mov     rax, cs:__security_cookie
0x180039320  xor     rax, rsp
0x180039323  mov     [rbp+57h+var_50], rax
0x180039327  mov     r15, r9
0x18003932a  mov     rsi, r8
0x18003932d  mov     r14, rdx
0x180039330  mov     rdi, rcx
0x180039333  call    cs:__imp_GetCurrentThreadId
0x180039339  lea     r13, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180039340  cmp     [rdi+0F0h], eax
0x180039346  jz      short loc_180039369
0x180039348  mov     r8d, 492h
0x18003934e  mov     rdx, r13
0x180039351  call    Log_AssertionEvent_3
0x180039356  call    cs:__imp_GetCurrentThreadId
0x18003935c  cmp     [rdi+0F0h], eax
0x180039362  jz      short loc_180039369
0x180039364  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039369  mov     ebx, 2
0x18003936e  mov     dword ptr [r15], 0
0x180039375  cmp     dword ptr [rdi+138h], 0
0x18003937c  lea     r12d, [rbx-1]
0x180039380  jz      short loc_1800393C1
0x180039382  cmp     [rsi+2F8h], r12d
0x180039389  jnz     short loc_1800393C1
0x18003938b  mov     rcx, r14
0x18003938e  call    ?GetCapabilities@PhoneLine@@QEAA?AW4PhoneLineCapabilities@@XZ; PhoneLine::GetCapabilities(void)
0x180039393  test    al, 40h
0x180039395  jnz     short loc_1800393C1
0x180039397  mov     r9d, ebx
0x18003939a  mov     r8, rsi
0x18003939d  mov     rdx, r14
0x1800393a0  mov     rcx, rdi
0x1800393a3  call    ?_RejectIncomingForError@PhoneController@@IEAAJPEAVPhoneLine@@AEBIW4RejectIncomingReason@@@Z; PhoneController::_RejectIncomingForError(PhoneLine *,uint const &,RejectIncomingReason)
0x1800393a8  test    eax, eax
0x1800393aa  jns     short loc_1800393BE
0x1800393ac  mov     r9d, 49Eh
0x1800393b2  mov     r8, r13
0x1800393b5  xor     edx, edx
0x1800393b7  mov     ecx, eax
0x1800393b9  call    Log_HREvent_7
0x1800393be  mov     [r15], r12d
0x1800393c1  mov     ecx, [rsi+2F8h]
0x1800393c7  cmp     ecx, r12d
0x1800393ca  jnz     loc_18003954E
0x1800393d0  mov     rcx, [rdi+60h]
0x1800393d4  lea     rdx, [rbp+57h+Buf1]
0x1800393d8  xor     r9d, r9d
0x1800393db  mov     qword ptr [rbp+57h+Buf1], 0
0x1800393e3  mov     r8d, r12d
0x1800393e6  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x1800393eb  mov     rbx, qword ptr [rbp+57h+Buf1]
0x1800393ef  test    rbx, rbx
0x1800393f2  jz      loc_18003972B
0x1800393f8  call    cs:__imp_GetCurrentThreadId
0x1800393fe  cmp     [rdi+0F0h], eax
0x180039404  jz      short loc_180039427
0x180039406  mov     r8d, 63Eh
0x18003940c  mov     rdx, r13
0x18003940f  call    Log_AssertionEvent_3
0x180039414  call    cs:__imp_GetCurrentThreadId
0x18003941a  cmp     [rdi+0F0h], eax
0x180039420  jz      short loc_180039427
0x180039422  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039427  mov     rcx, [rdi+60h]
0x18003942b  mov     edx, r12d
0x18003942e  call    ?GetCallCountByState@PhoneCallStorage@@QEAAIW4PH_CALLSTATE@@@Z; PhoneCallStorage::GetCallCountByState(PH_CALLSTATE)
0x180039433  cmp     eax, 2
0x180039436  jbe     short loc_180039450
0x180039438  mov     r8d, 644h
0x18003943e  mov     rdx, r13
0x180039441  call    Log_AssertionEvent_3
0x180039446  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003944b  jmp     loc_180039519
0x180039450  cmp     eax, r12d
0x180039453  ja      loc_180039519
0x180039459  jz      short loc_18003946E
0x18003945b  mov     r8d, 4B4h
0x180039461  mov     rdx, r13
0x180039464  call    Log_AssertionEvent_3
0x180039469  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003946e  lea     rdx, [rbp+57h+Buf1]; struct PhoneLine **
0x180039472  mov     qword ptr [rbp+57h+Buf1], 0
0x18003947a  mov     rcx, rbx; this
0x18003947d  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x180039482  mov     r12, qword ptr [rbp+57h+Buf1]
0x180039486  mov     rdx, r14; struct PhoneLine *
0x180039489  mov     rcx, r12; struct PhoneLine *
0x18003948c  call    ?_IsTwoIncomingCallsFromVoipAndBluetoothLines@@YAHPEAVPhoneLine@@0@Z; _IsTwoIncomingCallsFromVoipAndBluetoothLines(PhoneLine *,PhoneLine *)
0x180039491  movups  xmm0, xmmword ptr [r14+58h]
0x180039496  mov     r8d, 10h; Size
0x18003949c  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1800394a0  movups  xmm1, xmmword ptr [r12+58h]
0x1800394a6  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800394aa  mov     r13d, eax
0x1800394ad  movdqu  [rbp+57h+Buf2], xmm0
0x1800394b2  movdqu  [rbp+57h+Buf1], xmm1
0x1800394b7  call    memcmp_0
0x1800394bc  test    eax, eax
0x1800394be  jz      short loc_180039509
0x1800394c0  movups  xmm0, xmmword ptr [r12+70h]
0x1800394c6  mov     r12d, 10h
0x1800394cc  lea     rdx, CellularLineType; Buf2
0x1800394d3  mov     r8d, r12d; Size
0x1800394d6  lea     rcx, [rbp+57h+Buf2]; Buf1
0x1800394da  movdqu  [rbp+57h+Buf2], xmm0
0x1800394df  call    memcmp_0
0x1800394e4  test    eax, eax
0x1800394e6  jnz     short loc_180039509
0x1800394e8  movups  xmm0, xmmword ptr [r14+70h]
0x1800394ed  mov     r8d, r12d; Size
0x1800394f0  lea     rdx, CellularLineType; Buf2
0x1800394f7  lea     rcx, [rbp+57h+Buf2]; Buf1
0x1800394fb  movdqu  [rbp+57h+Buf2], xmm0
0x180039500  call    memcmp_0
0x180039505  test    eax, eax
0x180039507  jz      short loc_180039543
0x180039509  test    r13d, r13d
0x18003950c  jnz     short loc_180039543
0x18003950e  lea     r12d, [r13+1]
0x180039512  lea     r13, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180039519  mov     r9d, r12d
0x18003951c  mov     r8, rsi
0x18003951f  mov     rdx, r14
0x180039522  mov     rcx, rdi
0x180039525  call    ?_RejectIncomingForError@PhoneController@@IEAAJPEAVPhoneLine@@AEBIW4RejectIncomingReason@@@Z; PhoneController::_RejectIncomingForError(PhoneLine *,uint const &,RejectIncomingReason)
0x18003952a  test    eax, eax
0x18003952c  jns     short loc_180039540
0x18003952e  mov     r9d, 4C7h
0x180039534  mov     r8, r13
0x180039537  xor     edx, edx
0x180039539  mov     ecx, eax
0x18003953b  call    Log_HREvent_7
0x180039540  mov     [r15], r12d
0x180039543  mov     rax, [rbx]
0x180039546  mov     rcx, rbx
0x180039549  jmp     loc_180039722
0x18003954e  cmp     ecx, 5
0x180039551  jz      loc_18003972B
0x180039557  mov     eax, [rsi+8]
0x18003955a  bt      rax, 16h
0x18003955f  jnb     short loc_180039596
0x180039561  cmp     dword ptr [rsi+9C4h], 0
0x180039568  jz      short loc_180039596
0x18003956a  cmp     ecx, ebx
0x18003956c  jz      loc_18003972B
0x180039572  mov     r8d, 4DEh
0x180039578  mov     rdx, r13
0x18003957b  call    Log_AssertionEvent_3
0x180039580  cmp     [rsi+2F8h], ebx
0x180039586  jz      loc_18003972B
0x18003958c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039591  jmp     loc_18003972B
0x180039596  xorps   xmm0, xmm0
0x180039599  lea     r8, [rbp+57h+var_90]; struct PH_PHONE_CALL_COUNTS *
0x18003959d  xor     r9d, r9d; struct ISecurityToken *
0x1800395a0  mov     edx, r12d; int
0x1800395a3  mov     rcx, rdi; this
0x1800395a6  movups  [rbp+57h+var_90], xmm0
0x1800395aa  movups  [rbp+57h+var_80], xmm0
0x1800395ae  movups  [rbp+57h+var_70], xmm0
0x1800395b2  call    ?_ComputeCallCounts@PhoneController@@IEAAXHPEAUPH_PHONE_CALL_COUNTS@@PEAUISecurityToken@@@Z; PhoneController::_ComputeCallCounts(int,PH_PHONE_CALL_COUNTS *,ISecurityToken *)
0x1800395b7  mov     ecx, dword ptr [rbp+57h+var_80+0Ch]
0x1800395ba  mov     r8d, dword ptr [rbp+57h+var_80]
0x1800395be  add     ecx, r8d
0x1800395c1  cmp     ecx, ebx
0x1800395c3  jb      short loc_1800395F8
0x1800395c5  mov     rcx, rdi; this
0x1800395c8  call    ?_EndActiveOrFirstHeldCall@PhoneController@@IEAAJXZ; PhoneController::_EndActiveOrFirstHeldCall(void)
0x1800395cd  mov     ebx, eax
0x1800395cf  test    eax, eax
0x1800395d1  jns     loc_18003972B
0x1800395d7  mov     edx, eax; int
0x1800395d9  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800395de  mov     r9d, 4EBh
0x1800395e4  mov     r8, r13
0x1800395e7  mov     edx, r12d
0x1800395ea  mov     ecx, ebx
0x1800395ec  call    Log_HREvent_7
0x1800395f1  mov     eax, ebx
0x1800395f3  jmp     loc_18003972D
0x1800395f8  mov     edx, dword ptr [rbp+57h+var_80+4]
0x1800395fb  add     edx, dword ptr [rbp+57h+var_90]
0x1800395fe  add     edx, r8d
0x180039601  cmp     edx, r12d
0x180039604  jnz     loc_18003972B
0x18003960a  mov     eax, [rsi+2F8h]
0x180039610  cmp     eax, 6
0x180039613  ja      loc_18003972B
0x180039619  mov     ecx, 4Dh ; 'M'
0x18003961e  bt      ecx, eax
0x180039621  jnb     loc_18003972B
0x180039627  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calling_Fix_BluetoothAudioRoutingMultiCallPolicy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calling_Fix_BluetoothAudioRoutingMultiCallPolicy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calling_Fix_BluetoothAudioRoutingMultiCallPolicy> `wil::Feature<__WilFeatureTraits_Feature_Calling_Fix_BluetoothAudioRoutingMultiCallPolicy>::GetImpl(void)'::`2'::impl
0x18003962e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calling_Fix_BluetoothAudioRoutingMultiCallPolicy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calling_Fix_BluetoothAudioRoutingMultiCallPolicy>::__private_IsEnabled(void)
0x180039633  test    al, al
0x180039635  jz      short loc_180039647
0x180039637  mov     rdx, r14; struct PhoneLine *
0x18003963a  call    ?_ShouldSkipMultiCallPolicyForBluetoothHfp@PhoneController@@IEBAHPEAVPhoneLine@@@Z; PhoneController::_ShouldSkipMultiCallPolicyForBluetoothHfp(PhoneLine *)
0x18003963f  test    eax, eax
0x180039641  jnz     loc_18003972B
0x180039647  mov     rcx, [rdi+60h]
0x18003964b  lea     rdx, [rbp+57h+Buf1]
0x18003964f  mov     qword ptr [rbp+57h+Buf1], 0
0x180039657  call    ?GetActiveCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@XZ; PhoneCallStorage::GetActiveCall(void)
0x18003965c  mov     rdx, qword ptr [rbp+57h+Buf1]
0x180039660  test    rdx, rdx
0x180039663  jnz     short loc_1800396D0
0x180039665  mov     rcx, [rdi+60h]
0x180039669  lea     rdx, [rbp+57h+Buf2]
0x18003966d  xor     r9d, r9d
0x180039670  mov     r8d, ebx
0x180039673  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x180039678  mov     rdx, qword ptr [rbp+57h+Buf1]
0x18003967c  mov     rbx, [rax]
0x18003967f  cmp     rdx, rbx
0x180039682  jz      short loc_1800396B7
0x180039684  test    rbx, rbx
0x180039687  jz      short loc_18003969C
0x180039689  mov     rax, [rbx]
0x18003968c  mov     rcx, rbx
0x18003968f  mov     rax, [rax+8]
0x180039693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039698  mov     rdx, qword ptr [rbp+57h+Buf1]
0x18003969c  test    rdx, rdx
0x18003969f  jz      short loc_1800396B0
0x1800396a1  mov     rax, [rdx]
0x1800396a4  mov     rcx, rdx
0x1800396a7  mov     rax, [rax+10h]
0x1800396ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396b0  mov     rdx, rbx
0x1800396b3  mov     qword ptr [rbp+57h+Buf1], rbx
0x1800396b7  mov     rcx, qword ptr [rbp+57h+Buf2]
0x1800396bb  test    rcx, rcx
0x1800396be  jz      short loc_1800396D0
0x1800396c0  mov     rax, [rcx]
0x1800396c3  mov     rax, [rax+10h]
0x1800396c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396cc  mov     rdx, qword ptr [rbp+57h+Buf1]; struct CallInfo *
0x1800396d0  mov     rcx, rdi; this
0x1800396d3  call    ?_HoldOrEndCall@PhoneController@@IEAAJPEAVCallInfo@@@Z; PhoneController::_HoldOrEndCall(CallInfo *)
0x1800396d8  mov     ebx, eax
0x1800396da  test    eax, eax
0x1800396dc  jns     short loc_180039716
0x1800396de  mov     edx, eax; int
0x1800396e0  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800396e5  mov     r9d, 502h
0x1800396eb  mov     r8, r13
0x1800396ee  mov     edx, r12d
0x1800396f1  mov     ecx, ebx
0x1800396f3  call    Log_HREvent_7
0x1800396f8  mov     rcx, qword ptr [rbp+57h+Buf1]
0x1800396fc  test    rcx, rcx
0x1800396ff  jz      loc_1800395F1
0x180039705  mov     rax, [rcx]
0x180039708  mov     rax, [rax+10h]
0x18003970c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039711  jmp     loc_1800395F1
0x180039716  mov     rcx, qword ptr [rbp+57h+Buf1]
0x18003971a  test    rcx, rcx
0x18003971d  jz      short loc_18003972B
0x18003971f  mov     rax, [rcx]
0x180039722  mov     rax, [rax+10h]
0x180039726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003972b  xor     eax, eax
0x18003972d  mov     rcx, [rbp+57h+var_50]
0x180039731  xor     rcx, rsp; StackCookie
0x180039734  call    __security_check_cookie
0x180039739  add     rsp, 98h
0x180039740  pop     r15
0x180039742  pop     r14
0x180039744  pop     r13
0x180039746  pop     r12
0x180039748  pop     rdi
0x180039749  pop     rsi
0x18003974a  pop     rbx
0x18003974b  pop     rbp
0x18003974c  retn
```
