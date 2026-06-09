# Int_NetworkIsolationAsyncOpCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18001d830`
- end: `0x18001da0b`
- name: `?Int_NetworkIsolationAsyncOpCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `475`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18001d830`
- `0x180026c9c`
- `0x1800294b0`
- `0x180062010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18001d862`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001d862`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d8e8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d90e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d8e8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d90e`
- `fwbase!FwBaseFree` at `0x18001d8c5`
- `fwbase!FwBaseFree` at `0x18001d8c5`

## pseudocode

```c
void __fastcall Int_NetworkIsolationAsyncOpCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  RPC_STATUS v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r8
  void *v10; // rcx
  void *v11; // rcx
  FwPolicy2 *v12; // rcx
  __int64 v13; // rdx
  unsigned int Reply; // [rsp+20h] [rbp-18h] BYREF

  Reply = 0;
  if ( !Context )
  {
    v9 = 87;
    Reply = 87;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_26:
      (*((void (__fastcall **)(_QWORD, _QWORD, __int64, __int64))Context + 16))(
        *((_QWORD *)Context + 17),
        0,
        v9,
        WaitResult);
      *((_DWORD *)Context + 30) = Reply;
      goto LABEL_9;
    }
    v13 = 533;
    goto LABEL_24;
  }
  v5 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(Context + 8), &Reply);
  *((_DWORD *)Context + 30) = v5;
  if ( v5 == 997 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6, v8);
  _InterlockedExchange((volatile __int32 *)Context + 45, 0);
  v9 = Reply;
  if ( Reply )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    v13 = 534;
LABEL_24:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, (unsigned int)v9);
    v9 = Reply;
    goto LABEL_25;
  }
  v9 = *((unsigned int *)Context + 30);
  Reply = v9;
  if ( (_DWORD)v9 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    v13 = 535;
    goto LABEL_24;
  }
  (*((void (__fastcall **)(_QWORD, _QWORD))Context + 16))(*((_QWORD *)Context + 17), *((_QWORD *)Context + 21));
  FwBaseFree(*((_QWORD *)Context + 21));
  v10 = (void *)*((_QWORD *)Context + 23);
  *((_QWORD *)Context + 21) = 0;
  if ( v10 )
    SetEvent(v10);
  v9 = Reply;
  if ( Reply )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 536;
      goto LABEL_24;
    }
LABEL_25:
    if ( !(_DWORD)v9 )
      goto LABEL_9;
    goto LABEL_26;
  }
LABEL_9:
  v11 = (void *)*((_QWORD *)Context + 23);
  if ( v11 )
    SetEvent(v11);
}

```

## disassembly

