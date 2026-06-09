# ??$start_scoped_activity@VGetFileAttributesExBrokerActivity@TraceProvider@@@@YA?A_PXZ

- ea: `0x180016be0`
- end: `0x180016c98`
- name: `??$start_scoped_activity@VGetFileAttributesExBrokerActivity@TraceProvider@@@@YA?A_PXZ`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017f70`

## callees

- `0x180002be0`
- `0x18000c680`
- `0x18000c764`
- `0x180017360`
- `0x1800190ec`

## string_xrefs

- `0x180016c02`: `GetFileAttributesExBrokerActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall start_scoped_activity<TraceProvider::GetFileAttributesExBrokerActivity>(__int64 a1)
{
  _QWORD v3[42]; // [rsp+20h] [rbp-2B8h] BYREF
  _QWORD v4[42]; // [rsp+170h] [rbp-168h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v3);
  v3[0] = &TraceProvider::GetFileAttributesExBrokerActivity::`vftable';
  TraceProvider::GetFileAttributesExBrokerActivity::StartActivity((TraceProvider::GetFileAttributesExBrokerActivity *)v3);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v4,
    v3);
  v4[0] = &TraceProvider::GetFileAttributesExBrokerActivity::`vftable';
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    v4);
  *(_QWORD *)a1 = &TraceProvider::GetFileAttributesExBrokerActivity::`vftable';
  *(_BYTE *)(a1 + 336) = 1;
  TraceProvider::GetFileAttributesExBrokerActivity::~GetFileAttributesExBrokerActivity((TraceProvider::GetFileAttributesExBrokerActivity *)v4);
  TraceProvider::GetFileAttributesExBrokerActivity::~GetFileAttributesExBrokerActivity((TraceProvider::GetFileAttributesExBrokerActivity *)v3);
  return a1;
}

```

## disassembly

```asm
0x180016be0  mov     [rsp+arg_8], rbx
0x180016be5  push    rdi
0x180016be6  sub     rsp, 2D0h
0x180016bed  mov     rax, cs:__security_cookie
0x180016bf4  xor     rax, rsp
0x180016bf7  mov     [rsp+2D8h+var_18], rax
0x180016bff  mov     rbx, rcx
0x180016c02  lea     rdx, aGetfileattribu_1; "GetFileAttributesExBrokerActivity"
0x180016c09  lea     rcx, [rsp+2D8h+var_2B8]; struct wil::details::IFailureCallback *
0x180016c0e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016c13  lea     rdi, ??_7GetFileAttributesExBrokerActivity@TraceProvider@@6B@; const TraceProvider::GetFileAttributesExBrokerActivity::`vftable'
0x180016c1a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016c1f  mov     [rsp+2D8h+var_2B8], rdi
0x180016c24  call    ?StartActivity@GetFileAttributesExBrokerActivity@TraceProvider@@QEAAXXZ; TraceProvider::GetFileAttributesExBrokerActivity::StartActivity(void)
0x180016c29  lea     rdx, [rsp+2D8h+var_2B8]
0x180016c2e  lea     rcx, [rsp+2D8h+var_168]
0x180016c36  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016c3b  lea     rdx, [rsp+2D8h+var_168]
0x180016c43  mov     [rsp+2D8h+var_168], rdi
0x180016c4b  mov     rcx, rbx
0x180016c4e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016c53  mov     [rbx], rdi
0x180016c56  lea     rcx, [rsp+2D8h+var_168]; this
0x180016c5e  mov     byte ptr [rbx+150h], 1
0x180016c65  call    ??1GetFileAttributesExBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::GetFileAttributesExBrokerActivity::~GetFileAttributesExBrokerActivity(void)
0x180016c6a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016c6f  call    ??1GetFileAttributesExBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::GetFileAttributesExBrokerActivity::~GetFileAttributesExBrokerActivity(void)
0x180016c74  mov     rax, rbx
0x180016c77  mov     rcx, [rsp+2D8h+var_18]
0x180016c7f  xor     rcx, rsp; StackCookie
0x180016c82  call    __security_check_cookie
0x180016c87  mov     rbx, [rsp+2D8h+arg_8]
0x180016c8f  add     rsp, 2D0h
0x180016c96  pop     rdi
0x180016c97  retn
```
