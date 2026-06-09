# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180012400`
- end: `0x18001255a`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180019550`

## callees

- `0x180012400`
- `0x180012560`
- `0x180012580`
- `0x1800129ac`
- `0x180013064`
- `0x1800131d8`
- `0x1800198fc`
- `0x18001991c`
- `0x180025afc`
- `0x1800400b0`
- `0x1800400e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012466`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800124dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012466`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800124dd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001250f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001250f`

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
  char v10; // bl
  wil *v11; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v13[5]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
  }
  else
  {
    if ( a3 >= 0xC8 && ((int)a3 < 256 || a3 >= 0x200) )
      return;
    if ( (AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24)), v14 = v8, a3 <= 7) && (v9 = 204, _bittest(&v9, a3))
      || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(v8 + 8, a3, a2);
      v10 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
    if ( !v10 )
      return;
  }
  if ( !wil::ProcessShutdownInProgress(v11) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
    v13[0] = a1 + 32;
    if ( !*(_BYTE *)(a1 + 65) )
    {
      if ( !*(_QWORD *)(a1 + 48) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                            (PVOID)a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(a1 + 48, a1 + 65, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v13);
  }
}

```

## disassembly

```asm
0x180012400  mov     [rsp+arg_8], rbx
0x180012405  mov     [rsp+arg_10], rbp
0x18001240a  push    rsi
0x18001240b  push    rdi
0x18001240c  push    r14
0x18001240e  sub     rsp, 30h
0x180012412  mov     r14, r9
0x180012415  mov     ebx, r8d
0x180012418  mov     ebp, edx
0x18001241a  mov     rdi, rcx
0x18001241d  cmp     byte ptr [rcx], 0
0x180012420  jz      loc_180012547
0x180012426  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001242b  test    al, al
0x18001242d  jz      loc_180012547
0x180012433  mov     rsi, [rdi+18h]
0x180012437  cmp     ebx, 0FEh
0x18001243d  jz      loc_1800124C5
0x180012443  cmp     ebx, 0C8h
0x180012449  jb      short loc_180012463
0x18001244b  cmp     ebx, 100h
0x180012451  jl      loc_180012547
0x180012457  cmp     ebx, 200h
0x18001245d  jnb     loc_180012547
0x180012463  mov     rcx, rsi; SRWLock
0x180012466  call    cs:__imp_AcquireSRWLockExclusive
0x18001246c  mov     [rsp+48h+arg_0], rsi
0x180012471  cmp     ebx, 7
0x180012474  ja      short loc_180012480
0x180012476  mov     eax, 0CCh
0x18001247b  bt      eax, ebx
0x18001247e  jb      short loc_1800124A0
0x180012480  lea     eax, [rbx-100h]
0x180012486  cmp     eax, 7Fh
0x180012489  jbe     short loc_1800124A0
0x18001248b  mov     r9d, r14d
0x18001248e  lea     rcx, [rsi+48h]
0x180012492  mov     r8d, ebp
0x180012495  mov     edx, ebx
0x180012497  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001249c  mov     bl, al
0x18001249e  jmp     short loc_1800124B1
0x1800124a0  mov     r8d, ebp
0x1800124a3  mov     edx, ebx
0x1800124a5  lea     rcx, [rsi+8]
0x1800124a9  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800124ae  mov     bl, [rsi+40h]
0x1800124b1  lea     rcx, [rsp+48h+arg_0]
0x1800124b6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800124bb  test    bl, bl
0x1800124bd  jz      loc_180012547
0x1800124c3  jmp     short loc_1800124CD
0x1800124c5  mov     rcx, rsi; SRWLock
0x1800124c8  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800124cd  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800124d2  test    al, al
0x1800124d4  jnz     short loc_180012547
0x1800124d6  lea     rbx, [rdi+20h]
0x1800124da  mov     rcx, rbx; SRWLock
0x1800124dd  call    cs:__imp_AcquireSRWLockExclusive
0x1800124e3  mov     [rsp+48h+var_28], rbx
0x1800124e8  cmp     byte ptr [rdi+41h], 0
0x1800124ec  jnz     short loc_18001253C
0x1800124ee  lea     rbx, [rdi+30h]
0x1800124f2  cmp     qword ptr [rbx], 0
0x1800124f6  jnz     short loc_18001252A
0x1800124f8  lea     rcx, [rsp+48h+arg_0]; this
0x1800124fd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180012502  xor     r8d, r8d; pcbe
0x180012505  mov     rdx, rdi; pv
0x180012508  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001250f  call    cs:__imp_CreateThreadpoolTimer
0x180012515  mov     rdx, rax
0x180012518  mov     rcx, rbx
0x18001251b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180012520  lea     rcx, [rsp+48h+arg_0]; this
0x180012525  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001252a  mov     r8d, 493E0h
0x180012530  lea     rdx, [rdi+41h]
0x180012534  mov     rcx, rbx
0x180012537  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001253c  lea     rcx, [rsp+48h+var_28]
0x180012541  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012546  nop
0x180012547  mov     rbx, [rsp+48h+arg_8]
0x18001254c  mov     rbp, [rsp+48h+arg_10]
0x180012551  add     rsp, 30h
0x180012555  pop     r14
0x180012557  pop     rdi
0x180012558  pop     rsi
0x180012559  retn
```
