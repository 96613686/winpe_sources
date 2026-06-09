# ChaseThreads

- ea: `0x14002d150`
- end: `0x14002d312`
- name: `ChaseThreads`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002d318`

## callees

- `0x140014ee4`
- `0x140014f14`
- `0x14002d150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d2b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d2b4`
- `wer!CloseThreadWaitChainSession` at `0x14002d2a6`
- `wer!CloseThreadWaitChainSession` at `0x14002d2a6`
- `wer!GetThreadWaitChain` at `0x14002d1df`
- `wer!GetThreadWaitChain` at `0x14002d1df`
- `wer!RegisterWaitChainCOMCallback` at `0x14002d196`
- `wer!RegisterWaitChainCOMCallback` at `0x14002d196`
- `wer!OpenThreadWaitChainSession` at `0x14002d1a6`
- `wer!OpenThreadWaitChainSession` at `0x14002d1a6`
- `api-ms-win-core-com-private-l1-1-0!CoGetActivationState` at `0x14002d174`
- `api-ms-win-core-com-private-l1-1-0!CoGetCallState` at `0x14002d17e`

## pseudocode

```c
__int64 __fastcall ChaseThreads(
        int a1,
        DWORD a2,
        struct _WAITCHAIN_NODE_INFO *a3,
        DWORD *a4,
        LPBOOL IsCycle,
        _DWORD *a6)
{
  void *v10; // rax
  void *v11; // rbx
  signed int LastError; // eax
  unsigned int v13; // edi
  unsigned int v14; // ecx
  __int64 v15; // rdx
  signed int v16; // eax

  *IsCycle = 0;
  *a6 = 0;
  RegisterWaitChainCOMCallback(CoGetCallState, CoGetActivationState);
  v10 = OpenThreadWaitChainSession(0, 0);
  v11 = v10;
  if ( v10 )
  {
    *a4 = 16;
    if ( GetThreadWaitChain(v10, 0, 7u, a2, a4, a3, IsCycle) )
    {
      if ( *a4 == 1 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids);
        }
      }
      else
      {
        v14 = 0;
        if ( *a4 )
        {
          while ( 1 )
          {
            v15 = v14;
            if ( a3[v15].ObjectType == WctThreadType && a3[v15].ThreadObject.ProcessId != a1 )
              break;
            if ( ++v14 >= *a4 )
              goto LABEL_18;
          }
          *a6 = 1;
        }
      }
LABEL_18:
      v13 = 0;
    }
    else
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids, v13);
      }
    }
    CloseThreadWaitChainSession(v11);
  }
  else
  {
    v16 = GetLastError();
    v13 = v16;
    if ( v16 > 0 )
      v13 = (unsigned __int16)v16 | 0x80070000;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids, v13);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x14002d150  push    rbx
