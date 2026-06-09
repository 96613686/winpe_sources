# s_UbpmRpcTaskHostSendResponseReceiveCommand

- ea: `0x1800278a0`
- end: `0x180027a27`
- name: `s_UbpmRpcTaskHostSendResponseReceiveCommand`
- size: `391`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800278a0`
- `0x180032f78`
- `0x18003eee0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180027942`
- `ntdll!RtlReleaseSRWLockShared` at `0x180027942`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800278c4`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800278c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002792f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002792f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027994`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027994`

## pseudocode

```c
__int64 __fastcall s_UbpmRpcTaskHostSendResponseReceiveCommand(
        struct _RPC_ASYNC_STATE *a1,
        __int64 a2,
        _OWORD *a3,
        __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  char v10; // al
  signed __int32 v12; // r8d
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rcx
  signed __int32 v17[10]; // [rsp+0h] [rbp-68h] BYREF
  unsigned int Reply; // [rsp+70h] [rbp+8h] BYREF

  Reply = 0;
  RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
  if ( *(_DWORD *)a2 != 1665679957 )
  {
    Reply = 5;
    goto LABEL_8;
  }
  v10 = *(_BYTE *)(a2 + 104);
  if ( (v10 & 4) != 0 )
  {
    v12 = 1067;
    Reply = 1067;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v14 = 25;
LABEL_17:
    v15 = *(unsigned int *)(a2 + 32);
    v16 = v13[2];
    v17[8] = v12;
    WPP_SF_dd(v16, v14, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v15);
    goto LABEL_8;
  }
  if ( (v10 & 8) == 0 )
  {
    v12 = 1237;
    Reply = 1237;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_8;
    v14 = 26;
    goto LABEL_17;
  }
  *(_QWORD *)(a2 + 56) = a1;
  a1 = 0;
  *(_QWORD *)(a2 + 168) = a4;
  *(_OWORD *)(a2 + 112) = *a3;
  *(_OWORD *)(a2 + 128) = a3[1];
  _InterlockedOr(v17, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_Lqii(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v9,
      *(unsigned int *)(a2 + 32),
      a2,
      *(_QWORD *)(a2 + 96),
      *(_QWORD *)(a2 + 120));
  SetEvent(*(HANDLE *)(a2 + 48));
LABEL_8:
  RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
  if ( a1 )
    RpcAsyncCompleteCall(a1, &Reply);
  return Reply;
}

```

## disassembly

```asm
0x1800278a0  push    rbx
0x1800278a2  push    rbp
0x1800278a3  push    rsi
0x1800278a4  push    rdi
0x1800278a5  sub     rsp, 48h
0x1800278a9  mov     rdi, rcx
0x1800278ac  mov     [rsp+68h+Reply], 0
0x1800278b4  lea     rcx, g_TaskHostContextListLock
0x1800278bb  mov     rbp, r9
0x1800278be  mov     rsi, r8
0x1800278c1  mov     rbx, rdx
0x1800278c4  call    cs:__imp_RtlAcquireSRWLockShared
0x1800278cb  nop     dword ptr [rax+rax+00h]
0x1800278d0  cmp     dword ptr [rbx], 63484255h
0x1800278d6  jnz     loc_1800279F1
0x1800278dc  mov     al, [rbx+68h]
0x1800278df  test    al, 4
0x1800278e1  jnz     short loc_180027961
0x1800278e3  test    al, 8
0x1800278e5  jz      loc_1800279A2
0x1800278eb  mov     [rbx+38h], rdi
0x1800278ef  xor     edi, edi
0x1800278f1  mov     [rbx+0A8h], rbp
0x1800278f8  movups  xmm0, xmmword ptr [rsi]
0x1800278fb  movups  xmmword ptr [rbx+70h], xmm0
0x1800278ff  movups  xmm1, xmmword ptr [rsi+10h]
0x180027903  movups  xmmword ptr [rbx+80h], xmm1
0x18002790a  lock or [rsp+68h+var_68], edi
0x18002790e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027915  lea     rax, WPP_GLOBAL_Control
0x18002791c  cmp     rcx, rax
0x18002791f  jz      short loc_18002792B
0x180027921  test    byte ptr [rcx+1Ch], 80h
0x180027925  jnz     loc_1800279FE
0x18002792b  mov     rcx, [rbx+30h]; hEvent
0x18002792f  call    cs:__imp_SetEvent
0x180027936  nop     dword ptr [rax+rax+00h]
0x18002793b  lea     rcx, g_TaskHostContextListLock
0x180027942  call    cs:__imp_RtlReleaseSRWLockShared
0x180027949  nop     dword ptr [rax+rax+00h]
0x18002794e  test    rdi, rdi
0x180027951  jnz     short loc_18002798C
0x180027953  mov     eax, [rsp+68h+Reply]
0x180027957  add     rsp, 48h
0x18002795b  pop     rdi
0x18002795c  pop     rsi
0x18002795d  pop     rbp
0x18002795e  pop     rbx
0x18002795f  retn
0x180027961  mov     r8d, 42Bh
0x180027967  mov     [rsp+68h+Reply], r8d
0x18002796c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027973  lea     rax, WPP_GLOBAL_Control
0x18002797a  cmp     rcx, rax
0x18002797d  jz      short loc_18002793B
0x18002797f  test    byte ptr [rcx+1Ch], 1
0x180027983  jz      short loc_18002793B
0x180027985  mov     edx, 19h
0x18002798a  jmp     short loc_1800279D3
0x18002798c  lea     rdx, [rsp+68h+Reply]; Reply
0x180027991  mov     rcx, rdi; pAsync
0x180027994  call    cs:__imp_RpcAsyncCompleteCall
0x18002799b  nop     dword ptr [rax+rax+00h]
0x1800279a0  jmp     short loc_180027953
0x1800279a2  mov     r8d, 4D5h
0x1800279a8  mov     [rsp+68h+Reply], r8d
0x1800279ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279b4  lea     rax, WPP_GLOBAL_Control
0x1800279bb  cmp     rcx, rax
0x1800279be  jz      loc_18002793B
0x1800279c4  test    byte ptr [rcx+1Ch], 2
0x1800279c8  jz      loc_18002793B
0x1800279ce  mov     edx, 1Ah
0x1800279d3  mov     r9d, [rbx+20h]
0x1800279d7  mov     rcx, [rcx+10h]
0x1800279db  mov     dword ptr [rsp+68h+var_48], r8d
0x1800279e0  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800279e7  call    WPP_SF_dd
0x1800279ec  jmp     loc_18002793B
0x1800279f1  mov     [rsp+68h+Reply], 5
0x1800279f9  jmp     loc_18002793B
0x1800279fe  mov     rax, [rbx+78h]
0x180027a02  mov     r9d, [rbx+20h]
0x180027a06  mov     rcx, [rcx+10h]
0x180027a0a  mov     [rsp+68h+var_38], rax
0x180027a0f  mov     rax, [rbx+60h]
0x180027a13  mov     [rsp+68h+var_40], rax
0x180027a18  mov     [rsp+68h+var_48], rbx
0x180027a1d  call    WPP_SF_Lqii
0x180027a22  jmp     loc_18002792B
```
