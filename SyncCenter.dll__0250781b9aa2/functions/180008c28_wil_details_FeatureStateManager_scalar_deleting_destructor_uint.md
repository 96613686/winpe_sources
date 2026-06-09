# wil::details::FeatureStateManager::`scalar deleting destructor'(uint)

- ea: `0x180008c28`
- end: `0x180008d54`
- name: `??_GFeatureStateManager@details@wil@@QEAAPEAXI@Z`
- size: `300`
- prototype: `wil::details::FeatureStateManager *__fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180052f40`

## callees

- `0x180008c28`
- `0x18000ddd8`
- `0x18000df44`
- `0x18000e36c`
- `0x1800269f8`
- `0x180027598`
- `0x180027b28`
- `0x180028308`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008cdf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d16`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008cdf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d16`

## pseudocode

```c
wil::details::FeatureStateManager *__fastcall wil::details::FeatureStateManager::`scalar deleting destructor'(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rdi
  struct _TP_TIMER *v4; // rdi
  wil::details *v5; // rcx
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rcx
  wil::details *v7; // rcx
  void *v8; // rdx
  wil::details *v9; // rcx
  struct _TP_TIMER *v10; // rcx
  struct _TP_TIMER *v11; // rcx
  void *v12; // rcx
  char v14; // [rsp+30h] [rbp+8h] BYREF

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
  }
  *((_QWORD *)this + 7) = 0;
  v5 = (wil::details *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v5 )
    wil::details::FreeProcessHeap(v5, a2);
  v6 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v6 )
    wil::details::UnsubscribeProcessWideUsageFlush(v6, a2);
  v7 = (wil::details *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v7 )
    wil::details::FreeProcessHeap(v7, a2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  if ( *((_QWORD *)this + 18) )
    wil_details_RtlUnregisterFeatureConfigurationChangeNotification();
  v9 = (wil::details *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v9 )
    wil::details::FreeProcessHeap(v9, v8);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v10 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v10 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v10);
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v11 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v11);
  v12 = (void *)*((_QWORD *)this + 2);
  if ( v12 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v12);
  return this;
}

```

## disassembly

```asm
0x180008c28  mov     [rsp+arg_8], rbx
0x180008c2d  push    rdi
0x180008c2e  sub     rsp, 20h
0x180008c32  mov     byte ptr [rcx], 0
0x180008c35  mov     rbx, rcx
0x180008c38  mov     rdi, [rcx+30h]
0x180008c3c  test    rdi, rdi
0x180008c3f  jz      short loc_180008C5D
0x180008c41  lea     rcx, [rsp+28h+arg_0]; this
0x180008c46  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008c4b  mov     rcx, rdi; pti
0x180008c4e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180008c53  lea     rcx, [rsp+28h+arg_0]; this
0x180008c58  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008c5d  mov     qword ptr [rbx+30h], 0
0x180008c65  mov     rdi, [rbx+38h]
0x180008c69  test    rdi, rdi
0x180008c6c  jz      short loc_180008C8A
0x180008c6e  lea     rcx, [rsp+28h+arg_0]; this
0x180008c73  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008c78  mov     rcx, rdi; pti
0x180008c7b  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180008c80  lea     rcx, [rsp+28h+arg_0]; this
0x180008c85  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008c8a  mov     qword ptr [rbx+38h], 0
0x180008c92  mov     rcx, [rbx+100h]; this
0x180008c99  mov     qword ptr [rbx+100h], 0
0x180008ca4  test    rcx, rcx
0x180008ca7  jz      short loc_180008CAE
0x180008ca9  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180008cae  mov     rcx, [rbx+0E0h]; this
0x180008cb5  test    rcx, rcx
0x180008cb8  jz      short loc_180008CBF
0x180008cba  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180008cbf  lea     rdi, [rbx+98h]
0x180008cc6  mov     rcx, [rdi+40h]; this
0x180008cca  mov     qword ptr [rdi+40h], 0
0x180008cd2  test    rcx, rcx
0x180008cd5  jz      short loc_180008CDC
0x180008cd7  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180008cdc  mov     rcx, rdi; lpCriticalSection
0x180008cdf  call    cs:__imp_DeleteCriticalSection
0x180008ce5  mov     rcx, [rbx+90h]
0x180008cec  test    rcx, rcx
0x180008cef  jz      short loc_180008CF6
0x180008cf1  call    wil_details_RtlUnregisterFeatureConfigurationChangeNotification
0x180008cf6  mov     rcx, [rbx+88h]; this
0x180008cfd  mov     qword ptr [rbx+88h], 0
0x180008d08  test    rcx, rcx
0x180008d0b  jz      short loc_180008D12
0x180008d0d  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180008d12  lea     rcx, [rbx+48h]; lpCriticalSection
0x180008d16  call    cs:__imp_DeleteCriticalSection
0x180008d1c  mov     rcx, [rbx+38h]; pti
0x180008d20  test    rcx, rcx
0x180008d23  jz      short loc_180008D2A
0x180008d25  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180008d2a  mov     rcx, [rbx+30h]; pti
0x180008d2e  test    rcx, rcx
0x180008d31  jz      short loc_180008D38
0x180008d33  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180008d38  mov     rcx, [rbx+10h]; lpMem
0x180008d3c  test    rcx, rcx
0x180008d3f  jz      short loc_180008D46
0x180008d41  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180008d46  mov     rax, rbx
0x180008d49  mov     rbx, [rsp+28h+arg_8]
0x180008d4e  add     rsp, 20h
0x180008d52  pop     rdi
0x180008d53  retn
```
