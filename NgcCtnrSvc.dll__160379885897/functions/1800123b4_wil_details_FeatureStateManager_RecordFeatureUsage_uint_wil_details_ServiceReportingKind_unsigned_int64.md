# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800123b4`
- end: `0x18001251b`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18001bfb0`

## callees

- `0x1800123b4`
- `0x180012524`
- `0x1800125b4`
- `0x180012e40`
- `0x18001b940`
- `0x1800241b8`
- `0x180025d04`
- `0x180025d28`
- `0x180025d70`
- `0x180025d9c`
- `0x1800303d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001246a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001246a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012416`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012497`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012416`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012497`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800124cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800124cf`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rsi
  int v9; // eax
  wil *v10; // rcx
  char v11; // bl
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v13[9]; // [rsp+20h] [rbp-48h] BYREF
  char v14; // [rsp+70h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_17:
    if ( !wil::ProcessShutdownInProgress(v10) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      v13[0] = a1 + 32;
      if ( !*(_BYTE *)(a1 + 65) )
      {
        if ( !*(_QWORD *)(a1 + 48) )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              (PVOID)a1,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            a1 + 48,
            ThreadpoolTimer);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
        }
        wil::details::EnsureCoalescedTimer_SetTimer(a1 + 48, a1 + 65, 300000);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v13);
    }
    return;
  }
  if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24));
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage((wil::details_abi::RawUsageIndex *)(v8 + 8));
      v11 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v11 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v11 )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1800123b4  push    rbx
0x1800123b6  push    rbp
0x1800123b7  push    rsi
0x1800123b8  push    rdi
0x1800123b9  push    r14
0x1800123bb  push    r15
0x1800123bd  sub     rsp, 38h
0x1800123c1  mov     r15, r9
0x1800123c4  mov     ebx, r8d
0x1800123c7  mov     r14d, edx
0x1800123ca  mov     rdi, rcx
0x1800123cd  cmp     byte ptr [rcx], 0
0x1800123d0  jz      loc_18001250D
0x1800123d6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800123db  test    al, al
0x1800123dd  jz      loc_18001250D
0x1800123e3  mov     rsi, [rdi+18h]
0x1800123e7  cmp     ebx, 0FEh
0x1800123ed  jz      loc_18001247F
0x1800123f3  cmp     ebx, 0C8h
0x1800123f9  jb      short loc_180012413
0x1800123fb  cmp     ebx, 100h
0x180012401  jl      loc_18001250D
0x180012407  cmp     ebx, 200h
0x18001240d  jnb     loc_18001250D
0x180012413  mov     rcx, rsi; SRWLock
0x180012416  call    cs:__imp_AcquireSRWLockExclusive
0x18001241d  nop     dword ptr [rax+rax+00h]
0x180012422  cmp     ebx, 7
0x180012425  ja      short loc_180012431
0x180012427  mov     eax, 0CCh
0x18001242c  bt      eax, ebx
0x18001242f  jb      short loc_180012451
0x180012431  lea     eax, [rbx-100h]
0x180012437  cmp     eax, 7Fh
0x18001243a  jbe     short loc_180012451
0x18001243c  mov     r9d, r15d
0x18001243f  lea     rcx, [rsi+48h]
0x180012443  mov     r8d, r14d
0x180012446  mov     edx, ebx
0x180012448  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001244d  mov     bl, al
0x18001244f  jmp     short loc_180012462
0x180012451  mov     r8d, r14d
0x180012454  mov     edx, ebx
0x180012456  lea     rcx, [rsi+8]; this
0x18001245a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001245f  mov     bl, [rsi+40h]
0x180012462  test    rsi, rsi
0x180012465  jz      short loc_180012476
0x180012467  mov     rcx, rsi; SRWLock
0x18001246a  call    cs:__imp_ReleaseSRWLockExclusive
0x180012471  nop     dword ptr [rax+rax+00h]
0x180012476  test    bl, bl
0x180012478  jnz     short loc_180012487
0x18001247a  jmp     loc_18001250D
0x18001247f  mov     rcx, rsi; SRWLock
0x180012482  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180012487  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001248c  test    al, al
0x18001248e  jnz     short loc_18001250D
0x180012490  lea     rbx, [rdi+20h]
0x180012494  mov     rcx, rbx; SRWLock
0x180012497  call    cs:__imp_AcquireSRWLockExclusive
0x18001249e  nop     dword ptr [rax+rax+00h]
0x1800124a3  mov     [rsp+68h+var_48], rbx
0x1800124a8  cmp     byte ptr [rdi+41h], 0
0x1800124ac  jnz     short loc_180012502
0x1800124ae  lea     rbx, [rdi+30h]
0x1800124b2  cmp     qword ptr [rbx], 0
0x1800124b6  jnz     short loc_1800124F0
0x1800124b8  lea     rcx, [rsp+68h+arg_0]; this
0x1800124bd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800124c2  xor     r8d, r8d; pcbe
0x1800124c5  mov     rdx, rdi; pv
0x1800124c8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800124cf  call    cs:__imp_CreateThreadpoolTimer
0x1800124d6  nop     dword ptr [rax+rax+00h]
0x1800124db  mov     rdx, rax
0x1800124de  mov     rcx, rbx
0x1800124e1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800124e6  lea     rcx, [rsp+68h+arg_0]; this
0x1800124eb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800124f0  mov     r8d, 493E0h
0x1800124f6  lea     rdx, [rdi+41h]
0x1800124fa  mov     rcx, rbx
0x1800124fd  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180012502  lea     rcx, [rsp+68h+var_48]
0x180012507  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18001250c  nop
0x18001250d  add     rsp, 38h
0x180012511  pop     r15
0x180012513  pop     r14
0x180012515  pop     rdi
0x180012516  pop     rsi
0x180012517  pop     rbp
0x180012518  pop     rbx
0x180012519  retn
```