```asm
0x18001d830  push    rbx
0x18001d832  sub     rsp, 30h
0x18001d836  mov     rax, cs:__security_cookie
0x18001d83d  xor     rax, rsp
0x18001d840  mov     [rsp+38h+var_10], rax
0x18001d845  mov     [rsp+38h+Reply], 0
0x18001d84d  mov     rbx, rdx
0x18001d850  test    rdx, rdx
0x18001d853  jz      loc_18001D92E
0x18001d859  lea     rcx, [rdx+8]; pAsync
0x18001d85d  lea     rdx, [rsp+38h+Reply]; Reply
0x18001d862  call    cs:__imp_RpcAsyncCompleteCall
0x18001d869  nop     dword ptr [rax+rax+00h]
0x18001d86e  mov     [rbx+78h], eax
0x18001d871  cmp     eax, 3E5h
0x18001d876  jz      loc_18001D961
0x18001d87c  xor     eax, eax
0x18001d87e  xchg    eax, [rbx+0B4h]
0x18001d884  mov     r8d, [rsp+38h+Reply]
0x18001d889  test    r8d, r8d
0x18001d88c  jnz     loc_18001D96B
0x18001d892  mov     r8d, [rbx+78h]
0x18001d896  mov     [rsp+38h+Reply], r8d
0x18001d89b  test    r8d, r8d
0x18001d89e  jnz     loc_18001D98B
0x18001d8a4  mov     rdx, [rbx+0A8h]
0x18001d8ab  mov     rcx, [rbx+88h]
0x18001d8b2  mov     rax, [rbx+80h]
0x18001d8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8be  mov     rcx, [rbx+0A8h]
0x18001d8c5  call    cs:__imp_FwBaseFree
0x18001d8cc  nop     dword ptr [rax+rax+00h]
0x18001d8d1  mov     rcx, [rbx+0B8h]; hEvent
0x18001d8d8  mov     qword ptr [rbx+0A8h], 0
0x18001d8e3  test    rcx, rcx
0x18001d8e6  jz      short loc_18001D8F4
0x18001d8e8  call    cs:__imp_SetEvent
0x18001d8ef  nop     dword ptr [rax+rax+00h]
0x18001d8f4  mov     r8d, [rsp+38h+Reply]
0x18001d8f9  test    r8d, r8d
0x18001d8fc  jnz     loc_18001D9AB
0x18001d902  mov     rcx, [rbx+0B8h]; hEvent
0x18001d909  test    rcx, rcx
0x18001d90c  jz      short loc_18001D91A
0x18001d90e  call    cs:__imp_SetEvent
0x18001d915  nop     dword ptr [rax+rax+00h]
0x18001d91a  mov     rcx, [rsp+38h+var_10]
0x18001d91f  xor     rcx, rsp; StackCookie
0x18001d922  call    __security_check_cookie
0x18001d927  add     rsp, 30h
0x18001d92b  pop     rbx
0x18001d92c  retn
0x18001d92e  mov     r8d, 57h ; 'W'
0x18001d934  mov     [rsp+38h+Reply], r8d
0x18001d939  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d940  lea     rax, WPP_GLOBAL_Control
0x18001d947  cmp     rcx, rax
0x18001d94a  jz      loc_18001D9EA
0x18001d950  test    byte ptr [rcx+1Ch], 1
0x18001d954  jz      loc_18001D9EA
0x18001d95a  mov     edx, 215h
0x18001d95f  jmp     short loc_18001D9C9
0x18001d961  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "phClntSubscription->Status != RPC_S_ASYNC_CALL_PENDING")
0x18001d966  jmp     loc_18001D87C
0x18001d96b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d972  lea     rax, WPP_GLOBAL_Control
0x18001d979  cmp     rcx, rax
0x18001d97c  jz      short loc_18001D9E1
0x18001d97e  test    byte ptr [rcx+1Ch], 1
0x18001d982  jz      short loc_18001D9E1
0x18001d984  mov     edx, 216h
0x18001d989  jmp     short loc_18001D9C9
0x18001d98b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d992  lea     rax, WPP_GLOBAL_Control
0x18001d999  cmp     rcx, rax
0x18001d99c  jz      short loc_18001D9E1
0x18001d99e  test    byte ptr [rcx+1Ch], 1
0x18001d9a2  jz      short loc_18001D9E1
0x18001d9a4  mov     edx, 217h
0x18001d9a9  jmp     short loc_18001D9C9
0x18001d9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9b2  lea     rax, WPP_GLOBAL_Control
0x18001d9b9  cmp     rcx, rax
0x18001d9bc  jz      short loc_18001D9E1
0x18001d9be  test    byte ptr [rcx+1Ch], 1
0x18001d9c2  jz      short loc_18001D9E1
0x18001d9c4  mov     edx, 218h
0x18001d9c9  mov     rcx, [rcx+10h]
0x18001d9cd  mov     r9d, r8d
0x18001d9d0  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18001d9d7  call    WPP_SF_d
0x18001d9dc  mov     r8d, [rsp+38h+Reply]
0x18001d9e1  test    r8d, r8d
0x18001d9e4  jz      loc_18001D902
0x18001d9ea  mov     rcx, [rbx+88h]
0x18001d9f1  xor     edx, edx
0x18001d9f3  mov     rax, [rbx+80h]
0x18001d9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9ff  mov     eax, [rsp+38h+Reply]
0x18001da03  mov     [rbx+78h], eax
0x18001da06  jmp     loc_18001D902
```
