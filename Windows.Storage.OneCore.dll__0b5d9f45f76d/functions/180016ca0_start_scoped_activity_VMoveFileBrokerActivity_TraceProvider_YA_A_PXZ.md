# ??$start_scoped_activity@VMoveFileBrokerActivity@TraceProvider@@@@YA?A_PXZ

- ea: `0x180016ca0`
- end: `0x180016d58`
- name: `??$start_scoped_activity@VMoveFileBrokerActivity@TraceProvider@@@@YA?A_PXZ`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018440`

## callees

- `0x180002be0`
- `0x18000c680`
- `0x18000c764`
- `0x1800173c4`
- `0x18001918c`

## string_xrefs

- `0x180016cc2`: `MoveFileBrokerActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall start_scoped_activity<TraceProvider::MoveFileBrokerActivity>(__int64 a1)
{
  _QWORD v3[42]; // [rsp+20h] [rbp-2B8h] BYREF
  _QWORD v4[42]; // [rsp+170h] [rbp-168h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v3);
  v3[0] = &TraceProvider::MoveFileBrokerActivity::`vftable';
  TraceProvider::MoveFileBrokerActivity::StartActivity((TraceProvider::MoveFileBrokerActivity *)v3);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v4,
    v3);
  v4[0] = &TraceProvider::MoveFileBrokerActivity::`vftable';
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    v4);
  *(_QWORD *)a1 = &TraceProvider::MoveFileBrokerActivity::`vftable';
  *(_BYTE *)(a1 + 336) = 1;
  TraceProvider::MoveFileBrokerActivity::~MoveFileBrokerActivity((TraceProvider::MoveFileBrokerActivity *)v4);
  TraceProvider::MoveFileBrokerActivity::~MoveFileBrokerActivity((TraceProvider::MoveFileBrokerActivity *)v3);
  return a1;
}

```

## disassembly

```asm
0x180016ca0  mov     [rsp+arg_8], rbx
0x180016ca5  push    rdi
0x180016ca6  sub     rsp, 2D0h
0x180016cad  mov     rax, cs:__security_cookie
0x180016cb4  xor     rax, rsp
0x180016cb7  mov     [rsp+2D8h+var_18], rax
0x180016cbf  mov     rbx, rcx
0x180016cc2  lea     rdx, aMovefilebroker; "MoveFileBrokerActivity"
0x180016cc9  lea     rcx, [rsp+2D8h+var_2B8]; struct wil::details::IFailureCallback *
0x180016cce  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016cd3  lea     rdi, ??_7MoveFileBrokerActivity@TraceProvider@@6B@; const TraceProvider::MoveFileBrokerActivity::`vftable'
0x180016cda  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016cdf  mov     [rsp+2D8h+var_2B8], rdi
0x180016ce4  call    ?StartActivity@MoveFileBrokerActivity@TraceProvider@@QEAAXXZ; TraceProvider::MoveFileBrokerActivity::StartActivity(void)
0x180016ce9  lea     rdx, [rsp+2D8h+var_2B8]
0x180016cee  lea     rcx, [rsp+2D8h+var_168]
0x180016cf6  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016cfb  lea     rdx, [rsp+2D8h+var_168]
0x180016d03  mov     [rsp+2D8h+var_168], rdi
0x180016d0b  mov     rcx, rbx
0x180016d0e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016d13  mov     [rbx], rdi
0x180016d16  lea     rcx, [rsp+2D8h+var_168]; this
0x180016d1e  mov     byte ptr [rbx+150h], 1
0x180016d25  call    ??1MoveFileBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::MoveFileBrokerActivity::~MoveFileBrokerActivity(void)
0x180016d2a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016d2f  call    ??1MoveFileBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::MoveFileBrokerActivity::~MoveFileBrokerActivity(void)
0x180016d34  mov     rax, rbx
0x180016d37  mov     rcx, [rsp+2D8h+var_18]
0x180016d3f  xor     rcx, rsp; StackCookie
0x180016d42  call    __security_check_cookie
0x180016d47  mov     rbx, [rsp+2D8h+arg_8]
0x180016d4f  add     rsp, 2D0h
0x180016d56  pop     rdi
0x180016d57  retn
```
