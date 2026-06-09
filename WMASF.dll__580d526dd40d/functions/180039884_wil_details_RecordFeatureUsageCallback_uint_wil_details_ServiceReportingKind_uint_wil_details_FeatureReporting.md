# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x180039884`
- end: `0x1800399d4`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18003a450`

## callees

- `0x180032c1c`
- `0x18003368c`
- `0x180039744`
- `0x180039884`
- `0x18003bc6c`
- `0x18003c060`
- `0x180040010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800398e5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003996d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800398e5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003996d`

## pseudocode

```c
void __fastcall wil::details::RecordFeatureUsageCallback(wil *a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned int v6; // edi
  wil *v7; // rcx
  unsigned __int64 v8; // r8
  unsigned int v9; // r8d
  void (__fastcall *v10)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  char *v11; // [rsp+20h] [rbp-38h] BYREF
  _DWORD Source[2]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v13; // [rsp+30h] [rbp-28h]

  v6 = (unsigned int)a1;
  if ( g_wil_details_RecordSRUMFeatureUsage )
  {
    if ( !(_DWORD)a2 || (a1 = (wil *)(unsigned int)(a2 - 100), (unsigned int)a1 <= 0x31) )
      g_wil_details_RecordSRUMFeatureUsage(v6, a2, 1);
  }
  if ( *a5 && wil::details::g_enabledStateManager && !wil::ProcessShutdownInProgress(a1) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v11 = (char *)&SRWLock;
    if ( wil::details::g_enabledStateManager && !wil::ProcessShutdownInProgress(v7) )
    {
      Source[0] = v6;
      Source[1] = 0;
      v13 = a4;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18004A558, Source, v8);
      wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
        (struct _TP_TIMER **)&qword_18004A548,
        byte_18004A550,
        &wil::details::g_enabledStateManager);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
  v9 = a5[1];
  if ( v9 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)v6, a5[2], v9, a4, v11);
  if ( !a5[4] && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v11 = (char *)&SRWLock;
    if ( !qword_18004A5A0 )
    {
      v10 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_18004A5A0 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v10 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v10(&qword_18004A5A0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180039884  mov     [rsp+arg_10], rbx
0x180039889  push    rsi
0x18003988a  push    rdi
0x18003988b  push    r14
0x18003988d  sub     rsp, 40h
0x180039891  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180039898  mov     rsi, r9
0x18003989b  mov     rbx, [rsp+58h+arg_20]
0x1800398a3  mov     edi, ecx
0x1800398a5  test    rax, rax
0x1800398a8  jz      short loc_1800398C3
0x1800398aa  test    edx, edx
0x1800398ac  jz      short loc_1800398B6
0x1800398ae  lea     ecx, [rdx-64h]
0x1800398b1  cmp     ecx, 31h ; '1'
0x1800398b4  ja      short loc_1800398C3
0x1800398b6  mov     r8d, 1
0x1800398bc  mov     ecx, edi
0x1800398be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398c3  cmp     dword ptr [rbx], 0
0x1800398c6  lea     r14, SRWLock
0x1800398cd  jz      short loc_180039947
0x1800398cf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800398d5  test    eax, eax
0x1800398d7  jz      short loc_180039947
0x1800398d9  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800398de  test    al, al
0x1800398e0  jnz     short loc_180039947
0x1800398e2  mov     rcx, r14; SRWLock
0x1800398e5  call    cs:__imp_AcquireSRWLockExclusive
0x1800398eb  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800398f1  mov     [rsp+58h+var_38], r14; char *
0x1800398f6  test    eax, eax
0x1800398f8  jz      short loc_18003993D
0x1800398fa  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800398ff  test    al, al
0x180039901  jnz     short loc_18003993D
0x180039903  xor     eax, eax
0x180039905  mov     [rsp+58h+Source], edi
0x180039909  lea     rdx, [rsp+58h+Source]; Source
0x18003990e  mov     [rsp+58h+var_2C], eax
0x180039912  lea     rcx, qword_18004A558; this
0x180039919  mov     [rsp+58h+var_28], rsi
0x18003991e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180039923  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003992a  lea     rdx, byte_18004A550
0x180039931  lea     rcx, qword_18004A548
0x180039938  call    ??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)
0x18003993d  lea     rcx, [rsp+58h+var_38]
0x180039942  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180039947  mov     r8d, [rbx+4]; unsigned int
0x18003994b  test    r8d, r8d
0x18003994e  jz      short loc_18003995A
0x180039950  mov     edx, [rbx+8]; unsigned int
0x180039953  mov     ecx, edi; this
0x180039955  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18003995a  cmp     dword ptr [rbx+10h], 0
0x18003995e  jnz     short loc_1800399C6
0x180039960  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180039966  test    eax, eax
0x180039968  jz      short loc_1800399C6
0x18003996a  mov     rcx, r14; SRWLock
0x18003996d  call    cs:__imp_AcquireSRWLockExclusive
0x180039973  cmp     cs:qword_18004A5A0, 0
0x18003997b  mov     [rsp+58h+var_38], r14
0x180039980  jnz     short loc_1800399BC
0x180039982  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180039989  mov     cs:qword_18004A5A0, 0
0x180039994  test    rax, rax
0x180039997  jnz     short loc_1800399A5
0x180039999  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800399a0  test    rax, rax
0x1800399a3  jz      short loc_1800399BC
0x1800399a5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800399a9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1800399b0  lea     rcx, qword_18004A5A0
0x1800399b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399bc  lea     rcx, [rsp+58h+var_38]
0x1800399c1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800399c6  mov     rbx, [rsp+58h+arg_10]
0x1800399cb  add     rsp, 40h
0x1800399cf  pop     r14
0x1800399d1  pop     rdi
0x1800399d2  pop     rsi
0x1800399d3  retn
```
