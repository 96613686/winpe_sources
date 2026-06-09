# CMpWatchdogServiceCallback::OnShutdown(void)

- ea: `0x1400895b0`
- end: `0x14008988e`
- name: `?OnShutdown@CMpWatchdogServiceCallback@@UEAAXXZ`
- size: `734`
- prototype: `void __fastcall(CMpWatchdogServiceCallback *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14001263c`
- `0x14003a5c0`
- `0x14007d1e0`
- `0x14007d210`
- `0x14007d774`
- `0x14008371c`
- `0x140085d38`
- `0x1400868b0`
- `0x1400869dc`
- `0x140088aa4`
- `0x1400895b0`
- `0x14008a988`
- `0x14008c8d8`
- `0x140166250`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x140089816`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140089816`
- `ADVAPI32!RegCloseKey` at `0x140089673`
- `ADVAPI32!RegCloseKey` at `0x1400896b3`
- `ADVAPI32!RegCloseKey` at `0x140089774`
- `ADVAPI32!RegCloseKey` at `0x140089673`
- `ADVAPI32!RegCloseKey` at `0x1400896b3`
- `ADVAPI32!RegCloseKey` at `0x140089774`

## pseudocode

```c
void __fastcall CMpWatchdogServiceCallback::OnShutdown(CMpWatchdogServiceCallback *this)
{
  int v1; // eax
  __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rbx
  MpWatchDog *v6; // rcx
  const wchar_t *v7; // r9
  bool v8; // bl
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  int v10; // [rsp+20h] [rbp-30h] BYREF
  __int128 v11; // [rsp+28h] [rbp-28h] BYREF
  int v12; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF

  HrReportStatusToSCM(3);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 74, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids);
  v12 = 0;
  hKey = 0;
  v1 = CommonUtil::UtilRegOpenKey(
         (CommonUtil *)&hKey,
         (HKEY *)0xFFFFFFFF80000002LL,
         (const WCHAR *)&stru_140194720,
         (const wchar_t *)1);
  if ( v1 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v3 = 71;
LABEL_8:
      WPP_SF_d(*(_QWORD *)(v2 + 16), v3, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids, (unsigned int)v1);
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  v10 = 0;
  v1 = MpWatchDog::ReadFeatureControlWithMiscConfigOverride(hKey, 150, &v10);
  if ( v1 >= 0 )
  {
    v8 = v10 != 0;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v8 )
      goto LABEL_29;
  }
  else
  {
    if ( v1 != -2147024894 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        v3 = 72;
        goto LABEL_8;
      }
LABEL_9:
      if ( hKey )
        RegCloseKey(hKey);
LABEL_29:
      CMpWatchdogServiceCallback::StopCoreServiceModules(&v12);
      goto LABEL_38;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  v11 = 0;
  hKey = (HKEY)&v12;
  std::async<_lambda_80ed01b7d3f000ddd85685ac9d9a15a1_,>(&v11, v4, &hKey);
  hKey = (HKEY)120;
  v5 = v11;
  if ( !(_QWORD)v11 || BYTE8(v11) && *(_BYTE *)(v11 + 184) )
    std::_Throw_future_error2(4);
  if ( (unsigned int)std::_Associated_state<int>::_Wait_for<__int64,std::ratio<1,1>>(v11, &hKey) )
  {
    v6 = (MpWatchDog *)WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      if ( v12 < 0 )
        v7 = L"Unknown";
      else
        v7 = (&off_1401D90D0)[4 * v12];
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 75, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids, v7);
    }
    MpWatchDog::WdTracingFlushTraceSession(v6);
    if ( v12 >= 0 )
    {
      HrReportStatusToSCM(1);
      __fastfail(7u);
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 8), 0xFFFFFFFF) == 1 )
  {
    v9 = *(void (__fastcall ****)(_QWORD, __int64))(v5 + 200);
    if ( v9 )
      (**v9)(v9, v5);
    else
      (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  }
LABEL_38:
  if ( gs_ServiceConfigureTimer )
  {
    DeleteTimerQueueTimer(0, gs_ServiceConfigureTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    gs_ServiceConfigureTimer = 0;
  }
  HrReportStatusToSCM(1);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      76,
      &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
      (unsigned int)g_ServiceError);
}

```

## disassembly

