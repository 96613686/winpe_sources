# ??$start_scoped_activity@VCreateFile2BrokerActivity@TraceProvider@@@@YA?A_PXZ

- ea: `0x1800168e0`
- end: `0x180016998`
- name: `??$start_scoped_activity@VCreateFile2BrokerActivity@TraceProvider@@@@YA?A_PXZ`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017940`

## callees

- `0x180002be0`
- `0x18000c680`
- `0x18000c764`
- `0x1800172b0`
- `0x180018e6c`

## string_xrefs

- `0x180016902`: `CreateFile2BrokerActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall start_scoped_activity<TraceProvider::CreateFile2BrokerActivity>(__int64 a1)
{
  _QWORD v3[42]; // [rsp+20h] [rbp-2B8h] BYREF
  _QWORD v4[42]; // [rsp+170h] [rbp-168h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v3);
  v3[0] = &TraceProvider::CreateFile2BrokerActivity::`vftable';
  TraceProvider::CreateFile2BrokerActivity::StartActivity((TraceProvider::CreateFile2BrokerActivity *)v3);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v4,
    v3);
  v4[0] = &TraceProvider::CreateFile2BrokerActivity::`vftable';
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    v4);
  *(_QWORD *)a1 = &TraceProvider::CreateFile2BrokerActivity::`vftable';
  *(_BYTE *)(a1 + 336) = 1;
  TraceProvider::CreateFile2BrokerActivity::~CreateFile2BrokerActivity((TraceProvider::CreateFile2BrokerActivity *)v4);
  TraceProvider::CreateFile2BrokerActivity::~CreateFile2BrokerActivity((TraceProvider::CreateFile2BrokerActivity *)v3);
  return a1;
}

```

## disassembly

```asm
0x1800168e0  mov     [rsp+arg_8], rbx
0x1800168e5  push    rdi
0x1800168e6  sub     rsp, 2D0h
0x1800168ed  mov     rax, cs:__security_cookie
0x1800168f4  xor     rax, rsp
0x1800168f7  mov     [rsp+2D8h+var_18], rax
0x1800168ff  mov     rbx, rcx
0x180016902  lea     rdx, aCreatefile2bro; "CreateFile2BrokerActivity"
0x180016909  lea     rcx, [rsp+2D8h+var_2B8]; struct wil::details::IFailureCallback *
0x18001690e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016913  lea     rdi, ??_7CreateFile2BrokerActivity@TraceProvider@@6B@; const TraceProvider::CreateFile2BrokerActivity::`vftable'
0x18001691a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x18001691f  mov     [rsp+2D8h+var_2B8], rdi
0x180016924  call    ?StartActivity@CreateFile2BrokerActivity@TraceProvider@@QEAAXXZ; TraceProvider::CreateFile2BrokerActivity::StartActivity(void)
0x180016929  lea     rdx, [rsp+2D8h+var_2B8]
0x18001692e  lea     rcx, [rsp+2D8h+var_168]
0x180016936  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x18001693b  lea     rdx, [rsp+2D8h+var_168]
0x180016943  mov     [rsp+2D8h+var_168], rdi
0x18001694b  mov     rcx, rbx
0x18001694e  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x180016953  mov     [rbx], rdi
0x180016956  lea     rcx, [rsp+2D8h+var_168]; this
0x18001695e  mov     byte ptr [rbx+150h], 1
0x180016965  call    ??1CreateFile2BrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::CreateFile2BrokerActivity::~CreateFile2BrokerActivity(void)
0x18001696a  lea     rcx, [rsp+2D8h+var_2B8]; this
0x18001696f  call    ??1CreateFile2BrokerActivity@TraceProvider@@QEAA@XZ; TraceProvider::CreateFile2BrokerActivity::~CreateFile2BrokerActivity(void)
0x180016974  mov     rax, rbx
0x180016977  mov     rcx, [rsp+2D8h+var_18]
0x18001697f  xor     rcx, rsp; StackCookie
0x180016982  call    __security_check_cookie
0x180016987  mov     rbx, [rsp+2D8h+arg_8]
0x18001698f  add     rsp, 2D0h
0x180016996  pop     rdi
0x180016997  retn
```
