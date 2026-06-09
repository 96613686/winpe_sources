# WcmKGetInterfaceForNetworkRequest(void *,_WCM_ROUTE_POLICY_NETWORK_REQUEST const &,_NET_LUID_LH *,void * *)

- ea: `0x14000a2d8`
- end: `0x14000a472`
- name: `?WcmKGetInterfaceForNetworkRequest@@YAKPEAXAEBU_WCM_ROUTE_POLICY_NETWORK_REQUEST@@PEAT_NET_LUID_LH@@PEAPEAX@Z`
- size: `410`
- prototype: `unsigned int __fastcall(void *, const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *, union _NET_LUID_LH *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006cc4`

## callees

- `0x14000a1c4`
- `0x14000a214`
- `0x14000a2d8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000a384`
- `ntoskrnl!KeInitializeEvent` at `0x14000a384`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a410`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a410`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a365`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a365`
- `ntoskrnl!ExAllocatePool2` at `0x14000a325`
- `ntoskrnl!ExAllocatePool2` at `0x14000a325`
- `msrpc!RpcAsyncInitializeHandle` at `0x14000a34b`
- `msrpc!RpcAsyncInitializeHandle` at `0x14000a34b`
- `msrpc!RpcAsyncCancelCall` at `0x14000a3f3`
- `msrpc!RpcAsyncCancelCall` at `0x14000a3f3`
- `msrpc!RpcAsyncCompleteCall` at `0x14000a440`
- `msrpc!RpcAsyncCompleteCall` at `0x14000a440`

## pseudocode

```c
__int64 __fastcall WcmKGetInterfaceForNetworkRequest(
        void *a1,
        const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *a2,
        union _NET_LUID_LH *a3,
        void **a4)
{
  int v5; // r15d
  int v6; // esi
  int v7; // ebp
  struct _RPC_ASYNC_STATE *Pool2; // rax
  struct _RPC_ASYNC_STATE *v9; // rbx
  unsigned int v10; // edi
  unsigned int InterfaceForNetworkRequest; // eax
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  NTSTATUS v15; // eax
  int v16; // eax
  unsigned int Reply; // [rsp+68h] [rbp+10h] BYREF
  struct _RPC_ASYNC_STATE *v18; // [rsp+70h] [rbp+18h] BYREF

  a3->Value = 0;
  v5 = (int)a3;
  *a4 = 0;
  v6 = (int)a2;
  v7 = (int)a1;
  if ( !*((_WORD *)a2 + 20) || !*(_DWORD *)a2 )
    return 87;
  Pool2 = (struct _RPC_ASYNC_STATE *)ExAllocatePool2(64, 112, 1684435058);
  v18 = Pool2;
  v9 = Pool2;
  if ( Pool2 )
  {
    v10 = RpcAsyncInitializeHandle(Pool2, 0x58u);
    if ( !v10 )
    {
      KeInitializeEvent((PRKEVENT)&v9[1], NotificationEvent, 0);
      v9->u.Event = (PKEVENT)&v9[1];
      v9->NotificationType = RpcNotificationTypeEvent;
      InterfaceForNetworkRequest = StartRpcGetInterfaceForNetworkRequest((_DWORD)v9, v7, v6, v5, (__int64)a4);
      v10 = InterfaceForNetworkRequest;
      if ( InterfaceForNetworkRequest )
      {
        v13 = InterfaceForNetworkRequest + 1073610749;
        if ( (unsigned int)v13 <= 0x33 )
        {
          v14 = 0x8000001008001LL;
          if ( _bittest64(&v14, v13) )
            v10 = 1062;
        }
      }
      else if ( AsyncHelper::WaitInternal((AsyncHelper *)&v18, 0x493E0u) )
      {
        Reply = 0;
        RpcAsyncCompleteCall(v9, &Reply);
        v10 = Reply;
      }
      else
      {
        RpcAsyncCancelCall(v9, 1);
        while ( 1 )
        {
          v15 = KeWaitForSingleObject(&v9[1], Executive, 0, 1u, 0);
          if ( !v15 )
            break;
          v16 = v15 - 192;
          if ( v16 )
          {
            if ( v16 != 65 )
              break;
          }
        }
        v10 = 1460;
      }
    }
    ExFreePoolWithTag(v9, 0x64667072u);
  }
  else
  {
    return 8;
  }
  return v10;
}

```

## disassembly

