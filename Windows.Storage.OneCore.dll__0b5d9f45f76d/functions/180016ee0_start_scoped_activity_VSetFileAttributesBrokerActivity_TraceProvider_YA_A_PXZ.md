# ??$start_scoped_activity@VSetFileAttributesBrokerActivity@TraceProvider@@@@YA?A_PXZ

- ea: `0x180016ee0`
- end: `0x180016f98`
- name: `??$start_scoped_activity@VSetFileAttributesBrokerActivity@TraceProvider@@@@YA?A_PXZ`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018bb0`

## callees

- `0x180002be0`
- `0x18000c680`
- `0x18000c764`
- `0x180017448`
- `0x18001936c`

## string_xrefs

- `0x180016f02`: `SetFileAttributesBrokerActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall start_scoped_activity<TraceProvider::SetFileAttributesBrokerActivity>(__int64 a1)
{
  _QWORD v3[42]; // [rsp+20h] [rbp-2B8h] BYREF
  _QWORD v4[42]; // [rsp+170h] [rbp-168h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v3);
  v3[0] = &TraceProvider::SetFileAttributesBrokerActivity::`vftable';
  TraceProvider::SetFileAttributesBrokerActivity::StartActivity((TraceProvider::SetFileAttributesBrokerActivity *)v3);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v4,
    v3);
  v4[0] = &TraceProvider::SetFileAttributesBrokerActivity::`vftable';
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    v4);
  *(_QWORD *)a1 = &TraceProvider::SetFileAttributesBrokerActivity::`vftable';
  *(_BYTE *)(a1 + 336) = 1;
  TraceProvider::SetFileAttributesBrokerActivity::~SetFileAttributesBrokerActivity((TraceProvider::SetFileAttributesBrokerActivity *)v4);
  TraceProvider::SetFileAttributesBrokerActivity::~SetFileAttributesBrokerActivity((TraceProvider::SetFileAttributesBrokerActivity *)v3);
  return a1;
}

```

## disassembly

```asm
0x180016ee0  mov     [rsp+arg_8], rbx
0x180016ee5  push    rdi
0x180016ee6  sub     rsp, 2D0h
0x180016eed  mov     rax, cs:__security_cookie
0x180016ef4  xor     rax, rsp
0x180016ef7  mov     [rsp+2D8h+var_18], rax
0x180016eff  mov     rbx, rcx
0x180016f02  lea     rdx, aSetfileattribu_0; "SetFileAttributesBrokerActivity"
0x180016f09  lea     rcx, [rsp+2D8h+var_2B8]; struct wil::details::IFailureCallback *
0x180016f0e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016f13  lea     rdi, ??_7SetFileAttributesBrokerActivity@TraceProvider@@6B@; const TraceProvider::SetFileAttributesBrokerActivity::`vftable'
0x180016f1a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016f1f  mov     [rsp+2D8h+var_2B8], rdi
0x180016f24  call    ?StartActivity@SetFileAttributesBrokerActivity@TraceProvider@@QEAAXXZ; TraceProvider::SetFileAttributesBrokerActivity::StartActivity(void)
0x180016f29  lea     rdx, [rsp+2D8h+var_2B8]
0x180016f2e  lea     rcx, [rsp+2D8h+var_168]
0x180016f36  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016f3b  lea     rdx, [rsp+2D8h+var_168]
0x180016f43  mov     [rsp+2D8h+var_168], rdi
0x180016f4b  mov     rcx, rbx
0x180016f4e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016f53  mov     [rbx], rdi
0x180016f56  lea     rcx, [rsp+2D8h+var_168]; this
0x180016f5e  mov     byte ptr [rbx+150h], 1
0x180016f65  call    ??1SetFileAttributesBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::SetFileAttributesBrokerActivity::~SetFileAttributesBrokerActivity(void)
0x180016f6a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016f6f  call    ??1SetFileAttributesBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::SetFileAttributesBrokerActivity::~SetFileAttributesBrokerActivity(void)
0x180016f74  mov     rax, rbx
0x180016f77  mov     rcx, [rsp+2D8h+var_18]
0x180016f7f  xor     rcx, rsp; StackCookie
0x180016f82  call    __security_check_cookie
0x180016f87  mov     rbx, [rsp+2D8h+arg_8]
0x180016f8f  add     rsp, 2D0h
0x180016f96  pop     rdi
0x180016f97  retn
```
