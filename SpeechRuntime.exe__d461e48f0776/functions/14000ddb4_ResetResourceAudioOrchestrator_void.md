# ResetResourceAudioOrchestrator(void)

- ea: `0x14000ddb4`
- end: `0x14000de73`
- name: `?ResetResourceAudioOrchestrator@@YAJXZ`
- size: `191`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000849c`

## callees

- `0x140007c0c`
- `0x140008000`
- `0x14000a1b0`
- `0x14000ddb4`
- `0x14000e030`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ddf9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ddf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 ResetResourceAudioOrchestrator(void)
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  __int64 v2; // rdx
  int ppv; // [rsp+20h] [rbp-68h]
  _BYTE v5[88]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  LPVOID v7; // [rsp+90h] [rbp+8h] BYREF

  v7 = 0;
  SpPerfTelemetry::SpeechRuntime::ContinueActivityOnCurrentThread(&g_telemetry, v5);
  v0 = CoCreateInstance(&CLSID_SpResourceManager, 0, 0x17u, &GUID_93384e18_5014_43d5_adbb_a78e055926bd, &v7);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v0 = (*(__int64 (__fastcall **)(LPVOID, GUID *, _QWORD))(*(_QWORD *)v7 + 32LL))(v7, &CLSID_SpAudioOrchestrator, 0);
    v1 = v0;
    if ( v0 >= 0 )
    {
      v1 = 0;
      goto LABEL_7;
    }
    v2 = 209;
  }
  else
  {
    v2 = 208;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\exe\\speechruntime.cpp",
    (const char *)(unsigned int)v0,
    ppv);
LABEL_7:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v5);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v7);
  return v1;
}

```

## disassembly

```asm
0x14000ddb4  mov     rax, rsp
0x14000ddb7  push    rbx
0x14000ddb8  sub     rsp, 80h
0x14000ddbf  mov     qword ptr [rax+8], 0
0x14000ddc7  lea     rdx, [rax-58h]
0x14000ddcb  lea     rcx, ?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A; SpPerfTelemetry::SpeechRuntime g_telemetry
0x14000ddd2  call    ?ContinueActivityOnCurrentThread@SpeechRuntime@SpPerfTelemetry@@UEAA?AVActivityThreadWatcher@wil@@XZ; SpPerfTelemetry::SpeechRuntime::ContinueActivityOnCurrentThread(void)
0x14000ddd7  nop
0x14000ddd8  lea     rax, [rsp+88h+arg_0]
0x14000dde0  mov     qword ptr [rsp+88h+ppv], rax; int
0x14000dde5  lea     r9, _GUID_93384e18_5014_43d5_adbb_a78e055926bd; riid
0x14000ddec  xor     edx, edx; pUnkOuter
0x14000ddee  lea     r8d, [rdx+17h]; dwClsContext
0x14000ddf2  lea     rcx, CLSID_SpResourceManager; rclsid
0x14000ddf9  call    cs:__imp_CoCreateInstance
0x14000ddff  mov     ebx, eax
0x14000de01  test    eax, eax
0x14000de03  jns     short loc_14000DE0C
0x14000de05  mov     edx, 0D0h
0x14000de0a  jmp     short loc_14000DE35
0x14000de0c  mov     rcx, [rsp+88h+arg_0]
0x14000de14  mov     rax, [rcx]
0x14000de17  xor     r8d, r8d
0x14000de1a  lea     rdx, CLSID_SpAudioOrchestrator
0x14000de21  mov     rax, [rax+20h]
0x14000de25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de2a  mov     ebx, eax
0x14000de2c  test    eax, eax
0x14000de2e  jns     short loc_14000DE4E
0x14000de30  mov     edx, 0D1h; void *
0x14000de35  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14000de3c  mov     r9d, eax; char *
0x14000de3f  mov     rcx, [rsp+88h]; this
0x14000de47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000de4c  jmp     short loc_14000DE50
0x14000de4e  xor     ebx, ebx
0x14000de50  lea     rcx, [rsp+88h+var_58]; this
0x14000de55  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000de5a  nop
0x14000de5b  lea     rcx, [rsp+88h+arg_0]
0x14000de63  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14000de68  mov     eax, ebx
0x14000de6a  add     rsp, 80h
0x14000de71  pop     rbx
0x14000de72  retn
```
