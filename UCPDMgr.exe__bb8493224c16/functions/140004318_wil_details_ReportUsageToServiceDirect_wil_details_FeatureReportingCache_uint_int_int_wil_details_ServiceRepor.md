# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x140004318`
- end: `0x140004523`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `523`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x14000452c`

## callees

- `0x140002e50`
- `0x140003b20`
- `0x140004070`
- `0x140004318`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400043fb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400044a7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400043fb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400044a7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400043c2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000445b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400043c2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000445b`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        __int64 a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  __int64 v12; // rax
  __m128i v13; // xmm1
  unsigned int v14; // ebx
  unsigned __int64 v15; // r8
  __int64 v16; // r8
  void (__fastcall *v17)(_QWORD, _QWORD, __int64, _QWORD); // rax
  int v18; // edi
  void (__fastcall *v19)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v20; // rdx
  void (__fastcall *v21)(_QWORD, __int64, _QWORD, _QWORD); // rax
  bool v22; // zf
  _DWORD v24[2]; // [rsp+30h] [rbp-78h] BYREF
  __int64 v25; // [rsp+38h] [rbp-70h]
  __m128i v26; // [rsp+40h] [rbp-68h]
  __int64 v27; // [rsp+60h] [rbp-48h]
  _BYTE v28[64]; // [rsp+68h] [rbp-40h] BYREF

  v12 = wil_details_FeatureReporting_RecordUsageInCache(v28, a1, a5);
  v13 = *(__m128i *)v12;
  v26 = *(__m128i *)v12;
  v27 = *(_QWORD *)(v12 + 16);
  v14 = 0;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
  {
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
    v13 = v26;
  }
  if ( _mm_cvtsi128_si32(v13) && wil::details::g_enabledStateManager && !wil::details::g_processShutdownInProgress )
  {
    if ( !wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v24[0] = a2;
      v24[1] = 0;
      v25 = a1;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140015130, v24, v15);
      wil::details::EnabledStateManager::EnsureTimerUnderLock((struct _TP_TIMER **)&wil::details::g_enabledStateManager);
      ReleaseSRWLockExclusive(&SRWLock);
    }
    v13 = v26;
  }
  v16 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v13, 4));
  if ( (_DWORD)v16 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v13, 8)), v16, 0);
    }
  }
  v18 = v27;
  if ( !(_DWORD)v27 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_140015128 )
    {
      qword_140015128 = 0;
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_140015128, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    v21 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v21 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v21(a2, v20, 0, 0);
    }
  }
  v22 = v18 == 0;
  if ( !v18 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v16) = a8;
      g_wil_details_realtimeFeatureUsageHook(a2, a5, v16);
    }
    v22 = 1;
  }
  LOBYTE(v14) = v22;
  return v14;
}

