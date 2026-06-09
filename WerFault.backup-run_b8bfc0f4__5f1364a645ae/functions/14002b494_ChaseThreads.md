# ChaseThreads

- ea: `0x14002b494`
- end: `0x14002b631`
- name: `ChaseThreads`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002b638`

## callees

- `0x14001444c`
- `0x140014474`
- `0x14002b494`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b5da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b5da`
- `wer!CloseThreadWaitChainSession` at `0x14002b5d2`
- `wer!CloseThreadWaitChainSession` at `0x14002b5d2`
- `wer!GetThreadWaitChain` at `0x14002b517`
- `wer!GetThreadWaitChain` at `0x14002b517`
- `wer!RegisterWaitChainCOMCallback` at `0x14002b4da`
- `wer!RegisterWaitChainCOMCallback` at `0x14002b4da`
- `wer!OpenThreadWaitChainSession` at `0x14002b4e4`
- `wer!OpenThreadWaitChainSession` at `0x14002b4e4`
- `api-ms-win-core-com-private-l1-1-0!CoGetActivationState` at `0x14002b4b8`
- `api-ms-win-core-com-private-l1-1-0!CoGetCallState` at `0x14002b4c2`

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
0x14002b494  push    rbx
0x14002b496  push    rbp
0x14002b497  push    rsi
0x14002b498  push    rdi
0x14002b499  push    r12
0x14002b49b  push    r14
0x14002b49d  push    r15
0x14002b49f  sub     rsp, 40h
0x14002b4a3  mov     r15, [rsp+78h+arg_20]
0x14002b4ab  mov     ebp, edx
0x14002b4ad  mov     r14, [rsp+78h+arg_28]
0x14002b4b5  mov     r12d, ecx
0x14002b4b8  mov     rdx, cs:__imp_CoGetActivationState; ActivationStateCallback
0x14002b4bf  mov     rdi, r9
0x14002b4c2  mov     rcx, cs:__imp_CoGetCallState; CallStateCallback
0x14002b4c9  mov     rsi, r8
0x14002b4cc  mov     dword ptr [r15], 0
0x14002b4d3  mov     dword ptr [r14], 0
0x14002b4da  call    cs:__imp_RegisterWaitChainCOMCallback
0x14002b4e0  xor     edx, edx; callback
0x14002b4e2  xor     ecx, ecx; Flags
0x14002b4e4  call    cs:__imp_OpenThreadWaitChainSession
0x14002b4ea  mov     rbx, rax
0x14002b4ed  test    rax, rax
0x14002b4f0  jz      loc_14002B5DA
0x14002b4f6  xor     edx, edx; Context
0x14002b4f8  mov     [rsp+78h+IsCycle], r15; IsCycle
0x14002b4fd  mov     [rsp+78h+NodeInfoArray], rsi; NodeInfoArray
0x14002b502  mov     r9d, ebp; ThreadId
0x14002b505  mov     rcx, rax; WctHandle
0x14002b508  mov     dword ptr [rdi], 10h
0x14002b50e  mov     [rsp+78h+NodeCount], rdi; NodeCount
0x14002b513  lea     r8d, [rdx+7]; Flags
0x14002b517  call    cs:__imp_GetThreadWaitChain
0x14002b51d  test    eax, eax
0x14002b51f  jnz     short loc_14002B56D
0x14002b521  call    cs:__imp_GetLastError
0x14002b527  mov     edi, eax
0x14002b529  test    eax, eax
0x14002b52b  jle     short loc_14002B536
0x14002b52d  movzx   edi, ax
0x14002b530  or      edi, 80070000h
0x14002b536  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b53d  lea     rax, WPP_GLOBAL_Control
0x14002b544  cmp     rcx, rax
0x14002b547  jz      loc_14002B5CF
0x14002b54d  test    byte ptr [rcx+1Ch], 1
0x14002b551  jz      short loc_14002B5CF
0x14002b553  mov     rcx, [rcx+10h]
0x14002b557  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002b55e  mov     edx, 0Bh
0x14002b563  mov     r9d, edi
0x14002b566  call    WPP_SF_d
0x14002b56b  jmp     short loc_14002B5CF
0x14002b56d  cmp     dword ptr [rdi], 1
0x14002b570  jnz     short loc_14002B5A2
0x14002b572  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b579  lea     rax, WPP_GLOBAL_Control
0x14002b580  cmp     rcx, rax
0x14002b583  jz      short loc_14002B5CD
0x14002b585  test    byte ptr [rcx+1Ch], 4
0x14002b589  jz      short loc_14002B5CD
0x14002b58b  mov     rcx, [rcx+10h]
0x14002b58f  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002b596  mov     edx, 0Ch
0x14002b59b  call    WPP_SF_
0x14002b5a0  jmp     short loc_14002B5CD
0x14002b5a2  xor     ecx, ecx
0x14002b5a4  cmp     [rdi], ecx
0x14002b5a6  jbe     short loc_14002B5CD
0x14002b5a8  mov     eax, ecx
0x14002b5aa  imul    rdx, rax, 118h
0x14002b5b1  cmp     dword ptr [rdx+rsi], 8
0x14002b5b5  jnz     short loc_14002B5BE
0x14002b5b7  cmp     [rdx+rsi+8], r12d
0x14002b5bc  jnz     short loc_14002B5C6
0x14002b5be  inc     ecx
0x14002b5c0  cmp     ecx, [rdi]
0x14002b5c2  jb      short loc_14002B5A8
0x14002b5c4  jmp     short loc_14002B5CD
0x14002b5c6  mov     dword ptr [r14], 1
0x14002b5cd  xor     edi, edi
0x14002b5cf  mov     rcx, rbx; WctHandle
0x14002b5d2  call    cs:__imp_CloseThreadWaitChainSession
0x14002b5d8  jmp     short loc_14002B620
0x14002b5da  call    cs:__imp_GetLastError
0x14002b5e0  mov     edi, eax
0x14002b5e2  test    eax, eax
0x14002b5e4  jle     short loc_14002B5EF
0x14002b5e6  movzx   edi, ax
0x14002b5e9  or      edi, 80070000h
0x14002b5ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b5f6  lea     rax, WPP_GLOBAL_Control
0x14002b5fd  cmp     rcx, rax
0x14002b600  jz      short loc_14002B620
0x14002b602  test    byte ptr [rcx+1Ch], 1
0x14002b606  jz      short loc_14002B620
0x14002b608  mov     rcx, [rcx+10h]
0x14002b60c  lea     r8, WPP_1969d98add70354507e1e1f7959b3b3f_Traceguids
0x14002b613  mov     edx, 0Ah
0x14002b618  mov     r9d, edi
0x14002b61b  call    WPP_SF_d
0x14002b620  mov     eax, edi
0x14002b622  add     rsp, 40h
0x14002b626  pop     r15
0x14002b628  pop     r14
0x14002b62a  pop     r12
0x14002b62c  pop     rdi
0x14002b62d  pop     rsi
0x14002b62e  pop     rbp
0x14002b62f  pop     rbx
0x14002b630  retn
```
