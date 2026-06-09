# FwppSecureSocketAddNotify

- ea: `0x18000ea40`
- end: `0x18000eae5`
- name: `FwppSecureSocketAddNotify`
- size: `165`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004904`
- `0x180008440`
- `0x180008480`
- `0x180008f10`
- `0x18000dfac`
- `0x18000ea40`
- `0x1800203c0`
- `0x180020400`

## import_xrefs

- `msrpc!RpcAsyncCompleteCall` at `0x18000ea6a`
- `msrpc!RpcAsyncCompleteCall` at `0x18000ea6a`

## string_xrefs

- `0x18000ea7d`: `RpcAsyncCompleteCall`

## pseudocode

```c
unsigned __int64 __fastcall FwppSecureSocketAddNotify(__int64 a1)
{
  RPC_STATUS v2; // eax
  __int64 v3; // rcx
  __int64 v4; // rax
  unsigned int v5; // eax
  __int64 v6; // rcx
  PVOID v8; // [rsp+20h] [rbp-28h] BYREF
  int Reply; // [rsp+28h] [rbp-20h] BYREF

  v8 = (PVOID)a1;
  Reply = 0;
  v2 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)a1, &Reply);
  if ( v2 )
  {
    v4 = WfpReportSysErrorAsRpcStatus(v3, (int)"RpcAsyncCompleteCall", v2);
  }
  else
  {
    v4 = 0;
    if ( Reply < 0 )
      v4 = WfpReportSysErrorAsNtStatus(v3, (int)"FwppProxySecureSocketAdd", Reply);
  }
  v5 = WfpErrorToFwpErr(v4);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 88))(*(_QWORD *)(a1 + 96), v5, *(_QWORD *)(a1 + 104));
  FwppDeepFree_GUID(*(void **)(a1 + 104));
  return WfpNamedPoolFree(v6, &v8);
}

```

## disassembly

```asm
0x18000ea40  push    rbx
0x18000ea42  sub     rsp, 40h
0x18000ea46  mov     rax, cs:__security_cookie
0x18000ea4d  xor     rax, rsp
0x18000ea50  mov     [rsp+48h+var_18], rax
0x18000ea55  lea     rdx, [rsp+48h+Reply]; Reply
0x18000ea5a  mov     [rsp+48h+var_28], rcx
0x18000ea5f  mov     rbx, rcx
0x18000ea62  mov     [rsp+48h+Reply], 0
0x18000ea6a  call    cs:__imp_RpcAsyncCompleteCall
0x18000ea71  nop     dword ptr [rax+rax+00h]
0x18000ea76  test    eax, eax
0x18000ea78  jz      short loc_18000EA8B
0x18000ea7a  mov     r8d, eax
0x18000ea7d  lea     rdx, aRpcasynccomple; "RpcAsyncCompleteCall"
0x18000ea84  call    WfpReportSysErrorAsRpcStatus
0x18000ea89  jmp     short loc_18000EAA3
0x18000ea8b  mov     r8d, [rsp+48h+Reply]
0x18000ea90  xor     eax, eax
0x18000ea92  test    r8d, r8d
0x18000ea95  jns     short loc_18000EAA3
0x18000ea97  lea     rdx, aFwppproxysecur_1; "FwppProxySecureSocketAdd"
0x18000ea9e  call    WfpReportSysErrorAsNtStatus
0x18000eaa3  mov     rcx, rax
0x18000eaa6  call    WfpErrorToFwpErr
0x18000eaab  mov     r8, [rbx+68h]
0x18000eaaf  mov     edx, eax
0x18000eab1  mov     rax, [rbx+58h]
0x18000eab5  mov     rcx, [rbx+60h]
0x18000eab9  call    _guard_dispatch_icall
0x18000eabe  mov     rcx, [rbx+68h]
0x18000eac2  call    FwppDeepFree_GUID
0x18000eac7  lea     rdx, [rsp+48h+var_28]
0x18000eacc  call    WfpNamedPoolFree
0x18000ead1  mov     rcx, [rsp+48h+var_18]
0x18000ead6  xor     rcx, rsp; StackCookie
0x18000ead9  call    __security_check_cookie
0x18000eade  add     rsp, 40h
0x18000eae2  pop     rbx
0x18000eae3  retn
```
