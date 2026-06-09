# FSActivityManager::~FSActivityManager(void)

- ea: `0x180019948`
- end: `0x180019a49`
- name: `??1FSActivityManager@@MEAA@XZ`
- size: `257`
- prototype: `void __fastcall(FSActivityManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180019a60`

## callees

- `0x180005ed4`
- `0x180008338`
- `0x1800095c8`
- `0x18000a460`
- `0x18000a4a8`
- `0x1800198f4`
- `0x180019948`
- `0x18001adc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800199d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800199d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001996b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001996b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019a2c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019a2c`

## pseudocode

```c
void __fastcall FSActivityManager::~FSActivityManager(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  unsigned int v3; // esi

  v2 = this + 1;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&FSActivityManager::`vftable';
  EnterCriticalSection(this + 1);
  v3 = 0;
  if ( !LOBYTE(this[2].DebugInfo) )
    FSActivityManager::InternalShutdown((FSActivityManager *)this, 0, 0);
  do
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &this[3].LockSemaphore + 9 * (int)v3++,
      0);
  while ( v3 < 3 );
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, &WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids, this);
  LeaveCriticalSection(v2);
  CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>(&this[10]);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(&this[9].LockCount);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(&this[8].LockSemaphore);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(&this[8]);
  `vector destructor iterator'(
    &this[2].LockSemaphore,
    0x48u,
    3u,
    (void (*)(void *))FSActMgrAsyncWorkitemState::~FSActMgrAsyncWorkitemState);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&this[2].OwningThread);
  DeleteCriticalSection(v2);
  _InterlockedDecrement(&g_lRefModule);
}

```

## disassembly

```asm
0x180019948  mov     [rsp+arg_0], rbx
0x18001994d  mov     [rsp+arg_8], rsi
0x180019952  push    rdi
0x180019953  sub     rsp, 20h
0x180019957  lea     rax, ??_7FSActivityManager@@6B@; const FSActivityManager::`vftable'
0x18001995e  mov     rdi, rcx
0x180019961  lea     rbx, [rcx+28h]
0x180019965  mov     [rcx], rax
0x180019968  mov     rcx, rbx; lpCriticalSection
0x18001996b  call    cs:__imp_EnterCriticalSection
0x180019971  xor     esi, esi
0x180019973  cmp     [rdi+50h], sil
0x180019977  jnz     short loc_180019986
0x180019979  xor     r8d, r8d; int
0x18001997c  xor     edx, edx; struct FSActMgrAsyncWorkitemState *
0x18001997e  mov     rcx, rdi; this
0x180019981  call    ?InternalShutdown@FSActivityManager@@IEAAXPEAUFSActMgrAsyncWorkitemState@@H@Z; FSActivityManager::InternalShutdown(FSActMgrAsyncWorkitemState *,int)
0x180019986  movsxd  rax, esi
0x180019989  xor     edx, edx
0x18001998b  add     rax, 2
0x18001998f  lea     rcx, [rax+rax*8]
0x180019993  lea     rcx, [rdi+rcx*8]
0x180019997  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001999c  inc     esi
0x18001999e  cmp     esi, 3
0x1800199a1  jb      short loc_180019986
0x1800199a3  cmp     cs:byte_18010EC4D, 10h
0x1800199aa  jb      short loc_1800199CE
0x1800199ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199b3  lea     r8, WPP_47229f29bd5f33e3e7f2581ae6977b5e_Traceguids
0x1800199ba  mov     edx, 0Dh
0x1800199bf  mov     r9, rdi
0x1800199c2  mov     rcx, [rcx+0D8h]
0x1800199c9  call    WPP_SF_q
0x1800199ce  mov     rcx, rbx; lpCriticalSection
0x1800199d1  call    cs:__imp_LeaveCriticalSection
0x1800199d7  lea     rcx, [rdi+190h]
0x1800199de  call    ??1?$CTUnkArray@UIFSProcessActivity@@@@QEAA@XZ; CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>(void)
0x1800199e3  lea     rcx, [rdi+170h]; void *
0x1800199ea  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800199ef  lea     rcx, [rdi+158h]; void *
0x1800199f6  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800199fb  lea     rcx, [rdi+140h]; void *
0x180019a02  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x180019a07  mov     edx, 48h ; 'H'; unsigned __int64
0x180019a0c  lea     rcx, [rdi+68h]; void *
0x180019a10  lea     r9, ??1FSActMgrAsyncWorkitemState@@QEAA@XZ; void (*)(void *)
0x180019a17  lea     r8d, [rdx-45h]; unsigned __int64
0x180019a1b  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180019a20  lea     rcx, [rdi+60h]
0x180019a24  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180019a29  mov     rcx, rbx; lpCriticalSection
0x180019a2c  call    cs:__imp_DeleteCriticalSection
0x180019a32  lock dec cs:?g_lRefModule@@3JA; long g_lRefModule
0x180019a39  mov     rbx, [rsp+28h+arg_0]
0x180019a3e  mov     rsi, [rsp+28h+arg_8]
0x180019a43  add     rsp, 20h
0x180019a47  pop     rdi
0x180019a48  retn
```
