# ??$start_scoped_activity@VCopyFileBrokerActivity@TraceProvider@@@@YA?A_PXZ

- ea: `0x180016760`
- end: `0x180016818`
- name: `??$start_scoped_activity@VCopyFileBrokerActivity@TraceProvider@@@@YA?A_PXZ`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800176f0`

## callees

- `0x180002be0`
- `0x18000c680`
- `0x18000c764`
- `0x180017258`
- `0x180018d2c`

## string_xrefs

- `0x180016782`: `CopyFileBrokerActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall start_scoped_activity<TraceProvider::CopyFileBrokerActivity>(__int64 a1)
{
  _QWORD v3[42]; // [rsp+20h] [rbp-2B8h] BYREF
  _QWORD v4[42]; // [rsp+170h] [rbp-168h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v3);
  v3[0] = &TraceProvider::CopyFileBrokerActivity::`vftable';
  TraceProvider::CopyFileBrokerActivity::StartActivity((TraceProvider::CopyFileBrokerActivity *)v3);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v4,
    v3);
  v4[0] = &TraceProvider::CopyFileBrokerActivity::`vftable';
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    v4);
  *(_QWORD *)a1 = &TraceProvider::CopyFileBrokerActivity::`vftable';
  *(_BYTE *)(a1 + 336) = 1;
  TraceProvider::CopyFileBrokerActivity::~CopyFileBrokerActivity((TraceProvider::CopyFileBrokerActivity *)v4);
  TraceProvider::CopyFileBrokerActivity::~CopyFileBrokerActivity((TraceProvider::CopyFileBrokerActivity *)v3);
  return a1;
}

```

## disassembly

```asm
0x180016760  mov     [rsp+arg_8], rbx
0x180016765  push    rdi
0x180016766  sub     rsp, 2D0h
0x18001676d  mov     rax, cs:__security_cookie
0x180016774  xor     rax, rsp
0x180016777  mov     [rsp+2D8h+var_18], rax
0x18001677f  mov     rbx, rcx
0x180016782  lea     rdx, aCopyfilebroker; "CopyFileBrokerActivity"
0x180016789  lea     rcx, [rsp+2D8h+var_2B8]; struct wil::details::IFailureCallback *
0x18001678e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016793  lea     rdi, ??_7CopyFileBrokerActivity@TraceProvider@@6B@; const TraceProvider::CopyFileBrokerActivity::`vftable'
0x18001679a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x18001679f  mov     [rsp+2D8h+var_2B8], rdi
0x1800167a4  call    ?StartActivity@CopyFileBrokerActivity@TraceProvider@@QEAAXXZ; TraceProvider::CopyFileBrokerActivity::StartActivity(void)
0x1800167a9  lea     rdx, [rsp+2D8h+var_2B8]
0x1800167ae  lea     rcx, [rsp+2D8h+var_168]
0x1800167b6  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x1800167bb  lea     rdx, [rsp+2D8h+var_168]
0x1800167c3  mov     [rsp+2D8h+var_168], rdi
0x1800167cb  mov     rcx, rbx
0x1800167ce  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x1800167d3  mov     [rbx], rdi
0x1800167d6  lea     rcx, [rsp+2D8h+var_168]; this
0x1800167de  mov     byte ptr [rbx+150h], 1
0x1800167e5  call    ??1CopyFileBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::CopyFileBrokerActivity::~CopyFileBrokerActivity(void)
0x1800167ea  lea     rcx, [rsp+2D8h+var_2B8]; this
0x1800167ef  call    ??1CopyFileBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::CopyFileBrokerActivity::~CopyFileBrokerActivity(void)
0x1800167f4  mov     rax, rbx
0x1800167f7  mov     rcx, [rsp+2D8h+var_18]
0x1800167ff  xor     rcx, rsp; StackCookie
0x180016802  call    __security_check_cookie
0x180016807  mov     rbx, [rsp+2D8h+arg_8]
0x18001680f  add     rsp, 2D0h
0x180016816  pop     rdi
0x180016817  retn
```
