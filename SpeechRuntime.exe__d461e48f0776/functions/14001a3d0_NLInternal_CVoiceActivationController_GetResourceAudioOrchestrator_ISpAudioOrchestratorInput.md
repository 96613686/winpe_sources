# NLInternal::CVoiceActivationController::GetResourceAudioOrchestrator(ISpAudioOrchestratorInput * *)

- ea: `0x14001a3d0`
- end: `0x14001a4a0`
- name: `?GetResourceAudioOrchestrator@CVoiceActivationController@NLInternal@@AEAAJPEAPEAUISpAudioOrchestratorInput@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(NLInternal::CVoiceActivationController *__hidden this, struct ISpAudioOrchestratorInput **)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001a610`
- `0x14001ac50`
- `0x14001b000`
- `0x14001b110`

## callees

- `0x140007c0c`
- `0x140011ea8`
- `0x14001a3d0`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001a407`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001a407`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NLInternal::CVoiceActivationController::GetResourceAudioOrchestrator(
        NLInternal::CVoiceActivationController *this,
        struct ISpAudioOrchestratorInput **a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  LPVOID v7; // [rsp+50h] [rbp+8h] BYREF

  v7 = 0;
  v3 = CoCreateInstance(&CLSID_SpResourceManager, 0, 0x17u, &GUID_93384e18_5014_43d5_adbb_a78e055926bd, &v7);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, GUID *, _DWORD, struct ISpAudioOrchestratorInput **))(*(_QWORD *)v7 + 40LL))(
           v7,
           &CLSID_SpAudioOrchestrator,
           &GUID_NULL,
           &IID_ISpAudioOrchestratorInput,
           0,
           a2);
    v4 = v5;
    if ( v5 < 0 )
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"NLInternal::CVoiceActivationController::GetResourceAudioOrchestrator",
        L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceactivation\\voiceactivationcontroller.cpp(57)",
        v5);
  }
  else
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"NLInternal::CVoiceActivationController::GetResourceAudioOrchestrator",
      L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceactivation\\voiceactivationcontroller.cpp(56)",
      v3);
  }
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v7);
  return v4;
}

```

## disassembly

```asm
0x14001a3d0  mov     r11, rsp
0x14001a3d3  mov     [r11+10h], rbx
0x14001a3d7  mov     [r11+8], rcx
0x14001a3db  push    rdi
0x14001a3dc  sub     rsp, 40h
0x14001a3e0  mov     rdi, rdx
0x14001a3e3  mov     qword ptr [r11+8], 0
0x14001a3eb  lea     rax, [r11+8]
0x14001a3ef  mov     [r11-28h], rax
0x14001a3f3  lea     r9, _GUID_93384e18_5014_43d5_adbb_a78e055926bd; riid
0x14001a3fa  xor     edx, edx; pUnkOuter
0x14001a3fc  lea     r8d, [rdx+17h]; dwClsContext
0x14001a400  lea     rcx, CLSID_SpResourceManager; rclsid
0x14001a407  call    cs:__imp_CoCreateInstance
0x14001a40d  mov     ebx, eax
0x14001a40f  test    eax, eax
0x14001a411  jns     short loc_14001A420
0x14001a413  mov     dword ptr [rsp+48h+var_20], eax
0x14001a417  lea     rax, aOnecoreuapEndu_110; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001a41e  jmp     short loc_14001A464
0x14001a420  mov     rcx, [rsp+48h+arg_0]
0x14001a425  mov     rax, [rcx]
0x14001a428  mov     [rsp+48h+var_20], rdi
0x14001a42d  mov     dword ptr [rsp+48h+var_28], 0
0x14001a435  lea     r9, IID_ISpAudioOrchestratorInput
0x14001a43c  lea     r8, GUID_NULL
0x14001a443  lea     rdx, CLSID_SpAudioOrchestrator
0x14001a44a  mov     rax, [rax+28h]
0x14001a44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a453  mov     ebx, eax
0x14001a455  test    eax, eax
0x14001a457  jns     short loc_14001A489
0x14001a459  mov     dword ptr [rsp+48h+var_20], eax
0x14001a45d  lea     rax, aOnecoreuapEndu_109; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001a464  mov     [rsp+48h+var_28], rax
0x14001a469  lea     r9, aNlinternalCvoi_4; "NLInternal::CVoiceActivationController:"...
0x14001a470  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14001a477  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14001a47e  mov     ecx, 2; int
0x14001a483  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001a488  nop
0x14001a489  lea     rcx, [rsp+48h+arg_0]
0x14001a48e  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14001a493  mov     eax, ebx
0x14001a495  mov     rbx, [rsp+48h+arg_8]
0x14001a49a  add     rsp, 40h
0x14001a49e  pop     rdi
0x14001a49f  retn
```
