# CreateResourceAudioOrchestrator(ISpAudioOrchestratorInit * *)

- ea: `0x14000ab00`
- end: `0x14000ac1c`
- name: `?CreateResourceAudioOrchestrator@@YAJPEAPEAUISpAudioOrchestratorInit@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct ISpAudioOrchestratorInit **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000a2a0`

## callees

- `0x140007c0c`
- `0x140008000`
- `0x14000a1b0`
- `0x14000ab00`
- `0x14000e030`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ab4c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ab7f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ab4c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ab7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateResourceAudioOrchestrator(struct ISpAudioOrchestratorInit **a1)
{
  HRESULT Instance; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  struct ISpAudioOrchestratorInit *v5; // rax
  int ppv; // [rsp+20h] [rbp-68h]
  _BYTE v8[88]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  LPVOID v10; // [rsp+98h] [rbp+10h] BYREF

  v10 = 0;
  SpPerfTelemetry::SpeechRuntime::ContinueActivityOnCurrentThread(&g_telemetry, v8);
  Instance = CoCreateInstance(&CLSID_SpAudioOrchestrator, 0, 0x17u, &GUID_d8ebd271_83e3_492d_8fa1_a6d1496f6684, &v10);
  v3 = Instance;
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(
                 &CLSID_SpResourceManager,
                 0,
                 0x17u,
                 &GUID_93384e18_5014_43d5_adbb_a78e055926bd,
                 &g_cpResourceManager);
    v3 = Instance;
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, GUID *, LPVOID))(*(_QWORD *)g_cpResourceManager + 32LL))(
                   g_cpResourceManager,
                   &CLSID_SpAudioOrchestrator,
                   v10);
      v3 = Instance;
      if ( Instance >= 0 )
      {
        v5 = (struct ISpAudioOrchestratorInit *)v10;
        v10 = 0;
        *a1 = v5;
        v3 = 0;
        goto LABEL_9;
      }
      v4 = 233;
    }
    else
    {
      v4 = 227;
    }
  }
  else
  {
    v4 = 226;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\exe\\speechruntime.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_9:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v10);
  return v3;
}

```

## disassembly

```asm
0x14000ab00  mov     rax, rsp
0x14000ab03  mov     [rax+8], rbx
0x14000ab07  push    rdi
0x14000ab08  sub     rsp, 80h
0x14000ab0f  mov     rdi, rcx
0x14000ab12  mov     qword ptr [rax+10h], 0
0x14000ab1a  lea     rdx, [rax-58h]
0x14000ab1e  lea     rcx, ?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A; SpPerfTelemetry::SpeechRuntime g_telemetry
0x14000ab25  call    ?ContinueActivityOnCurrentThread@SpeechRuntime@SpPerfTelemetry@@UEAA?AVActivityThreadWatcher@wil@@XZ; SpPerfTelemetry::SpeechRuntime::ContinueActivityOnCurrentThread(void)
0x14000ab2a  nop
0x14000ab2b  lea     rax, [rsp+88h+arg_8]
0x14000ab33  mov     qword ptr [rsp+88h+ppv], rax; ppv
0x14000ab38  lea     r9, _GUID_d8ebd271_83e3_492d_8fa1_a6d1496f6684; riid
0x14000ab3f  xor     edx, edx; pUnkOuter
0x14000ab41  lea     r8d, [rdx+17h]; dwClsContext
0x14000ab45  lea     rcx, CLSID_SpAudioOrchestrator; rclsid
0x14000ab4c  call    cs:__imp_CoCreateInstance
0x14000ab52  mov     ebx, eax
0x14000ab54  test    eax, eax
0x14000ab56  jns     short loc_14000AB5F
0x14000ab58  mov     edx, 0E2h
0x14000ab5d  jmp     short loc_14000AB90
0x14000ab5f  lea     rax, ?g_cpResourceManager@@3V?$CComPtr@UISpResourceManager@@@ATL@@A; ATL::CComPtr<ISpResourceManager> g_cpResourceManager
0x14000ab66  mov     qword ptr [rsp+88h+ppv], rax; int
0x14000ab6b  lea     r9, _GUID_93384e18_5014_43d5_adbb_a78e055926bd; riid
0x14000ab72  xor     edx, edx; pUnkOuter
0x14000ab74  lea     r8d, [rdx+17h]; dwClsContext
0x14000ab78  lea     rcx, CLSID_SpResourceManager; rclsid
0x14000ab7f  call    cs:__imp_CoCreateInstance
0x14000ab85  mov     ebx, eax
0x14000ab87  test    eax, eax
0x14000ab89  jns     short loc_14000ABA9
0x14000ab8b  mov     edx, 0E3h; void *
0x14000ab90  mov     rcx, [rsp+88h]; this
0x14000ab98  mov     r9d, eax; char *
0x14000ab9b  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14000aba2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000aba7  jmp     short loc_14000ABF1
0x14000aba9  mov     rcx, cs:?g_cpResourceManager@@3V?$CComPtr@UISpResourceManager@@@ATL@@A; ATL::CComPtr<ISpResourceManager> g_cpResourceManager
0x14000abb0  mov     rax, [rcx]
0x14000abb3  mov     r8, [rsp+88h+arg_8]
0x14000abbb  lea     rdx, CLSID_SpAudioOrchestrator
0x14000abc2  mov     rax, [rax+20h]
0x14000abc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abcb  mov     ebx, eax
0x14000abcd  test    eax, eax
0x14000abcf  jns     short loc_14000ABD8
0x14000abd1  mov     edx, 0E9h
0x14000abd6  jmp     short loc_14000AB90
0x14000abd8  mov     rax, [rsp+88h+arg_8]
0x14000abe0  mov     [rsp+88h+arg_8], 0
0x14000abec  mov     [rdi], rax
0x14000abef  xor     ebx, ebx
0x14000abf1  lea     rcx, [rsp+88h+var_58]; this
0x14000abf6  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000abfb  nop
0x14000abfc  lea     rcx, [rsp+88h+arg_8]
0x14000ac04  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14000ac09  mov     eax, ebx
0x14000ac0b  mov     rbx, [rsp+88h+arg_0]
0x14000ac13  add     rsp, 80h
0x14000ac1a  pop     rdi
0x14000ac1b  retn
```
