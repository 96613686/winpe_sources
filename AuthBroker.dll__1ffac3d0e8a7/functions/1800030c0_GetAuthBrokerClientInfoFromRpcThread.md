# _GetAuthBrokerClientInfoFromRpcThread

- ea: `0x1800030c0`
- end: `0x180003328`
- name: `_GetAuthBrokerClientInfoFromRpcThread`
- size: `616`
- prototype: `__int64 __fastcall(unsigned int *clientProcessId, unsigned int *clientThreadId, void **clientTokenHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a70`
- `0x180002b20`

## callees

- `0x1800030c0`
- `0x18000737c`
- `0x180011b30`

## import_xrefs

- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800030f9`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800030f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003272`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800031e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800031e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800031fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800031fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003305`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003268`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003268`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800031a4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800031a4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000330f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000330f`
- `api-ms-win-core-com-l1-1-0!CoGetCallerTID` at `0x18000315b`
- `api-ms-win-core-com-l1-1-0!CoGetCallerTID` at `0x18000315b`

## pseudocode

```c
__int64 __fastcall GetAuthBrokerClientInfoFromRpcThread(
        unsigned int *clientProcessId,
        unsigned int *clientThreadId,
        void **clientTokenHandle)
{
  int v5; // esi
  RPC_STATUS v6; // eax
  unsigned int v7; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v8; // rcx
  unsigned __int16 v9; // dx
  unsigned int v10; // r9d
  HRESULT v11; // eax
  HANDLE CurrentThread; // rax
  signed int v13; // eax
  signed int LastError; // eax
  unsigned int tokenInformationSize; // [rsp+60h] [rbp+8h] BYREF
  unsigned int isAppContainer; // [rsp+68h] [rbp+10h] BYREF
  void *tokenHandle; // [rsp+70h] [rbp+18h] BYREF

  *clientProcessId = 0;
  *clientThreadId = 0;
  v5 = 0;
  tokenHandle = 0;
  isAppContainer = 0;
  tokenInformationSize = 0;
  *clientTokenHandle = 0;
  v6 = I_RpcBindingInqLocalClientPID(0, clientProcessId);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      v9 = 26;
LABEL_8:
      v10 = v7;
LABEL_9:
      WPP_SF_d(v8[1].Control.Logger, v9, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v10);
    }
  }
  else
  {
    if ( CoGetCallerTID(clientThreadId) >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 5u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control[1].Control.Logger,
          0x1Bu,
          WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
          *clientThreadId);
      }
      if ( *clientThreadId == -1 )
        *clientThreadId = 0;
    }
    v11 = CoImpersonateClient();
    v7 = v11;
    if ( v11 >= 0 )
    {
      v5 = 1;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &tokenHandle) )
      {
        if ( GetTokenInformation(tokenHandle, TokenIsAppContainer, &isAppContainer, 4u, &tokenInformationSize) )
        {
          if ( tokenInformationSize == 4 && isAppContainer )
          {
            v7 = 0;
            *clientTokenHandle = tokenHandle;
            tokenHandle = 0;
LABEL_46:
            CoRevertToSelf();
            return v7;
          }
          v7 = -2147020646;
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x1Fu, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
          }
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            v9 = 30;
            goto LABEL_8;
          }
        }
      }
      else
      {
        v13 = GetLastError();
        v7 = v13;
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          v9 = 29;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        v9 = 28;
        v10 = v11;
        goto LABEL_9;
      }
    }
  }
  if ( tokenHandle )
    CloseHandle(tokenHandle);
  if ( v5 )
    goto LABEL_46;
  return v7;
}

```

## disassembly

