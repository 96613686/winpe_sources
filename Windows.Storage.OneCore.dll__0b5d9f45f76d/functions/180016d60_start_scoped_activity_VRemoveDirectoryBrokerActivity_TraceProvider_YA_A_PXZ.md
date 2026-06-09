# ??$start_scoped_activity@VRemoveDirectoryBrokerActivity@TraceProvider@@@@YA?A_PXZ

- ea: `0x180016d60`
- end: `0x180016e18`
- name: `??$start_scoped_activity@VRemoveDirectoryBrokerActivity@TraceProvider@@@@YA?A_PXZ`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800188a0`

## callees

- `0x180002be0`
- `0x18000c680`
- `0x18000c764`
- `0x1800173f0`
- `0x18001922c`

## string_xrefs

- `0x180016d82`: `RemoveDirectoryBrokerActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall start_scoped_activity<TraceProvider::RemoveDirectoryBrokerActivity>(__int64 a1)
{
  _QWORD v3[42]; // [rsp+20h] [rbp-2B8h] BYREF
  _QWORD v4[42]; // [rsp+170h] [rbp-168h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v3);
  v3[0] = &TraceProvider::RemoveDirectoryBrokerActivity::`vftable';
  TraceProvider::RemoveDirectoryBrokerActivity::StartActivity((TraceProvider::RemoveDirectoryBrokerActivity *)v3);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v4,
    v3);
  v4[0] = &TraceProvider::RemoveDirectoryBrokerActivity::`vftable';
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    v4);
  *(_QWORD *)a1 = &TraceProvider::RemoveDirectoryBrokerActivity::`vftable';
  *(_BYTE *)(a1 + 336) = 1;
  TraceProvider::RemoveDirectoryBrokerActivity::~RemoveDirectoryBrokerActivity((TraceProvider::RemoveDirectoryBrokerActivity *)v4);
  TraceProvider::RemoveDirectoryBrokerActivity::~RemoveDirectoryBrokerActivity((TraceProvider::RemoveDirectoryBrokerActivity *)v3);
  return a1;
}

```

## disassembly

```asm
0x180016d60  mov     [rsp+arg_8], rbx
0x180016d65  push    rdi
0x180016d66  sub     rsp, 2D0h
0x180016d6d  mov     rax, cs:__security_cookie
0x180016d74  xor     rax, rsp
0x180016d77  mov     [rsp+2D8h+var_18], rax
0x180016d7f  mov     rbx, rcx
0x180016d82  lea     rdx, aRemovedirector_0; "RemoveDirectoryBrokerActivity"
0x180016d89  lea     rcx, [rsp+2D8h+var_2B8]; struct wil::details::IFailureCallback *
0x180016d8e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016d93  lea     rdi, ??_7RemoveDirectoryBrokerActivity@TraceProvider@@6B@; const TraceProvider::RemoveDirectoryBrokerActivity::`vftable'
0x180016d9a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016d9f  mov     [rsp+2D8h+var_2B8], rdi
0x180016da4  call    ?StartActivity@RemoveDirectoryBrokerActivity@TraceProvider@@QEAAXXZ; TraceProvider::RemoveDirectoryBrokerActivity::StartActivity(void)
0x180016da9  lea     rdx, [rsp+2D8h+var_2B8]
0x180016dae  lea     rcx, [rsp+2D8h+var_168]
0x180016db6  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016dbb  lea     rdx, [rsp+2D8h+var_168]
0x180016dc3  mov     [rsp+2D8h+var_168], rdi
0x180016dcb  mov     rcx, rbx
0x180016dce  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016dd3  mov     [rbx], rdi
0x180016dd6  lea     rcx, [rsp+2D8h+var_168]; this
0x180016dde  mov     byte ptr [rbx+150h], 1
0x180016de5  call    ??1RemoveDirectoryBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::RemoveDirectoryBrokerActivity::~RemoveDirectoryBrokerActivity(void)
0x180016dea  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016def  call    ??1RemoveDirectoryBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::RemoveDirectoryBrokerActivity::~RemoveDirectoryBrokerActivity(void)
0x180016df4  mov     rax, rbx
0x180016df7  mov     rcx, [rsp+2D8h+var_18]
0x180016dff  xor     rcx, rsp; StackCookie
0x180016e02  call    __security_check_cookie
0x180016e07  mov     rbx, [rsp+2D8h+arg_8]
0x180016e0f  add     rsp, 2D0h
0x180016e16  pop     rdi
0x180016e17  retn
```
