# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001d3ec`
- end: `0x18001d564`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180038020`

## callees

- `0x18001d3ec`
- `0x18001d56c`
- `0x18001d670`
- `0x18001dbec`
- `0x18002be48`
- `0x18002be6c`
- `0x18002bed0`
- `0x18002bffc`
- `0x18002effc`
- `0x180037200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d4a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d545`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d4a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d545`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d451`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d4d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d451`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d4d7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d50a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d50a`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rdi
  int v9; // eax
  wil *v10; // rcx
  char v11; // bl
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v13[56]; // [rsp+20h] [rbp-38h] BYREF

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
      if ( !*(_BYTE *)(a1 + 65) )
      {
        if ( !*(_QWORD *)(a1 + 48) )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)v13);
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              (PVOID)a1,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            a1 + 48,
            ThreadpoolTimer);
          wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
        }
        wil::details::EnsureCoalescedTimer_SetTimer(a1 + 48, a1 + 65, 300000);
      }
      if ( a1 != -32 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
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
0x18001d3ec  mov     [rsp+arg_18], rbx
0x18001d3f1  push    rbp
0x18001d3f2  push    rsi
0x18001d3f3  push    rdi
0x18001d3f4  push    r14
0x18001d3f6  push    r15
0x18001d3f8  sub     rsp, 30h
0x18001d3fc  mov     r15, r9
0x18001d3ff  mov     ebx, r8d
0x18001d402  mov     r14d, edx
0x18001d405  mov     rsi, rcx
0x18001d408  cmp     byte ptr [rcx], 0
0x18001d40b  jz      loc_18001D552
0x18001d411  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001d416  test    al, al
0x18001d418  jz      loc_18001D552
0x18001d41e  mov     rdi, [rsi+18h]
0x18001d422  cmp     ebx, 0FEh
0x18001d428  jz      loc_18001D4BB
0x18001d42e  cmp     ebx, 0C8h
0x18001d434  jb      short loc_18001D44E
0x18001d436  cmp     ebx, 100h
0x18001d43c  jl      loc_18001D552
0x18001d442  cmp     ebx, 200h
0x18001d448  jnb     loc_18001D552
0x18001d44e  mov     rcx, rdi; SRWLock
0x18001d451  call    cs:__imp_AcquireSRWLockExclusive
0x18001d458  nop     dword ptr [rax+rax+00h]
0x18001d45d  cmp     ebx, 7
0x18001d460  ja      short loc_18001D46C
0x18001d462  mov     eax, 0CCh
0x18001d467  bt      eax, ebx
0x18001d46a  jb      short loc_18001D48C
0x18001d46c  lea     eax, [rbx-100h]
0x18001d472  cmp     eax, 7Fh
0x18001d475  jbe     short loc_18001D48C
0x18001d477  mov     r9d, r15d
0x18001d47a  lea     rcx, [rdi+48h]
0x18001d47e  mov     r8d, r14d
0x18001d481  mov     edx, ebx
0x18001d483  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001d488  mov     bl, al
0x18001d48a  jmp     short loc_18001D49D
0x18001d48c  mov     r8d, r14d
0x18001d48f  mov     edx, ebx
0x18001d491  lea     rcx, [rdi+8]; this
0x18001d495  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001d49a  mov     bl, [rdi+40h]
0x18001d49d  test    rdi, rdi
0x18001d4a0  jz      short loc_18001D4B1
0x18001d4a2  mov     rcx, rdi; SRWLock
0x18001d4a5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d4ac  nop     dword ptr [rax+rax+00h]
0x18001d4b1  test    bl, bl
0x18001d4b3  jz      loc_18001D552
0x18001d4b9  jmp     short loc_18001D4C3
0x18001d4bb  mov     rcx, rdi; SRWLock
0x18001d4be  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001d4c3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001d4c8  test    al, al
0x18001d4ca  jnz     loc_18001D552
0x18001d4d0  lea     rbx, [rsi+20h]
0x18001d4d4  mov     rcx, rbx; SRWLock
0x18001d4d7  call    cs:__imp_AcquireSRWLockExclusive
0x18001d4de  nop     dword ptr [rax+rax+00h]
0x18001d4e3  cmp     byte ptr [rsi+41h], 0
0x18001d4e7  jnz     short loc_18001D53D
0x18001d4e9  lea     rdi, [rsi+30h]
0x18001d4ed  cmp     qword ptr [rdi], 0
0x18001d4f1  jnz     short loc_18001D52B
0x18001d4f3  lea     rcx, [rsp+58h+var_38]; this
0x18001d4f8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001d4fd  xor     r8d, r8d; pcbe
0x18001d500  mov     rdx, rsi; pv
0x18001d503  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d50a  call    cs:__imp_CreateThreadpoolTimer
0x18001d511  nop     dword ptr [rax+rax+00h]
0x18001d516  mov     rdx, rax
0x18001d519  mov     rcx, rdi
0x18001d51c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001d521  lea     rcx, [rsp+58h+var_38]; this
0x18001d526  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001d52b  mov     r8d, 493E0h
0x18001d531  lea     rdx, [rsi+41h]
0x18001d535  mov     rcx, rdi
0x18001d538  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001d53d  test    rbx, rbx
0x18001d540  jz      short loc_18001D552
0x18001d542  mov     rcx, rbx; SRWLock
0x18001d545  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d54c  nop     dword ptr [rax+rax+00h]
0x18001d551  nop
0x18001d552  mov     rbx, [rsp+58h+arg_18]
0x18001d557  add     rsp, 30h
0x18001d55b  pop     r15
0x18001d55d  pop     r14
0x18001d55f  pop     rdi
0x18001d560  pop     rsi
0x18001d561  pop     rbp
0x18001d562  retn
```