0x14002d152  push    rbp
0x14002d153  push    rsi
0x14002d154  push    rdi
0x14002d155  push    r12
0x14002d157  push    r14
0x14002d159  push    r15
0x14002d15b  sub     rsp, 40h
0x14002d15f  mov     r15, [rsp+78h+arg_20]
0x14002d167  mov     ebp, edx
0x14002d169  mov     r14, [rsp+78h+arg_28]
0x14002d171  mov     r12d, ecx
0x14002d174  mov     rdx, cs:__imp_CoGetActivationState; ActivationStateCallback
0x14002d17b  mov     rdi, r9
0x14002d17e  mov     rcx, cs:__imp_CoGetCallState; CallStateCallback
0x14002d185  mov     rsi, r8
0x14002d188  mov     dword ptr [r15], 0
0x14002d18f  mov     dword ptr [r14], 0
0x14002d196  call    cs:__imp_RegisterWaitChainCOMCallback
0x14002d19d  nop     dword ptr [rax+rax+00h]
0x14002d1a2  xor     edx, edx; callback
0x14002d1a4  xor     ecx, ecx; Flags
0x14002d1a6  call    cs:__imp_OpenThreadWaitChainSession
0x14002d1ad  nop     dword ptr [rax+rax+00h]
0x14002d1b2  mov     rbx, rax
0x14002d1b5  test    rax, rax
0x14002d1b8  jz      loc_14002D2B4
0x14002d1be  xor     edx, edx; Context
0x14002d1c0  mov     [rsp+78h+IsCycle], r15; IsCycle
0x14002d1c5  mov     [rsp+78h+NodeInfoArray], rsi; NodeInfoArray
0x14002d1ca  mov     r9d, ebp; ThreadId
0x14002d1cd  mov     rcx, rax; WctHandle
0x14002d1d0  mov     dword ptr [rdi], 10h
0x14002d1d6  mov     [rsp+78h+NodeCount], rdi; NodeCount
0x14002d1db  lea     r8d, [rdx+7]; Flags
0x14002d1df  call    cs:__imp_GetThreadWaitChain
0x14002d1e6  nop     dword ptr [rax+rax+00h]
0x14002d1eb  test    eax, eax
0x14002d1ed  jnz     short loc_14002D241
0x14002d1ef  call    cs:__imp_GetLastError
0x14002d1f6  nop     dword ptr [rax+rax+00h]
0x14002d1fb  mov     edi, eax
0x14002d1fd  test    eax, eax
0x14002d1ff  jle     short loc_14002D20A
0x14002d201  movzx   edi, ax
0x14002d204  or      edi, 80070000h
0x14002d20a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d211  lea     rax, WPP_GLOBAL_Control
0x14002d218  cmp     rcx, rax
0x14002d21b  jz      loc_14002D2A3
0x14002d221  test    byte ptr [rcx+1Ch], 1
0x14002d225  jz      short loc_14002D2A3
0x14002d227  mov     rcx, [rcx+10h]
0x14002d22b  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002d232  mov     edx, 0Bh
0x14002d237  mov     r9d, edi
0x14002d23a  call    WPP_SF_d
0x14002d23f  jmp     short loc_14002D2A3
0x14002d241  cmp     dword ptr [rdi], 1
0x14002d244  jnz     short loc_14002D276
0x14002d246  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d24d  lea     rax, WPP_GLOBAL_Control
0x14002d254  cmp     rcx, rax
0x14002d257  jz      short loc_14002D2A1
0x14002d259  test    byte ptr [rcx+1Ch], 4
0x14002d25d  jz      short loc_14002D2A1
0x14002d25f  mov     rcx, [rcx+10h]
0x14002d263  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002d26a  mov     edx, 0Ch
0x14002d26f  call    WPP_SF_
0x14002d274  jmp     short loc_14002D2A1
0x14002d276  xor     ecx, ecx
0x14002d278  cmp     [rdi], ecx
0x14002d27a  jbe     short loc_14002D2A1
0x14002d27c  mov     eax, ecx
0x14002d27e  imul    rdx, rax, 118h
0x14002d285  cmp     dword ptr [rdx+rsi], 8
0x14002d289  jnz     short loc_14002D292
0x14002d28b  cmp     [rdx+rsi+8], r12d
0x14002d290  jnz     short loc_14002D29A
0x14002d292  inc     ecx
0x14002d294  cmp     ecx, [rdi]
0x14002d296  jb      short loc_14002D27C
0x14002d298  jmp     short loc_14002D2A1
0x14002d29a  mov     dword ptr [r14], 1
0x14002d2a1  xor     edi, edi
0x14002d2a3  mov     rcx, rbx; WctHandle
0x14002d2a6  call    cs:__imp_CloseThreadWaitChainSession
0x14002d2ad  nop     dword ptr [rax+rax+00h]
0x14002d2b2  jmp     short loc_14002D300
0x14002d2b4  call    cs:__imp_GetLastError
0x14002d2bb  nop     dword ptr [rax+rax+00h]
0x14002d2c0  mov     edi, eax
0x14002d2c2  test    eax, eax
0x14002d2c4  jle     short loc_14002D2CF
0x14002d2c6  movzx   edi, ax
0x14002d2c9  or      edi, 80070000h
0x14002d2cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d2d6  lea     rax, WPP_GLOBAL_Control
0x14002d2dd  cmp     rcx, rax
0x14002d2e0  jz      short loc_14002D300
0x14002d2e2  test    byte ptr [rcx+1Ch], 1
0x14002d2e6  jz      short loc_14002D300
0x14002d2e8  mov     rcx, [rcx+10h]
0x14002d2ec  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002d2f3  mov     edx, 0Ah
0x14002d2f8  mov     r9d, edi
0x14002d2fb  call    WPP_SF_d
0x14002d300  mov     eax, edi
0x14002d302  add     rsp, 40h
0x14002d306  pop     r15
0x14002d308  pop     r14
0x14002d30a  pop     r12
0x14002d30c  pop     rdi
0x14002d30d  pop     rsi
0x14002d30e  pop     rbp
0x14002d30f  pop     rbx
0x14002d310  retn
```