```asm
0x14000a2d8  mov     [rsp+arg_0], rbx
0x14000a2dd  mov     [rsp+arg_18], rbp
0x14000a2e2  push    rsi
0x14000a2e3  push    rdi
0x14000a2e4  push    r12
0x14000a2e6  push    r14
0x14000a2e8  push    r15
0x14000a2ea  sub     rsp, 30h
0x14000a2ee  xor     r12d, r12d
0x14000a2f1  mov     r14, r9
0x14000a2f4  mov     [r8], r12
0x14000a2f7  mov     r15, r8
0x14000a2fa  mov     [r9], r12
0x14000a2fd  mov     rsi, rdx
0x14000a300  mov     rbp, rcx
0x14000a303  cmp     [rdx+28h], r12w
0x14000a308  jz      loc_14000A455
0x14000a30e  cmp     [rdx], r12d
0x14000a311  jz      loc_14000A455
0x14000a317  lea     edx, [r12+70h]
0x14000a31c  mov     r8d, 64667072h
0x14000a322  lea     ecx, [rdx-30h]
0x14000a325  call    cs:__imp_ExAllocatePool2
0x14000a32c  nop     dword ptr [rax+rax+00h]
0x14000a331  mov     [rsp+58h+arg_10], rax
0x14000a336  mov     rbx, rax
0x14000a339  test    rax, rax
0x14000a33c  jnz     short loc_14000A343
0x14000a33e  lea     edi, [rax+8]
0x14000a341  jmp     short loc_14000A371
0x14000a343  mov     edx, 58h ; 'X'; Size
0x14000a348  mov     rcx, rbx; pAsync
0x14000a34b  call    cs:__imp_RpcAsyncInitializeHandle
0x14000a352  nop     dword ptr [rax+rax+00h]
0x14000a357  mov     edi, eax
0x14000a359  test    eax, eax
0x14000a35b  jz      short loc_14000A378
0x14000a35d  mov     edx, 64667072h; Tag
0x14000a362  mov     rcx, rbx; P
0x14000a365  call    cs:__imp_ExFreePoolWithTag
0x14000a36c  nop     dword ptr [rax+rax+00h]
0x14000a371  mov     eax, edi
0x14000a373  jmp     loc_14000A45A
0x14000a378  lea     rdi, [rbx+58h]
0x14000a37c  xor     r8d, r8d; State
0x14000a37f  mov     rcx, rdi; Event
0x14000a382  xor     edx, edx; Type
0x14000a384  call    cs:__imp_KeInitializeEvent
0x14000a38b  nop     dword ptr [rax+rax+00h]
0x14000a390  mov     [rbx+30h], rdi
0x14000a394  mov     r9, r15
0x14000a397  mov     r8, rsi
0x14000a39a  mov     dword ptr [rbx+2Ch], 1
0x14000a3a1  mov     rdx, rbp
0x14000a3a4  mov     [rsp+58h+Timeout], r14
0x14000a3a9  mov     rcx, rbx
0x14000a3ac  call    StartRpcGetInterfaceForNetworkRequest
0x14000a3b1  mov     edi, eax
0x14000a3b3  test    eax, eax
0x14000a3b5  jz      short loc_14000A3D8
0x14000a3b7  add     eax, 3FFDFFFDh
0x14000a3bc  cmp     eax, 33h ; '3'
0x14000a3bf  ja      short loc_14000A35D
0x14000a3c1  mov     rcx, 8000001008001h
0x14000a3cb  bt      rcx, rax
0x14000a3cf  jnb     short loc_14000A35D
0x14000a3d1  mov     edi, 426h
0x14000a3d6  jmp     short loc_14000A35D
0x14000a3d8  mov     edx, 493E0h; unsigned int
0x14000a3dd  lea     rcx, [rsp+58h+arg_10]; this
0x14000a3e2  call    ?WaitInternal@AsyncHelper@@AEBA_NK@Z; AsyncHelper::WaitInternal(ulong)
0x14000a3e7  mov     rcx, rbx; pAsync
0x14000a3ea  test    al, al
0x14000a3ec  jnz     short loc_14000A436
0x14000a3ee  mov     edx, 1; fAbort
0x14000a3f3  call    cs:__imp_RpcAsyncCancelCall
0x14000a3fa  nop     dword ptr [rax+rax+00h]
0x14000a3ff  lea     rcx, [rbx+58h]; Object
0x14000a403  mov     [rsp+58h+Timeout], r12; Timeout
0x14000a408  mov     r9b, 1; Alertable
0x14000a40b  xor     r8d, r8d; WaitMode
0x14000a40e  xor     edx, edx; WaitReason
0x14000a410  call    cs:__imp_KeWaitForSingleObject
0x14000a417  nop     dword ptr [rax+rax+00h]
0x14000a41c  test    eax, eax
0x14000a41e  jz      short loc_14000A42C
0x14000a420  sub     eax, 0C0h
0x14000a425  jz      short loc_14000A3FF
0x14000a427  cmp     eax, 41h ; 'A'
0x14000a42a  jz      short loc_14000A3FF
0x14000a42c  mov     edi, 5B4h
0x14000a431  jmp     loc_14000A35D
0x14000a436  lea     rdx, [rsp+58h+Reply]; Reply
0x14000a43b  mov     [rsp+58h+Reply], r12d
0x14000a440  call    cs:__imp_RpcAsyncCompleteCall
0x14000a447  nop     dword ptr [rax+rax+00h]
0x14000a44c  mov     edi, [rsp+58h+Reply]
0x14000a450  jmp     loc_14000A35D
0x14000a455  mov     eax, 57h ; 'W'
0x14000a45a  mov     rbx, [rsp+58h+arg_0]
0x14000a45f  mov     rbp, [rsp+58h+arg_18]
0x14000a464  add     rsp, 30h
0x14000a468  pop     r15
0x14000a46a  pop     r14
0x14000a46c  pop     r12
0x14000a46e  pop     rdi
0x14000a46f  pop     rsi
0x14000a470  retn
```
