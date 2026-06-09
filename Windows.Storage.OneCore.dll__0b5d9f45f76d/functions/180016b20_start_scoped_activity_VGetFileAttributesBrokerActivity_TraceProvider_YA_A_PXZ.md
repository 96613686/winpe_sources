# ??$start_scoped_activity@VGetFileAttributesBrokerActivity@TraceProvider@@@@YA?A_PXZ

- ea: `0x180016b20`
- end: `0x180016bd8`
- name: `??$start_scoped_activity@VGetFileAttributesBrokerActivity@TraceProvider@@@@YA?A_PXZ`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800180b0`

## callees

- `0x180002be0`
- `0x18000c680`
- `0x18000c764`
- `0x180017334`
- `0x18001904c`

## string_xrefs

- `0x180016b42`: `GetFileAttributesBrokerActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall start_scoped_activity<TraceProvider::GetFileAttributesBrokerActivity>(__int64 a1)
{
  _QWORD v3[42]; // [rsp+20h] [rbp-2B8h] BYREF
  _QWORD v4[42]; // [rsp+170h] [rbp-168h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v3);
  v3[0] = &TraceProvider::GetFileAttributesBrokerActivity::`vftable';
  TraceProvider::GetFileAttributesBrokerActivity::StartActivity((TraceProvider::GetFileAttributesBrokerActivity *)v3);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v4,
    v3);
  v4[0] = &TraceProvider::GetFileAttributesBrokerActivity::`vftable';
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    v4);
  *(_QWORD *)a1 = &TraceProvider::GetFileAttributesBrokerActivity::`vftable';
  *(_BYTE *)(a1 + 336) = 1;
  TraceProvider::GetFileAttributesBrokerActivity::~GetFileAttributesBrokerActivity((TraceProvider::GetFileAttributesBrokerActivity *)v4);
  TraceProvider::GetFileAttributesBrokerActivity::~GetFileAttributesBrokerActivity((TraceProvider::GetFileAttributesBrokerActivity *)v3);
  return a1;
}

```

## disassembly

```asm
0x180016b20  mov     [rsp+arg_8], rbx
0x180016b25  push    rdi
0x180016b26  sub     rsp, 2D0h
0x180016b2d  mov     rax, cs:__security_cookie
0x180016b34  xor     rax, rsp
0x180016b37  mov     [rsp+2D8h+var_18], rax
0x180016b3f  mov     rbx, rcx
0x180016b42  lea     rdx, aGetfileattribu_3; "GetFileAttributesBrokerActivity"
0x180016b49  lea     rcx, [rsp+2D8h+var_2B8]; struct wil::details::IFailureCallback *
0x180016b4e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016b53  lea     rdi, ??_7GetFileAttributesBrokerActivity@TraceProvider@@6B@; const TraceProvider::GetFileAttributesBrokerActivity::`vftable'
0x180016b5a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016b5f  mov     [rsp+2D8h+var_2B8], rdi
0x180016b64  call    ?StartActivity@GetFileAttributesBrokerActivity@TraceProvider@@QEAAXXZ; TraceProvider::GetFileAttributesBrokerActivity::StartActivity(void)
0x180016b69  lea     rdx, [rsp+2D8h+var_2B8]
0x180016b6e  lea     rcx, [rsp+2D8h+var_168]
0x180016b76  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016b7b  lea     rdx, [rsp+2D8h+var_168]
0x180016b83  mov     [rsp+2D8h+var_168], rdi
0x180016b8b  mov     rcx, rbx
0x180016b8e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016b93  mov     [rbx], rdi
0x180016b96  lea     rcx, [rsp+2D8h+var_168]; this
0x180016b9e  mov     byte ptr [rbx+150h], 1
0x180016ba5  call    ??1GetFileAttributesBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::GetFileAttributesBrokerActivity::~GetFileAttributesBrokerActivity(void)
0x180016baa  lea     rcx, [rsp+2D8h+var_2B8]; this
0x180016baf  call    ??1GetFileAttributesBrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::GetFileAttributesBrokerActivity::~GetFileAttributesBrokerActivity(void)
0x180016bb4  mov     rax, rbx
0x180016bb7  mov     rcx, [rsp+2D8h+var_18]
0x180016bbf  xor     rcx, rsp; StackCookie
0x180016bc2  call    __security_check_cookie
0x180016bc7  mov     rbx, [rsp+2D8h+arg_8]
0x180016bcf  add     rsp, 2D0h
0x180016bd6  pop     rdi
0x180016bd7  retn
```
