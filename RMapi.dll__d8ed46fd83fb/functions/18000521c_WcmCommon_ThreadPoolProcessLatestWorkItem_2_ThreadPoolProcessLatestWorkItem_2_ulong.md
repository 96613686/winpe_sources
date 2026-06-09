# WcmCommon::ThreadPoolProcessLatestWorkItem<2>::ThreadPoolProcessLatestWorkItem<2>(ulong)

- ea: `0x18000521c`
- end: `0x1800052f2`
- name: `??0?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@QEAA@K@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001df88`

## callees

- `0x18000521c`
- `0x180005300`
- `0x180005390`
- `0x180006e88`
- `0x180009f78`
- `0x18000d810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005236`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005236`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800052dd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800052dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem<2>::ThreadPoolProcessLatestWorkItem<2>(__int64 a1)
{
  struct _TP_WORK **v2; // rax
  PTP_WORK v4; // [rsp+70h] [rbp+18h] BYREF

  InitializeCriticalSectionEx((LPCRITICAL_SECTION)a1, 0x1F4u, 0);
  WcmCommon::details::TPEnvironment::TPEnvironment((WcmCommon::details::TPEnvironment *)(a1 + 40));
  *(_QWORD *)(a1 + 120) = 0;
  *(_DWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  `eh vector constructor iterator'(
    (void *)(a1 + 152),
    0x40u,
    2u,
    (void (*)(void *))std::any::any,
    (void (*)(void *))std::any::~any);
  *(_BYTE *)(a1 + 280) = 0;
  v2 = WcmCommon::details::TPEnvironment::create_tp(
         a1 + 40,
         &v4,
         (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))WcmCommon::ThreadPoolProcessLatestWorkItem<2>::WorkCallback,
         (void *)a1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator=(
    (struct _TP_WORK **)(a1 + 120),
    v2);
  if ( v4 )
    wil::details::DestroyThreadPoolWork<0>::Destroy(v4);
  *(_QWORD *)(a1 + 144) = 0;
  QueryPerformanceFrequency((LARGE_INTEGER *)(a1 + 144));
  return a1;
}

```

## disassembly

```asm
0x18000521c  mov     [rsp+arg_0], rcx
0x180005221  push    rbx
0x180005222  push    rbp
0x180005223  push    rsi
0x180005224  push    rdi
0x180005225  push    r14
0x180005227  sub     rsp, 30h
0x18000522b  mov     rbp, rcx
0x18000522e  xor     r8d, r8d; Flags
0x180005231  mov     edx, 1F4h; dwSpinCount
0x180005236  call    cs:__imp_InitializeCriticalSectionEx
0x18000523c  nop
0x18000523d  lea     rcx, [rbp+28h]; this
0x180005241  call    ??0TPEnvironment@details@WcmCommon@@QEAA@KK@Z; WcmCommon::details::TPEnvironment::TPEnvironment(ulong,ulong)
0x180005246  nop
0x180005247  mov     qword ptr [rbp+78h], 0
0x18000524f  mov     dword ptr [rbp+80h], 0
0x180005259  mov     qword ptr [rbp+88h], 0
0x180005264  lea     r14, [rbp+90h]
0x18000526b  xor     eax, eax
0x18000526d  mov     [r14], rax
0x180005270  lea     rax, ??1any@std@@QEAA@XZ; std::any::~any(void)
0x180005277  mov     [rsp+58h+var_38], rax; void (*)(void *)
0x18000527c  lea     r9, ??0any@std@@QEAA@XZ; void (*)(void *)
0x180005283  mov     edx, 40h ; '@'; unsigned __int64
0x180005288  lea     r8d, [rdx-3Eh]; unsigned __int64
0x18000528c  lea     rcx, [rbp+98h]; void *
0x180005293  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180005298  nop
0x180005299  mov     byte ptr [rbp+118h], 0
0x1800052a0  mov     r9, rbp
0x1800052a3  lea     r8, ?WorkCallback@?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; WcmCommon::ThreadPoolProcessLatestWorkItem<2>::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x1800052aa  lea     rdx, [rsp+58h+arg_10]
0x1800052af  lea     rcx, [rbp+28h]
0x1800052b3  call    ?create_tp@TPEnvironment@details@WcmCommon@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; WcmCommon::details::TPEnvironment::create_tp(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x1800052b8  mov     rdx, rax
0x1800052bb  lea     rcx, [rbp+78h]
0x1800052bf  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>> &&)
0x1800052c4  mov     rcx, [rsp+58h+arg_10]
0x1800052c9  test    rcx, rcx
0x1800052cc  jz      short loc_1800052D3
0x1800052ce  call    ?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z; wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)
0x1800052d3  mov     qword ptr [r14], 0
0x1800052da  mov     rcx, r14; lpFrequency
0x1800052dd  call    cs:__imp_QueryPerformanceFrequency
0x1800052e3  nop
0x1800052e4  mov     rax, rbp
0x1800052e7  add     rsp, 30h
0x1800052eb  pop     r14
0x1800052ed  pop     rdi
0x1800052ee  pop     rsi
0x1800052ef  pop     rbp
0x1800052f0  pop     rbx
0x1800052f1  retn
```
