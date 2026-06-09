# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000dbc8`
- end: `0x14000dd27`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `351`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x140082ef0`

## callees

- `0x14000c604`
- `0x14000c670`
- `0x14000dbc8`
- `0x1400260c4`
- `0x140026514`
- `0x140027f78`
- `0x1400291b4`
- `0x140029b38`
- `0x140085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000dc7f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000dce3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000dc7f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000dce3`

## string_xrefs

- `0x14000dca3`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rdi
  struct _TP_TIMER *v4; // rdi
  __int64 v5; // rcx
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 (*NtDllProcedureAddress)(void); // rax
  __int64 v10; // rcx
  struct _TP_TIMER *v11; // rcx
  struct _TP_TIMER *v12; // rcx
  void *v13; // rcx
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
  v5 = *((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v5 )
    MincryptFree();
  v6 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v6 )
    wil::details::UnsubscribeProcessWideUsageFlush(v6, a2);
  v7 = *((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v7 )
    MincryptFree();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v8 = *((_QWORD *)this + 18);
  if ( v8 )
  {
    NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))NtDllProcedureAddress)(v8);
    }
  }
  v10 = *((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v10 )
    MincryptFree();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v11 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v11);
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v12 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v12);
  v13 = (void *)*((_QWORD *)this + 2);
  if ( v13 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v13);
}

```

## disassembly

```asm
0x14000dbc8  mov     [rsp+arg_8], rbx
0x14000dbcd  push    rdi
0x14000dbce  sub     rsp, 20h
0x14000dbd2  mov     rbx, rcx
0x14000dbd5  mov     byte ptr [rcx], 0
0x14000dbd8  mov     rdi, [rcx+30h]
0x14000dbdc  test    rdi, rdi
0x14000dbdf  jz      short loc_14000DBFD
0x14000dbe1  lea     rcx, [rsp+28h+arg_0]; this
0x14000dbe6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000dbeb  mov     rcx, rdi; pti
0x14000dbee  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000dbf3  lea     rcx, [rsp+28h+arg_0]; this
0x14000dbf8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000dbfd  mov     qword ptr [rbx+30h], 0
0x14000dc05  mov     rdi, [rbx+38h]
0x14000dc09  test    rdi, rdi
0x14000dc0c  jz      short loc_14000DC2A
0x14000dc0e  lea     rcx, [rsp+28h+arg_0]; this
0x14000dc13  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000dc18  mov     rcx, rdi; pti
0x14000dc1b  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000dc20  lea     rcx, [rsp+28h+arg_0]; this
0x14000dc25  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000dc2a  mov     qword ptr [rbx+38h], 0
0x14000dc32  mov     rcx, [rbx+100h]
0x14000dc39  mov     qword ptr [rbx+100h], 0
0x14000dc44  test    rcx, rcx
0x14000dc47  jz      short loc_14000DC4E
0x14000dc49  call    MincryptFree
0x14000dc4e  mov     rcx, [rbx+0E0h]; this
0x14000dc55  test    rcx, rcx
0x14000dc58  jz      short loc_14000DC5F
0x14000dc5a  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000dc5f  lea     rdi, [rbx+98h]
0x14000dc66  mov     rcx, [rdi+40h]
0x14000dc6a  mov     qword ptr [rdi+40h], 0
0x14000dc72  test    rcx, rcx
0x14000dc75  jz      short loc_14000DC7C
0x14000dc77  call    MincryptFree
0x14000dc7c  mov     rcx, rdi; lpCriticalSection
0x14000dc7f  call    cs:__imp_DeleteCriticalSection
0x14000dc86  nop     dword ptr [rax+rax+00h]
0x14000dc8b  mov     rdi, [rbx+90h]
0x14000dc92  test    rdi, rdi
0x14000dc95  jz      short loc_14000DCC3
0x14000dc97  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000dc9e  test    rax, rax
0x14000dca1  jnz     short loc_14000DCBB
0x14000dca3  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000dcaa  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000dcaf  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000dcb6  test    rax, rax
0x14000dcb9  jz      short loc_14000DCC3
0x14000dcbb  mov     rcx, rdi
0x14000dcbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dcc3  mov     rcx, [rbx+88h]
0x14000dcca  mov     qword ptr [rbx+88h], 0
0x14000dcd5  test    rcx, rcx
0x14000dcd8  jz      short loc_14000DCDF
0x14000dcda  call    MincryptFree
0x14000dcdf  lea     rcx, [rbx+48h]; lpCriticalSection
0x14000dce3  call    cs:__imp_DeleteCriticalSection
0x14000dcea  nop     dword ptr [rax+rax+00h]
0x14000dcef  mov     rcx, [rbx+38h]; pti
0x14000dcf3  test    rcx, rcx
0x14000dcf6  jz      short loc_14000DCFD
0x14000dcf8  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000dcfd  mov     rcx, [rbx+30h]; pti
0x14000dd01  test    rcx, rcx
0x14000dd04  jz      short loc_14000DD0C
0x14000dd06  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000dd0b  nop
0x14000dd0c  mov     rcx, [rbx+10h]; lpMem
0x14000dd10  test    rcx, rcx
0x14000dd13  jz      short loc_14000DD1B
0x14000dd15  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14000dd1a  nop
0x14000dd1b  mov     rbx, [rsp+28h+arg_8]
0x14000dd20  add     rsp, 20h
0x14000dd24  pop     rdi
0x14000dd25  retn
```