```

## disassembly

```asm
0x140004318  mov     [rsp+arg_10], rbx
0x14000431d  push    rbp
0x14000431e  push    rsi
0x14000431f  push    rdi
0x140004320  push    r14
0x140004322  push    r15
0x140004324  sub     rsp, 80h
0x14000432b  mov     r15d, r9d
0x14000432e  mov     r14d, r8d
0x140004331  mov     ebp, edx
0x140004333  mov     rdi, rcx
0x140004336  mov     esi, [rsp+0A8h+arg_20]
0x14000433d  mov     r8d, esi
0x140004340  mov     rdx, rcx
0x140004343  lea     rcx, [rsp+0A8h+var_40]
0x140004348  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000434d  movups  xmm1, xmmword ptr [rax]
0x140004350  movups  [rsp+0A8h+var_68], xmm1
0x140004355  movsd   xmm0, qword ptr [rax+10h]
0x14000435a  movsd   [rsp+0A8h+var_48], xmm0
0x140004360  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x140004367  xor     ebx, ebx
0x140004369  test    rax, rax
0x14000436c  jz      short loc_14000438E
0x14000436e  test    esi, esi
0x140004370  jz      short loc_14000437A
0x140004372  lea     ecx, [rsi-64h]
0x140004375  cmp     ecx, 31h ; '1'
0x140004378  ja      short loc_14000438E
0x14000437a  mov     r8d, 1
0x140004380  mov     edx, esi
0x140004382  mov     ecx, ebp
0x140004384  call    _guard_dispatch_icall
0x140004389  movups  xmm1, [rsp+0A8h+var_68]
0x14000438e  movd    eax, xmm1
0x140004392  test    eax, eax
0x140004394  jz      short loc_140004406
0x140004396  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000439c  jz      short loc_140004406
0x14000439e  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x1400043a4  jnz     short loc_140004406
0x1400043a6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400043ad  test    rax, rax
0x1400043b0  jz      short loc_1400043BB
0x1400043b2  call    _guard_dispatch_icall
0x1400043b7  test    al, al
0x1400043b9  jnz     short loc_140004401
0x1400043bb  lea     rcx, SRWLock; SRWLock
0x1400043c2  call    cs:__imp_AcquireSRWLockExclusive
0x1400043c8  mov     [rsp+0A8h+var_78], ebp
0x1400043cc  xor     eax, eax
0x1400043ce  mov     [rsp+0A8h+var_74], eax
0x1400043d2  mov     [rsp+0A8h+var_70], rdi
0x1400043d7  lea     rdx, [rsp+0A8h+var_78]; void *
0x1400043dc  lea     rcx, qword_140015130; this
0x1400043e3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400043e8  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1400043ef  call    ?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::EnsureTimerUnderLock(void)
0x1400043f4  lea     rcx, SRWLock; SRWLock
0x1400043fb  call    cs:__imp_ReleaseSRWLockExclusive
0x140004401  movups  xmm1, [rsp+0A8h+var_68]
0x140004406  movdqa  xmm0, xmm1
0x14000440a  psrldq  xmm0, 4
0x14000440f  movd    r8d, xmm0
0x140004414  test    r8d, r8d
0x140004417  jz      short loc_140004444
0x140004419  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140004420  test    rax, rax
0x140004423  jnz     short loc_140004431
0x140004425  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000442c  test    rax, rax
0x14000442f  jz      short loc_140004444
0x140004431  psrldq  xmm1, 8
0x140004436  xor     r9d, r9d
0x140004439  movd    edx, xmm1
0x14000443d  mov     ecx, ebp
0x14000443f  call    _guard_dispatch_icall
0x140004444  mov     edi, dword ptr [rsp+0A8h+var_48]
0x140004448  test    edi, edi
0x14000444a  jnz     short loc_1400044AE
0x14000444c  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140004452  jz      short loc_1400044AE
0x140004454  lea     rcx, SRWLock; SRWLock
0x14000445b  call    cs:__imp_AcquireSRWLockExclusive
0x140004461  cmp     cs:qword_140015128, rbx
0x140004468  jnz     short loc_1400044A0
0x14000446a  mov     cs:qword_140015128, rbx
0x140004471  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140004478  test    rax, rax
0x14000447b  jnz     short loc_140004489
0x14000447d  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140004484  test    rax, rax
0x140004487  jz      short loc_1400044A0
0x140004489  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000448d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x140004494  lea     rcx, qword_140015128
0x14000449b  call    _guard_dispatch_icall
0x1400044a0  lea     rcx, SRWLock; SRWLock
0x1400044a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400044ad  nop
0x1400044ae  test    r14d, r14d
0x1400044b1  jz      short loc_1400044E4
0x1400044b3  mov     edx, esi
0x1400044b5  bts     edx, 1Fh
0x1400044b9  test    r15d, r15d
0x1400044bc  cmovz   edx, esi
0x1400044bf  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400044c6  test    rax, rax
0x1400044c9  jnz     short loc_1400044D7
0x1400044cb  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1400044d2  test    rax, rax
0x1400044d5  jz      short loc_1400044E4
0x1400044d7  xor     r9d, r9d
0x1400044da  xor     r8d, r8d
0x1400044dd  mov     ecx, ebp
0x1400044df  call    _guard_dispatch_icall
0x1400044e4  test    edi, edi
0x1400044e6  jnz     short loc_140004507
0x1400044e8  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1400044ef  test    rax, rax
0x1400044f2  jz      short loc_140004505
0x1400044f4  mov     r8b, [rsp+0A8h+arg_38]
0x1400044fc  mov     edx, esi
0x1400044fe  mov     ecx, ebp
0x140004500  call    _guard_dispatch_icall
0x140004505  test    edi, edi
0x140004507  setz    bl
0x14000450a  mov     eax, ebx
0x14000450c  mov     rbx, [rsp+0A8h+arg_10]
0x140004514  add     rsp, 80h
0x14000451b  pop     r15
0x14000451d  pop     r14
0x14000451f  pop     rdi
0x140004520  pop     rsi
0x140004521  pop     rbp
0x140004522  retn
```
