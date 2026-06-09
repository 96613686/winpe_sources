# CmaRpcSrv_NotifyResuming

- ea: `0x180004e30`
- end: `0x180004f33`
- name: `CmaRpcSrv_NotifyResuming`
- size: `259`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, Container::Manager::Agent::Core *, Container::Manager::Agent::Core *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002140`
- `0x1800045e4`
- `0x180004e30`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x18000892c`
- `0x18001bfb4`
- `0x18001fb70`
- `0x180020000`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180004f01`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180004f01`

## string_xrefs

- `0x180004e9a`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
RPC_STATUS __fastcall CmaRpcSrv_NotifyResuming(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        Container::Manager::Agent::Core *a3,
        Container::Manager::Agent::Core *a4)
{
  struct _CMA_HOT_PATCH_MIRRORING_INFORMATION *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  int updated; // eax
  int v11; // ebx
  __int64 v12; // rdx
  int Reply[4]; // [rsp+20h] [rbp-188h] BYREF
  _QWORD v15[42]; // [rsp+30h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "NotifyResuming",
    a3,
    a4);
  v15[0] = &CmAgentTraceProvider::NotifyResuming::`vftable';
  CmAgentTraceProvider::NotifyResuming::StartActivity((CmAgentTraceProvider::NotifyResuming *)v15);
  if ( a3
    && (updated = Container::Manager::Agent::Core::UpdateRuntimeFeatureConfigurations(a3, v7, v8, v9),
        v11 = updated,
        updated < 0) )
  {
    v12 = 756;
  }
  else
  {
    if ( !*((_DWORD *)a4 + 2)
      || (updated = Container::Manager::Agent::Core::UpdateHotPatches(a4, v7, v8, v9), v11 = updated, updated >= 0) )
    {
      wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        v15,
        0);
      v11 = 0;
      goto LABEL_9;
    }
    v12 = 761;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
    (const char *)(unsigned int)updated,
    Reply[0]);
LABEL_9:
  v15[0] = &CmAgentTraceProvider::NotifyResuming::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v15);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v15);
  Reply[0] = v11;
  return RpcAsyncCompleteCall(pAsync, Reply);
}

```

## disassembly

```asm
0x180004e30  mov     [rsp+arg_8], rbx
0x180004e35  push    rsi
0x180004e36  push    rdi
0x180004e37  push    r14
0x180004e39  sub     rsp, 190h
0x180004e40  mov     rax, cs:__security_cookie
0x180004e47  xor     rax, rsp
0x180004e4a  mov     [rsp+1A8h+var_28], rax
0x180004e52  mov     rdi, r9
0x180004e55  mov     rbx, r8
0x180004e58  mov     rsi, rcx
0x180004e5b  lea     rdx, aNotifyresuming; "NotifyResuming"
0x180004e62  lea     rcx, [rsp+1A8h+var_178]
0x180004e67  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180004e6c  lea     r14, ??_7NotifyResuming@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::NotifyResuming::`vftable'
0x180004e73  mov     [rsp+1A8h+var_178], r14
0x180004e78  lea     rcx, [rsp+1A8h+var_178]; this
0x180004e7d  call    ?StartActivity@NotifyResuming@CmAgentTraceProvider@@QEAAXXZ; CmAgentTraceProvider::NotifyResuming::StartActivity(void)
0x180004e82  test    rbx, rbx
0x180004e85  jz      short loc_180004EB3
0x180004e87  mov     rcx, rbx; this
0x180004e8a  call    ?UpdateRuntimeFeatureConfigurations@Core@Agent@Manager@Container@@YAJAEBU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@@Z; Container::Manager::Agent::Core::UpdateRuntimeFeatureConfigurations(_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION const &)
0x180004e8f  mov     ebx, eax
0x180004e91  test    eax, eax
0x180004e93  jns     short loc_180004EB3
0x180004e95  mov     edx, 2F4h; void *
0x180004e9a  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180004ea1  mov     r9d, eax; char *
0x180004ea4  mov     rcx, [rsp+1A8h]; this
0x180004eac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004eb1  jmp     short loc_180004EDC
0x180004eb3  cmp     dword ptr [rdi+8], 0
0x180004eb7  jz      short loc_180004ECE
0x180004eb9  mov     rcx, rdi; this
0x180004ebc  call    ?UpdateHotPatches@Core@Agent@Manager@Container@@YAJAEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@Z; Container::Manager::Agent::Core::UpdateHotPatches(_CMA_HOT_PATCH_MIRRORING_INFORMATION &)
0x180004ec1  mov     ebx, eax
0x180004ec3  test    eax, eax
0x180004ec5  jns     short loc_180004ECE
0x180004ec7  mov     edx, 2F9h
0x180004ecc  jmp     short loc_180004E9A
0x180004ece  xor     edx, edx
0x180004ed0  lea     rcx, [rsp+1A8h+var_178]
0x180004ed5  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180004eda  xor     ebx, ebx
0x180004edc  mov     [rsp+1A8h+var_178], r14
0x180004ee1  lea     rcx, [rsp+1A8h+var_178]
0x180004ee6  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180004eeb  lea     rcx, [rsp+1A8h+var_178]
0x180004ef0  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180004ef5  mov     [rsp+1A8h+Reply], ebx
0x180004ef9  lea     rdx, [rsp+1A8h+Reply]; Reply
0x180004efe  mov     rcx, rsi; pAsync
0x180004f01  call    cs:__imp_RpcAsyncCompleteCall
0x180004f08  nop     dword ptr [rax+rax+00h]
0x180004f0d  nop
0x180004f0e  mov     rcx, [rsp+1A8h+var_28]
0x180004f16  xor     rcx, rsp; StackCookie
0x180004f19  call    __security_check_cookie
0x180004f1e  mov     rbx, [rsp+1A8h+arg_8]
0x180004f26  add     rsp, 190h
0x180004f2d  pop     r14
0x180004f2f  pop     rdi
0x180004f30  pop     rsi
0x180004f31  retn
```
