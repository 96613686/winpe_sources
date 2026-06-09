# ??$start_scoped_activity@VDeleteFileBrokerActivity@TraceProvider@@@@YA?A_PXZ

- ea: `0x1800169a0`
- end: `0x180016a58`
- name: `??$start_scoped_activity@VDeleteFileBrokerActivity@TraceProvider@@@@YA?A_PXZ`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017b70`

## callees

- `0x180002be0`
- `0x18000c680`
- `0x18000c764`
- `0x1800172dc`
- `0x180018f0c`

## string_xrefs

- `0x1800169c2`: `DeleteFileBrokerActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall start_scoped_activity<TraceProvider::DeleteFileBrokerActivity>(__int64 a1)
{
  _QWORD v3[42]; // [rsp+20h] [rbp-2B8h] BYREF
  _QWORD v4[42]; // [rsp+170h] [rbp-168h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v3);
  v3[0] = &TraceProvider::DeleteFileBrokerActivity::`vftable';
  TraceProvider::DeleteFileBrokerActivity::StartActivity((TraceProvider::DeleteFileBrokerActivity *)v3);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v4,
    v3);
  v4[0] = &TraceProvider::DeleteFileBrokerActivity::`vftable';
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    v4);
  *(_QWORD *)a1 = &TraceProvider::DeleteFileBrokerActivity::`vftable';
  *(_BYTE *)(a1 + 336) = 1;
  TraceProvider::DeleteFileBrokerActivity::~DeleteFileBrokerActivity((TraceProvider::DeleteFileBrokerActivity *)v4);
  TraceProvider::DeleteFileBrokerActivity::~DeleteFileBrokerActivity((TraceProvider::DeleteFileBrokerActivity *)v3);
  return a1;
}

```

## disassembly

```asm
0x1800169a0  mov     [rsp+arg_8], rbx
0x1800169a5  push    rdi
0x1800169a6  sub     rsp, 2D0h
0x1800169ad  mov     rax, cs:__security_cookie
0x1800169b4  xor     rax, rsp
0x1800169b7  mov     [rsp+2D8h+var_18], rax
0x1800169bf  mov     rbx, rcx
0x1800169c2  lea     rdx, aDeletefilebrok; "DeleteFileBrokerActivity"
0x1800169c9  lea     rcx, [rsp+2D8h+var_2B8]; struct wil::details::IFailureCallback *
0x1800169ce  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800169d3  lea     rdi, ??_7DeleteFileBrokerActivity@TraceProvider@@6B@; const TraceProvider::DeleteFileBrokerActivity::`vftable'
0x1800169da  lea     rcx, [rsp+2D8h+var_2B8]; this
0x1800169df  mov     [rsp+2D8h+var_2B8], rdi
0x1800169e4  call    ?StartActivity@DeleteFileBrokerActivity@TraceProvider@@QEAAXXZ; TraceProvider::DeleteFileBrokerActivity::StartActivity(void)
0x1800169e9  lea     rdx, [rsp+2D8h+var_2B8]
0x1800169ee  lea     rcx, [rsp+2D8h+var_168]
0x1800169f6  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x1800169fb  lea     rdx, [rsp+2D8h+var_168]
0x180016a03  mov     [rsp+2D8h+var_168], rdi
0x180016a0b  mov     rcx, rbx
0x180016a0e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016a13  mov     [rbx], rdi
0x180016a16  lea     rcx, [rsp+2D8h+var_168]; this
0x180016a1e  mov     byte ptr [rbx+150h], 1
0x180016a25  call    ??1DeleteFileBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::DeleteFileBrokerActivity::~DeleteFileBrokerActivity(void)
0x180016a2a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016a2f  call    ??1DeleteFileBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::DeleteFileBrokerActivity::~DeleteFileBrokerActivity(void)
0x180016a34  mov     rax, rbx
0x180016a37  mov     rcx, [rsp+2D8h+var_18]
0x180016a3f  xor     rcx, rsp; StackCookie
0x180016a42  call    __security_check_cookie
0x180016a47  mov     rbx, [rsp+2D8h+arg_8]
0x180016a4f  add     rsp, 2D0h
0x180016a56  pop     rdi
0x180016a57  retn
```