```asm
0x1400895b0  mov     [rsp-8+arg_0], rbx
0x1400895b5  mov     [rsp-8+arg_8], r14
0x1400895ba  mov     [rsp-8+arg_10], r15
0x1400895bf  push    rbp
0x1400895c0  mov     rbp, rsp
0x1400895c3  sub     rsp, 50h
0x1400895c7  mov     rax, cs:__security_cookie
0x1400895ce  xor     rax, rsp
0x1400895d1  mov     [rbp+var_8], rax
0x1400895d5  xor     edx, edx
0x1400895d7  lea     ecx, [rdx+3]
0x1400895da  call    HrReportStatusToSCM
0x1400895df  lea     r14, WPP_GLOBAL_Control
0x1400895e6  lea     r15, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x1400895ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400895f4  cmp     rcx, r14
0x1400895f7  jz      short loc_140089610
0x1400895f9  test    byte ptr [rcx+1Ch], 2
0x1400895fd  jz      short loc_140089610
0x1400895ff  mov     edx, 4Ah ; 'J'
0x140089604  mov     r8, r15
0x140089607  mov     rcx, [rcx+10h]
0x14008960b  call    WPP_SF_
0x140089610  mov     [rbp+var_18], 0
0x140089617  mov     [rbp+hKey], 0
0x14008961f  mov     r9d, 1; wchar_t *
0x140089625  lea     r8, stru_140194720; HKEY
0x14008962c  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x140089633  lea     rcx, [rbp+hKey]; this
0x140089637  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x14008963c  test    eax, eax
0x14008963e  jns     short loc_14008967E
0x140089640  mov     rcx, cs:WPP_GLOBAL_Control
0x140089647  cmp     rcx, r14
0x14008964a  jz      short loc_140089666
0x14008964c  test    byte ptr [rcx+1Ch], 1
0x140089650  jz      short loc_140089666
0x140089652  mov     edx, 47h ; 'G'
0x140089657  mov     r9d, eax
0x14008965a  mov     r8, r15
0x14008965d  mov     rcx, [rcx+10h]
0x140089661  call    WPP_SF_d
0x140089666  mov     rcx, [rbp+hKey]; hKey
0x14008966a  test    rcx, rcx
0x14008966d  jz      loc_140089782
0x140089673  call    cs:__imp_RegCloseKey
0x140089679  jmp     loc_140089782
0x14008967e  mov     [rbp+var_30], 0
0x140089685  lea     r8, [rbp+var_30]
0x140089689  mov     edx, 96h
0x14008968e  mov     rcx, [rbp+hKey]
0x140089692  call    ?ReadFeatureControlWithMiscConfigOverride@MpWatchDog@@YAJPEAUHKEY__@@W4FeatureControlEnum@@PEAK@Z; MpWatchDog::ReadFeatureControlWithMiscConfigOverride(HKEY__ *,FeatureControlEnum,ulong *)
0x140089697  test    eax, eax
0x140089699  jns     loc_140089764
0x14008969f  cmp     eax, 80070002h
0x1400896a4  jnz     loc_140089740
0x1400896aa  mov     rcx, [rbp+hKey]; hKey
0x1400896ae  test    rcx, rcx
0x1400896b1  jz      short loc_1400896B9
0x1400896b3  call    cs:__imp_RegCloseKey
0x1400896b9  xorps   xmm0, xmm0
0x1400896bc  movups  [rbp+var_28], xmm0
0x1400896c0  lea     rax, [rbp+var_18]
0x1400896c4  mov     [rbp+hKey], rax
0x1400896c8  lea     r8, [rbp+hKey]
0x1400896cc  lea     rcx, [rbp+var_28]
0x1400896d0  call    ??$async@V_lambda_80ed01b7d3f000ddd85685ac9d9a15a1_@@$$V@std@@YA?AV?$future@X@0@W4launch@0@$$QEAV_lambda_80ed01b7d3f000ddd85685ac9d9a15a1_@@@Z; std::async<_lambda_80ed01b7d3f000ddd85685ac9d9a15a1_,>(std::launch,_lambda_80ed01b7d3f000ddd85685ac9d9a15a1_ &&)
0x1400896d5  mov     [rbp+hKey], 78h ; 'x'
0x1400896dd  mov     rbx, qword ptr [rbp+var_28]
0x1400896e1  test    rbx, rbx
0x1400896e4  jz      loc_140089883
0x1400896ea  cmp     byte ptr [rbp+var_28+8], 0
0x1400896ee  jz      short loc_1400896FD
0x1400896f0  cmp     byte ptr [rbx+0B8h], 0
0x1400896f7  jnz     loc_140089883
0x1400896fd  lea     rdx, [rbp+hKey]
0x140089701  mov     rcx, rbx
0x140089704  call    ??$_Wait_for@_JU?$ratio@$00$00@std@@@?$_Associated_state@H@std@@QEAA?AW4future_status@1@AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@1@@Z; std::_Associated_state<int>::_Wait_for<__int64,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,1>> const &)
0x140089709  test    eax, eax
0x14008970b  jz      loc_1400897C6
0x140089711  mov     rcx, cs:WPP_GLOBAL_Control
0x140089718  cmp     rcx, r14
0x14008971b  jz      loc_1400897A5
0x140089721  test    byte ptr [rcx+1Ch], 1
0x140089725  jz      short loc_1400897A5
0x140089727  movsxd  rax, [rbp+var_18]
0x14008972b  test    eax, eax
0x14008972d  js      short loc_14008978D
0x14008972f  shl     rax, 5
0x140089733  lea     r9, off_1401D90D0; "WdTargetManager"
0x14008973a  mov     r9, [rax+r9]
0x14008973e  jmp     short loc_140089794
0x140089740  mov     rcx, cs:WPP_GLOBAL_Control
0x140089747  cmp     rcx, r14
0x14008974a  jz      loc_140089666
0x140089750  test    byte ptr [rcx+1Ch], 2
0x140089754  jz      loc_140089666
0x14008975a  mov     edx, 48h ; 'H'
0x14008975f  jmp     loc_140089657
0x140089764  cmp     [rbp+var_30], 0
0x140089768  setnz   bl
0x14008976b  mov     rcx, [rbp+hKey]; hKey
0x14008976f  test    rcx, rcx
0x140089772  jz      short loc_14008977A
0x140089774  call    cs:__imp_RegCloseKey
0x14008977a  test    bl, bl
0x14008977c  jz      loc_1400896B9
0x140089782  lea     rcx, [rbp+var_18]; int *
0x140089786  call    ?StopCoreServiceModules@CMpWatchdogServiceCallback@@SAXAEAH@Z; CMpWatchdogServiceCallback::StopCoreServiceModules(int &)
0x14008978b  jmp     short loc_140089804
0x14008978d  lea     r9, aUnknown_2; "Unknown"
0x140089794  mov     edx, 4Bh ; 'K'
0x140089799  mov     r8, r15
0x14008979c  mov     rcx, [rcx+10h]
0x1400897a0  call    WPP_SF_S
0x1400897a5  call    ?WdTracingFlushTraceSession@MpWatchDog@@YAJXZ; MpWatchDog::WdTracingFlushTraceSession(void)
0x1400897aa  cmp     [rbp+var_18], 0
0x1400897ae  jl      short loc_1400897C6
0x1400897b0  mov     edx, 80004005h
0x1400897b5  mov     ecx, 1
0x1400897ba  call    HrReportStatusToSCM
0x1400897bf  mov     ecx, 7
0x1400897c4  int     29h; Win8: RtlFailFast(ecx)
0x1400897c6  or      eax, 0FFFFFFFFh
0x1400897c9  lock xadd [rbx+8], eax
0x1400897ce  cmp     eax, 1
0x1400897d1  jnz     short loc_140089804
0x1400897d3  mov     rcx, [rbx+0C8h]
0x1400897da  test    rcx, rcx
0x1400897dd  jz      short loc_1400897F0
0x1400897df  mov     rax, [rcx]
0x1400897e2  mov     rdx, rbx
0x1400897e5  mov     rax, [rax]
0x1400897e8  call    cs:__guard_dispatch_icall_fptr
0x1400897ee  jmp     short loc_140089804
0x1400897f0  mov     rax, [rbx]
0x1400897f3  mov     edx, 1
0x1400897f8  mov     rcx, rbx
0x1400897fb  mov     rax, [rax]
0x1400897fe  call    cs:__guard_dispatch_icall_fptr
0x140089804  mov     rdx, cs:?gs_ServiceConfigureTimer@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A; Timer
0x14008980b  test    rdx, rdx
0x14008980e  jz      short loc_140089827
0x140089810  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x140089814  xor     ecx, ecx; TimerQueue
0x140089816  call    cs:__imp_DeleteTimerQueueTimer
0x14008981c  mov     cs:?gs_ServiceConfigureTimer@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A, 0; CommonUtil::CUniqueHandle<CommonUtil::CAutoDeleteTimerQueueTimer> gs_ServiceConfigureTimer
0x140089827  mov     edx, cs:?g_ServiceError@@3JA; long g_ServiceError
0x14008982d  mov     ecx, 1
0x140089832  call    HrReportStatusToSCM
0x140089837  mov     rcx, cs:WPP_GLOBAL_Control
0x14008983e  cmp     rcx, r14
0x140089841  jz      short loc_140089862
0x140089843  test    byte ptr [rcx+1Ch], 2
0x140089847  jz      short loc_140089862
0x140089849  mov     edx, 4Ch ; 'L'
0x14008984e  mov     r9d, cs:?g_ServiceError@@3JA; long g_ServiceError
0x140089855  mov     r8, r15
0x140089858  mov     rcx, [rcx+10h]
0x14008985c  call    WPP_SF_d
0x140089861  nop
0x140089862  mov     rcx, [rbp+var_8]
0x140089866  xor     rcx, rsp; StackCookie
0x140089869  call    __security_check_cookie
0x14008986e  mov     rbx, [rsp+50h+arg_0]
0x140089873  mov     r14, [rsp+50h+arg_8]
0x140089878  mov     r15, [rsp+50h+arg_10]
0x14008987d  add     rsp, 50h
0x140089881  pop     rbp
0x140089882  retn
0x140089883  mov     ecx, 4
0x140089888  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
