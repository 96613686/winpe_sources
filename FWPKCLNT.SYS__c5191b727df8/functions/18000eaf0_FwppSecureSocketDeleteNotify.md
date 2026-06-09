# FwppSecureSocketDeleteNotify

- ea: `0x18000eaf0`
- end: `0x18000eb88`
- name: `FwppSecureSocketDeleteNotify`
- size: `152`
- prototype: `unsigned __int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180004904`
- `0x180008480`
- `0x180008f10`
- `0x18000dfac`
- `0x18000eaf0`
- `0x1800203c0`
- `0x180020400`

## import_xrefs

- `msrpc!RpcAsyncCompleteCall` at `0x18000eb1a`
- `msrpc!RpcAsyncCompleteCall` at `0x18000eb1a`

## string_xrefs

- `0x18000eb2d`: `RpcAsyncCompleteCall`
- `0x18000eb47`: `FwppProxySecureSocketDelete`

## pseudocode

```c
unsigned __int64 __fastcall FwppSecureSocketDeleteNotify(__int64 a1)
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
      v4 = WfpReportSysErrorAsNtStatus(v3, (int)"FwppProxySecureSocketDelete", Reply);
  }
  v5 = WfpErrorToFwpErr(v4);
  (*(void (__fastcall **)(_QWORD, _QWORD))(a1 + 88))(*(_QWORD *)(a1 + 96), v5);
  return WfpNamedPoolFree(v6, &v8);
}

```

## disassembly

```asm
0x18000eaf0  push    rbx
0x18000eaf2  sub     rsp, 40h
0x18000eaf6  mov     rax, cs:__security_cookie
0x18000eafd  xor     rax, rsp
0x18000eb00  mov     [rsp+48h+var_18], rax
0x18000eb05  lea     rdx, [rsp+48h+Reply]; Reply
0x18000eb0a  mov     [rsp+48h+var_28], rcx
0x18000eb0f  mov     rbx, rcx
0x18000eb12  mov     [rsp+48h+Reply], 0
0x18000eb1a  call    cs:__imp_RpcAsyncCompleteCall
0x18000eb21  nop     dword ptr [rax+rax+00h]
0x18000eb26  test    eax, eax
0x18000eb28  jz      short loc_18000EB3B
0x18000eb2a  mov     r8d, eax
0x18000eb2d  lea     rdx, aRpcasynccomple; "RpcAsyncCompleteCall"
0x18000eb34  call    WfpReportSysErrorAsRpcStatus
0x18000eb39  jmp     short loc_18000EB53
0x18000eb3b  mov     r8d, [rsp+48h+Reply]
0x18000eb40  xor     eax, eax
0x18000eb42  test    r8d, r8d
0x18000eb45  jns     short loc_18000EB53
0x18000eb47  lea     rdx, aFwppproxysecur_0; "FwppProxySecureSocketDelete"
0x18000eb4e  call    WfpReportSysErrorAsNtStatus
0x18000eb53  mov     rcx, rax
0x18000eb56  call    WfpErrorToFwpErr
0x18000eb5b  mov     rcx, [rbx+60h]
0x18000eb5f  mov     edx, eax
0x18000eb61  mov     rax, [rbx+58h]
0x18000eb65  call    _guard_dispatch_icall
0x18000eb6a  lea     rdx, [rsp+48h+var_28]
0x18000eb6f  call    WfpNamedPoolFree
0x18000eb74  mov     rcx, [rsp+48h+var_18]
0x18000eb79  xor     rcx, rsp; StackCookie
0x18000eb7c  call    __security_check_cookie
0x18000eb81  add     rsp, 40h
0x18000eb85  pop     rbx
0x18000eb86  retn
```
