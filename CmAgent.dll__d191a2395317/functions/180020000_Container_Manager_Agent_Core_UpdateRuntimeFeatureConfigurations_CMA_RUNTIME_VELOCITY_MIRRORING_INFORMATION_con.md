# Container::Manager::Agent::Core::UpdateRuntimeFeatureConfigurations(_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION const &)

- ea: `0x180020000`
- end: `0x1800200de`
- name: `?UpdateRuntimeFeatureConfigurations@Core@Agent@Manager@Container@@YAJAEBU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core *this, const struct _CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *, __int64, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180004e30`
- `0x1800052b0`
- `0x1800178e0`

## callees

- `0x180002140`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x18000892c`
- `0x18000a768`
- `0x18001c640`
- `0x180020000`

## import_xrefs

- `ntdll!RtlOverwriteFeatureConfigurationBuffer` at `0x180020063`
- `ntdll!RtlOverwriteFeatureConfigurationBuffer` at `0x180020063`

## string_xrefs

- `0x180020022`: `UpdateRuntimeFeatureConfigurations`
- `0x18002007b`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::UpdateRuntimeFeatureConfigurations(
        Container::Manager::Agent::Core *this,
        const struct _CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r9
  __int64 v6; // r8
  int v7; // eax
  unsigned int v8; // ebx
  int v10[4]; // [rsp+20h] [rbp-178h] BYREF
  _QWORD v11[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v11,
    "UpdateRuntimeFeatureConfigurations",
    a3,
    a4);
  v11[0] = &CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations::`vftable';
  CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations::StartActivity((CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations *)v11);
  v5 = *((unsigned int *)this + 2);
  v6 = *(_QWORD *)this;
  *(_QWORD *)v10 = 0;
  v7 = RtlOverwriteFeatureConfigurationBuffer(v10, 1, v6, v5);
  if ( v7 >= 0 )
  {
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v11,
      0);
    v8 = 0;
  }
  else
  {
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x327,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
           (const char *)(unsigned int)v7,
           v10[0]);
  }
  v11[0] = &CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v11);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v11);
  return v8;
}

```

## disassembly

```asm
0x180020000  mov     [rsp+arg_8], rbx
0x180020005  push    rdi
0x180020006  sub     rsp, 190h
0x18002000d  mov     rax, cs:__security_cookie
0x180020014  xor     rax, rsp
0x180020017  mov     [rsp+198h+var_18], rax
0x18002001f  mov     rbx, rcx
0x180020022  lea     rdx, aUpdateruntimef; "UpdateRuntimeFeatureConfigurations"
0x180020029  lea     rcx, [rsp+198h+var_168]
0x18002002e  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180020033  lea     rdi, ??_7UpdateRuntimeFeatureConfigurations@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations::`vftable'
0x18002003a  lea     rcx, [rsp+198h+var_168]; this
0x18002003f  mov     [rsp+198h+var_168], rdi
0x180020044  call    ?StartActivity@UpdateRuntimeFeatureConfigurations@CmAgentTraceProvider@@QEAAXXZ; CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations::StartActivity(void)
0x180020049  mov     r9d, [rbx+8]
0x18002004d  lea     rcx, [rsp+198h+var_178]
0x180020052  mov     r8, [rbx]
0x180020055  mov     edx, 1
0x18002005a  mov     qword ptr [rsp+198h+var_178], 0; int
0x180020063  call    cs:__imp_RtlOverwriteFeatureConfigurationBuffer
0x18002006a  nop     dword ptr [rax+rax+00h]
0x18002006f  test    eax, eax
0x180020071  jns     short loc_180020093
0x180020073  mov     rcx, [rsp+198h]; this
0x18002007b  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180020082  mov     r9d, eax; char *
0x180020085  mov     edx, 327h; void *
0x18002008a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002008f  mov     ebx, eax
0x180020091  jmp     short loc_1800200A1
0x180020093  xor     edx, edx
0x180020095  lea     rcx, [rsp+198h+var_168]
0x18002009a  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002009f  xor     ebx, ebx
0x1800200a1  lea     rcx, [rsp+198h+var_168]
0x1800200a6  mov     [rsp+198h+var_168], rdi
0x1800200ab  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800200b0  lea     rcx, [rsp+198h+var_168]
0x1800200b5  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800200ba  mov     eax, ebx
0x1800200bc  mov     rcx, [rsp+198h+var_18]
0x1800200c4  xor     rcx, rsp; StackCookie
0x1800200c7  call    __security_check_cookie
0x1800200cc  mov     rbx, [rsp+198h+arg_8]
0x1800200d4  add     rsp, 190h
0x1800200db  pop     rdi
0x1800200dc  retn
```
