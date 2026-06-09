# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001ef18`
- end: `0x18001efe9`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `209`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180025240`

## callees

- `0x180015a10`
- `0x180016790`
- `0x1800176d4`
- `0x180017708`
- `0x1800178c4`
- `0x18001ef18`
- `0x18001f344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ef47`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ef47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001efd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001efd9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001efa4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001efa4`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  char v10; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Source[0] = a2;
        Source[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), Source, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    if ( pv != (char *)-8LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 1);
  }
}

```

## disassembly

```asm
0x18001ef18  push    rbx
0x18001ef1a  push    rbp
0x18001ef1b  push    rsi
0x18001ef1c  push    rdi
0x18001ef1d  sub     rsp, 38h
0x18001ef21  mov     rsi, r8
0x18001ef24  mov     ebp, edx
0x18001ef26  mov     rbx, rcx
0x18001ef29  mov     eax, [rcx]
0x18001ef2b  test    eax, eax
0x18001ef2d  jz      loc_18001EFE0
0x18001ef33  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001ef38  test    al, al
0x18001ef3a  jnz     loc_18001EFE0
0x18001ef40  lea     rdi, [rbx+8]
0x18001ef44  mov     rcx, rdi; SRWLock
0x18001ef47  call    cs:__imp_AcquireSRWLockExclusive
0x18001ef4d  mov     eax, [rbx]
0x18001ef4f  test    eax, eax
0x18001ef51  jz      short loc_18001EFD1
0x18001ef53  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001ef58  test    al, al
0x18001ef5a  jnz     short loc_18001EFD1
0x18001ef5c  mov     [rsp+58h+Source], ebp
0x18001ef60  xor     eax, eax
0x18001ef62  mov     [rsp+58h+var_34], eax
0x18001ef66  mov     [rsp+58h+var_30], rsi
0x18001ef6b  lea     rcx, [rbx+20h]; this
0x18001ef6f  lea     r8d, [rax+10h]; SourceSize
0x18001ef73  lea     rdx, [rsp+58h+Source]; Source
0x18001ef78  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001ef7d  cmp     byte ptr [rbx+18h], 0
0x18001ef81  jnz     short loc_18001EFD1
0x18001ef83  lea     rsi, [rbx+10h]
0x18001ef87  cmp     qword ptr [rsi], 0
0x18001ef8b  jnz     short loc_18001EFBF
0x18001ef8d  lea     rcx, [rsp+58h+arg_0]; this
0x18001ef92  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ef97  xor     r8d, r8d; pcbe
0x18001ef9a  mov     rdx, rbx; pv
0x18001ef9d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001efa4  call    cs:__imp_CreateThreadpoolTimer
0x18001efaa  mov     rdx, rax
0x18001efad  mov     rcx, rsi
0x18001efb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001efb5  lea     rcx, [rsp+58h+arg_0]; this
0x18001efba  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001efbf  mov     r8d, 493E0h
0x18001efc5  lea     rdx, [rbx+18h]
0x18001efc9  mov     rcx, rsi
0x18001efcc  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001efd1  test    rdi, rdi
0x18001efd4  jz      short loc_18001EFE0
0x18001efd6  mov     rcx, rdi; SRWLock
0x18001efd9  call    cs:__imp_ReleaseSRWLockExclusive
0x18001efdf  nop
0x18001efe0  add     rsp, 38h
0x18001efe4  pop     rdi
0x18001efe5  pop     rsi
0x18001efe6  pop     rbp
0x18001efe7  pop     rbx
0x18001efe8  retn
```