```asm
0x1800030c0  mov     [rsp+arg_18], rbx
0x1800030c5  push    rbp
0x1800030c6  push    rsi
0x1800030c7  push    rdi
0x1800030c8  push    r14
0x1800030ca  push    r15
0x1800030cc  sub     rsp, 30h
0x1800030d0  xor     r15d, r15d
0x1800030d3  mov     rdi, clientThreadId
0x1800030d6  mov     [clientProcessId], r15d
0x1800030d9  mov     r14, clientTokenHandle
0x1800030dc  mov     [clientThreadId], r15d
0x1800030df  mov     esi, r15d
0x1800030e2  mov     clientThreadId, clientProcessId; Pid
0x1800030e5  mov     [rsp+58h+tokenHandle], r15
0x1800030ea  xor     ecx, ecx; Binding
0x1800030ec  mov     [rsp+58h+isAppContainer], r15d
0x1800030f1  mov     [rsp+58h+tokenInformationSize], r15d
0x1800030f6  mov     [clientTokenHandle], r15
0x1800030f9  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800030ff  mov     ebx, eax
0x180003101  test    eax, eax
0x180003103  jz      short loc_180003158
0x180003105  jle     short loc_180003110
0x180003107  movzx   ebx, ax
0x18000310a  or      ebx, 80070000h
0x180003110  mov     clientProcessId, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180003117  lea     rbp, WPP_GLOBAL_Control
0x18000311e  cmp     clientProcessId, rbp
0x180003121  jz      $Exit_1
0x180003127  test    byte ptr [clientProcessId+44h], 10h
0x18000312b  jz      $Exit_1
0x180003131  cmp     byte ptr [clientProcessId+41h], 2
0x180003135  jb      $Exit_1
0x18000313b  mov     edx, 1Ah; id
0x180003140  mov     r9d, ebx; _a1
0x180003143  mov     clientProcessId, [clientProcessId+38h]; Logger
0x180003147  lea     clientTokenHandle, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000314e  call    WPP_SF_d
0x180003153  jmp     $Exit_1
0x180003158  mov     clientProcessId, rdi; lpdwTID
0x18000315b  call    cs:__imp_CoGetCallerTID
0x180003161  lea     rbp, WPP_GLOBAL_Control
0x180003168  test    eax, eax
0x18000316a  js      short loc_1800031A4
0x18000316c  mov     clientProcessId, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180003173  cmp     clientProcessId, rbp
0x180003176  jz      short loc_18000319C
0x180003178  test    byte ptr [clientProcessId+44h], 10h
0x18000317c  jz      short loc_18000319C
0x18000317e  cmp     byte ptr [clientProcessId+41h], 5
0x180003182  jb      short loc_18000319C
0x180003184  mov     r9d, [rdi]; _a1
0x180003187  lea     clientTokenHandle, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000318e  mov     clientProcessId, [clientProcessId+38h]; Logger
0x180003192  mov     edx, 1Bh; id
0x180003197  call    WPP_SF_d
0x18000319c  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18000319f  jnz     short loc_1800031A4
0x1800031a1  mov     [rdi], r15d
0x1800031a4  call    cs:__imp_CoImpersonateClient
0x1800031aa  mov     ebx, eax
0x1800031ac  test    eax, eax
0x1800031ae  jns     short loc_1800031E1
0x1800031b0  mov     clientProcessId, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800031b7  cmp     clientProcessId, rbp
0x1800031ba  jz      $Exit_1
0x1800031c0  test    byte ptr [clientProcessId+44h], 10h
0x1800031c4  jz      $Exit_1
0x1800031ca  cmp     byte ptr [clientProcessId+41h], 2
0x1800031ce  jb      $Exit_1
0x1800031d4  mov     edx, 1Ch
0x1800031d9  mov     r9d, eax
0x1800031dc  jmp     loc_180003143
0x1800031e1  mov     esi, 1
0x1800031e6  call    cs:__imp_GetCurrentThread
0x1800031ec  lea     r9, [rsp+58h+tokenHandle]; TokenHandle
0x1800031f1  mov     r8d, esi; OpenAsSelf
0x1800031f4  mov     clientProcessId, rax; ThreadHandle
0x1800031f7  mov     edx, 8; DesiredAccess
0x1800031fc  call    cs:__imp_OpenThreadToken
0x180003202  test    eax, eax
0x180003204  jnz     short loc_180003249
0x180003206  call    cs:__imp_GetLastError
0x18000320c  mov     ebx, eax
0x18000320e  test    eax, eax
0x180003210  jle     short loc_18000321B
0x180003212  movzx   ebx, ax
0x180003215  or      ebx, 80070000h
0x18000321b  mov     clientProcessId, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180003222  cmp     clientProcessId, rbp
0x180003225  jz      $Exit_1
0x18000322b  test    byte ptr [clientProcessId+44h], 10h
0x18000322f  jz      $Exit_1
0x180003235  cmp     byte ptr [clientProcessId+41h], 2
0x180003239  jb      $Exit_1
0x18000323f  mov     edx, 1Dh
0x180003244  jmp     loc_180003140
0x180003249  mov     clientProcessId, [rsp+58h+tokenHandle]; TokenHandle
0x18000324e  lea     rax, [rsp+58h+tokenInformationSize]
0x180003253  mov     r9d, 4; TokenInformationLength
0x180003259  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000325e  lea     clientTokenHandle, [rsp+58h+isAppContainer]; TokenInformation
0x180003263  mov     edx, 1Dh; TokenInformationClass
0x180003268  call    cs:__imp_GetTokenInformation
0x18000326e  test    eax, eax
0x180003270  jnz     short loc_1800032A9
0x180003272  call    cs:__imp_GetLastError
0x180003278  mov     ebx, eax
0x18000327a  test    eax, eax
0x18000327c  jle     short loc_180003287
0x18000327e  movzx   ebx, ax
0x180003281  or      ebx, 80070000h
0x180003287  mov     clientProcessId, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000328e  cmp     clientProcessId, rbp
0x180003291  jz      short $Exit_1
0x180003293  test    byte ptr [clientProcessId+44h], 10h
0x180003297  jz      short $Exit_1
0x180003299  cmp     byte ptr [clientProcessId+41h], 2
0x18000329d  jb      short $Exit_1
0x18000329f  mov     edx, 1Eh
0x1800032a4  jmp     loc_180003140
0x1800032a9  cmp     [rsp+58h+tokenInformationSize], 4
0x1800032ae  jnz     short loc_1800032C9
0x1800032b0  cmp     [rsp+58h+isAppContainer], r15d
0x1800032b5  jz      short loc_1800032C9
0x1800032b7  mov     rax, [rsp+58h+tokenHandle]
0x1800032bc  mov     ebx, r15d
0x1800032bf  mov     [r14], rax
0x1800032c2  mov     [rsp+58h+tokenHandle], r15
0x1800032c7  jmp     short loc_18000330F
0x1800032c9  mov     ebx, 8007109Ah
0x1800032ce  mov     clientProcessId, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800032d5  cmp     clientProcessId, rbp
0x1800032d8  jz      short $Exit_1
0x1800032da  test    byte ptr [clientProcessId+44h], 10h
0x1800032de  jz      short $Exit_1
0x1800032e0  cmp     byte ptr [clientProcessId+41h], 2
0x1800032e4  jb      short $Exit_1
0x1800032e6  mov     clientProcessId, [clientProcessId+38h]; Logger
0x1800032ea  lea     clientTokenHandle, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800032f1  mov     edx, 1Fh; id
0x1800032f6  call    WPP_SF_
0x1800032fb  mov     clientProcessId, [rsp+58h+tokenHandle]; hObject
0x180003300  test    clientProcessId, clientProcessId
0x180003303  jz      short loc_18000330B
0x180003305  call    cs:__imp_CloseHandle
0x18000330b  test    esi, esi
0x18000330d  jz      short loc_180003315
0x18000330f  call    cs:__imp_CoRevertToSelf
0x180003315  mov     eax, ebx
0x180003317  mov     rbx, [rsp+58h+arg_18]
0x18000331c  add     rsp, 30h
0x180003320  pop     r15
0x180003322  pop     r14
0x180003324  pop     rdi
0x180003325  pop     rsi
0x180003326  pop     rbp
0x180003327  retn
```
