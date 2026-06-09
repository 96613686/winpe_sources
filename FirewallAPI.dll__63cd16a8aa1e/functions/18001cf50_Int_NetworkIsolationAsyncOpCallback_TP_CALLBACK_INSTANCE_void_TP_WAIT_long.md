# Int_NetworkIsolationAsyncOpCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18001cf50`
- end: `0x18001d112`
- name: `?Int_NetworkIsolationAsyncOpCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `450`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005954`
- `0x18001cf50`
- `0x18002514c`
- `0x1800277b0`
- `0x18005e010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18001cf82`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001cf82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001cffc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d01c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001cffc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d01c`
- `fwbase!FwBaseFree` at `0x18001cfdf`
- `fwbase!FwBaseFree` at `0x18001cfdf`

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
    v13 = 534;
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
    v13 = 535;
LABEL_24:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, (unsigned int)v9);
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
    v13 = 536;
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
      v13 = 537;
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
0x18001cf50  push    rbx
0x18001cf52  sub     rsp, 30h
0x18001cf56  mov     rax, cs:__security_cookie
0x18001cf5d  xor     rax, rsp
0x18001cf60  mov     [rsp+38h+var_10], rax
0x18001cf65  mov     [rsp+38h+Reply], 0
0x18001cf6d  mov     rbx, rdx
0x18001cf70  test    rdx, rdx
0x18001cf73  jz      loc_18001D035
0x18001cf79  lea     rcx, [rdx+8]; pAsync
0x18001cf7d  lea     rdx, [rsp+38h+Reply]; Reply
0x18001cf82  call    cs:__imp_RpcAsyncCompleteCall
0x18001cf88  mov     [rbx+78h], eax
0x18001cf8b  cmp     eax, 3E5h
0x18001cf90  jz      loc_18001D068
0x18001cf96  xor     eax, eax
0x18001cf98  xchg    eax, [rbx+0B4h]
0x18001cf9e  mov     r8d, [rsp+38h+Reply]
0x18001cfa3  test    r8d, r8d
0x18001cfa6  jnz     loc_18001D072
0x18001cfac  mov     r8d, [rbx+78h]
0x18001cfb0  mov     [rsp+38h+Reply], r8d
0x18001cfb5  test    r8d, r8d
0x18001cfb8  jnz     loc_18001D092
0x18001cfbe  mov     rdx, [rbx+0A8h]
0x18001cfc5  mov     rcx, [rbx+88h]
0x18001cfcc  mov     rax, [rbx+80h]
0x18001cfd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfd8  mov     rcx, [rbx+0A8h]
0x18001cfdf  call    cs:__imp_FwBaseFree
0x18001cfe5  mov     rcx, [rbx+0B8h]; hEvent
0x18001cfec  mov     qword ptr [rbx+0A8h], 0
0x18001cff7  test    rcx, rcx
0x18001cffa  jz      short loc_18001D002
0x18001cffc  call    cs:__imp_SetEvent
0x18001d002  mov     r8d, [rsp+38h+Reply]
0x18001d007  test    r8d, r8d
0x18001d00a  jnz     loc_18001D0B2
0x18001d010  mov     rcx, [rbx+0B8h]; hEvent
0x18001d017  test    rcx, rcx
0x18001d01a  jz      short loc_18001D022
0x18001d01c  call    cs:__imp_SetEvent
0x18001d022  mov     rcx, [rsp+38h+var_10]
0x18001d027  xor     rcx, rsp; StackCookie
0x18001d02a  call    __security_check_cookie
0x18001d02f  add     rsp, 30h
0x18001d033  pop     rbx
0x18001d034  retn
0x18001d035  mov     r8d, 57h ; 'W'
0x18001d03b  mov     [rsp+38h+Reply], r8d
0x18001d040  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d047  lea     rax, WPP_GLOBAL_Control
0x18001d04e  cmp     rcx, rax
0x18001d051  jz      loc_18001D0F1
0x18001d057  test    byte ptr [rcx+1Ch], 1
0x18001d05b  jz      loc_18001D0F1
0x18001d061  mov     edx, 216h
0x18001d066  jmp     short loc_18001D0D0
0x18001d068  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d06d  jmp     loc_18001CF96
0x18001d072  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d079  lea     rax, WPP_GLOBAL_Control
0x18001d080  cmp     rcx, rax
0x18001d083  jz      short loc_18001D0E8
0x18001d085  test    byte ptr [rcx+1Ch], 1
0x18001d089  jz      short loc_18001D0E8
0x18001d08b  mov     edx, 217h
0x18001d090  jmp     short loc_18001D0D0
0x18001d092  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d099  lea     rax, WPP_GLOBAL_Control
0x18001d0a0  cmp     rcx, rax
0x18001d0a3  jz      short loc_18001D0E8
0x18001d0a5  test    byte ptr [rcx+1Ch], 1
0x18001d0a9  jz      short loc_18001D0E8
0x18001d0ab  mov     edx, 218h
0x18001d0b0  jmp     short loc_18001D0D0
0x18001d0b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0b9  lea     rax, WPP_GLOBAL_Control
0x18001d0c0  cmp     rcx, rax
0x18001d0c3  jz      short loc_18001D0E8
0x18001d0c5  test    byte ptr [rcx+1Ch], 1
0x18001d0c9  jz      short loc_18001D0E8
0x18001d0cb  mov     edx, 219h
0x18001d0d0  mov     rcx, [rcx+10h]
0x18001d0d4  mov     r9d, r8d
0x18001d0d7  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18001d0de  call    WPP_SF_d
0x18001d0e3  mov     r8d, [rsp+38h+Reply]
0x18001d0e8  test    r8d, r8d
0x18001d0eb  jz      loc_18001D010
0x18001d0f1  mov     rcx, [rbx+88h]
0x18001d0f8  xor     edx, edx
0x18001d0fa  mov     rax, [rbx+80h]
0x18001d101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d106  mov     eax, [rsp+38h+Reply]
0x18001d10a  mov     [rbx+78h], eax
0x18001d10d  jmp     loc_18001D010
```
