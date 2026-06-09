# ??$start_scoped_activity@VReplaceFileBrokerActivity@TraceProvider@@@@YA?A_PXZ

- ea: `0x180016e20`
- end: `0x180016ed8`
- name: `??$start_scoped_activity@VReplaceFileBrokerActivity@TraceProvider@@@@YA?A_PXZ`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018990`

## callees

- `0x180002be0`
- `0x18000c680`
- `0x18000c764`
- `0x18001741c`
- `0x1800192cc`

## string_xrefs

- `0x180016e42`: `ReplaceFileBrokerActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall start_scoped_activity<TraceProvider::ReplaceFileBrokerActivity>(__int64 a1)
{
  _QWORD v3[42]; // [rsp+20h] [rbp-2B8h] BYREF
  _QWORD v4[42]; // [rsp+170h] [rbp-168h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v3);
  v3[0] = &TraceProvider::ReplaceFileBrokerActivity::`vftable';
  TraceProvider::ReplaceFileBrokerActivity::StartActivity((TraceProvider::ReplaceFileBrokerActivity *)v3);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v4,
    v3);
  v4[0] = &TraceProvider::ReplaceFileBrokerActivity::`vftable';
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    v4);
  *(_QWORD *)a1 = &TraceProvider::ReplaceFileBrokerActivity::`vftable';
  *(_BYTE *)(a1 + 336) = 1;
  TraceProvider::ReplaceFileBrokerActivity::~ReplaceFileBrokerActivity((TraceProvider::ReplaceFileBrokerActivity *)v4);
  TraceProvider::ReplaceFileBrokerActivity::~ReplaceFileBrokerActivity((TraceProvider::ReplaceFileBrokerActivity *)v3);
  return a1;
}

```

## disassembly

```asm
0x180016e20  mov     [rsp+arg_8], rbx
0x180016e25  push    rdi
0x180016e26  sub     rsp, 2D0h
0x180016e2d  mov     rax, cs:__security_cookie
0x180016e34  xor     rax, rsp
0x180016e37  mov     [rsp+2D8h+var_18], rax
0x180016e3f  mov     rbx, rcx
0x180016e42  lea     rdx, aReplacefilebro; "ReplaceFileBrokerActivity"
0x180016e49  lea     rcx, [rsp+2D8h+var_2B8]; struct wil::details::IFailureCallback *
0x180016e4e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016e53  lea     rdi, ??_7ReplaceFileBrokerActivity@TraceProvider@@6B@; const TraceProvider::ReplaceFileBrokerActivity::`vftable'
0x180016e5a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016e5f  mov     [rsp+2D8h+var_2B8], rdi
0x180016e64  call    ?StartActivity@ReplaceFileBrokerActivity@TraceProvider@@QEAAXXZ; TraceProvider::ReplaceFileBrokerActivity::StartActivity(void)
0x180016e69  lea     rdx, [rsp+2D8h+var_2B8]
0x180016e6e  lea     rcx, [rsp+2D8h+var_168]
0x180016e76  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016e7b  lea     rdx, [rsp+2D8h+var_168]
0x180016e83  mov     [rsp+2D8h+var_168], rdi
0x180016e8b  mov     rcx, rbx
0x180016e8e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016e93  mov     [rbx], rdi
0x180016e96  lea     rcx, [rsp+2D8h+var_168]; this
0x180016e9e  mov     byte ptr [rbx+150h], 1
0x180016ea5  call    ??1ReplaceFileBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::ReplaceFileBrokerActivity::~ReplaceFileBrokerActivity(void)
0x180016eaa  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016eaf  call    ??1ReplaceFileBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::ReplaceFileBrokerActivity::~ReplaceFileBrokerActivity(void)
0x180016eb4  mov     rax, rbx
0x180016eb7  mov     rcx, [rsp+2D8h+var_18]
0x180016ebf  xor     rcx, rsp; StackCookie
0x180016ec2  call    __security_check_cookie
0x180016ec7  mov     rbx, [rsp+2D8h+arg_8]
0x180016ecf  add     rsp, 2D0h
0x180016ed6  pop     rdi
0x180016ed7  retn
```
