# BdeSvcApipEventTrigger

- ea: `0x180026720`
- end: `0x180027097`
- name: `BdeSvcApipEventTrigger`
- size: `2423`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180008f50`
- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18000dd60`
- `0x18000f760`
- `0x180026720`
- `0x18002d020`
- `0x180034070`
- `0x18004f2a8`
- `0x18007e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180026a97`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180026a97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026fcc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f1a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180026d29`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180026de3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180026d29`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180026de3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180026bba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180026bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026b9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026b9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026fdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027022`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026fdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027022`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800268bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026948`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800268bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026948`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027005`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027039`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027005`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027039`
- `RPCRT4!RpcImpersonateClient` at `0x180026b19`
- `RPCRT4!RpcImpersonateClient` at `0x180026b19`
- `RPCRT4!RpcRevertToSelf` at `0x180026c44`
- `RPCRT4!RpcRevertToSelf` at `0x180026c90`
- `RPCRT4!RpcRevertToSelf` at `0x180026c44`
- `RPCRT4!RpcRevertToSelf` at `0x180026c90`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180026eec`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180026eec`

## pseudocode

```c
__int64 __fastcall BdeSvcApipEventTrigger(__int64 a1, int a2, const unsigned __int16 *a3, int a4)
{
  __int64 v5; // r14
  PVOID *v6; // r10
  unsigned __int64 v7; // rbp
  _DWORD *v8; // rdi
  _DWORD *v9; // r13
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // rdx
  unsigned int v14; // ebp
  void *v15; // r15
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  _DWORD *v19; // rax
  BdeSvcWorkTracking *v20; // rcx
  unsigned __int16 *v21; // rax
  __int64 v22; // rdx
  BdeSvcWorkTracking *v23; // rcx
  unsigned int v24; // eax
  signed int v25; // eax
  HANDLE CurrentThread; // rax
  DWORD v27; // eax
  PVOID *v28; // rcx
  unsigned int v29; // eax
  unsigned int v30; // eax
  int v31; // ebp
  DWORD v32; // eax
  DWORD LastError; // eax
  int v34; // eax
  __int64 v35; // r8
  DWORD v36; // eax
  void *v37; // rcx
  void *v38; // rcx
  HANDLE hThread; // [rsp+40h] [rbp-58h]
  unsigned __int64 v42; // [rsp+48h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-48h] BYREF
  int v44; // [rsp+58h] [rbp-40h] BYREF

  v5 = a2;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v42 = 0;
  v7 = 0;
  hThread = 0;
  v8 = 0;
  TokenHandle = 0;
  v9 = 0;
  v44 = 0;
  if ( (_DWORD)v5 )
  {
    v14 = -1;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
    {
      WPP_SF_d(v6[2], 99, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v5);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v12 = -2147024809;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 )
    {
      WPP_SF_d(v6[2], 100, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, 2147942487LL);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_16:
    if ( !a4 )
    {
      v15 = hThread;
      v16 = 0;
LABEL_107:
      if ( !v15 )
        goto LABEL_141;
      if ( v16 || ResumeThread(v15) != -1 )
      {
        WaitForSingleObject(v15, 0xFFFFFFFF);
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            123,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            LastError);
        if ( !v9 )
          v9 = v8;
        v8 = v9;
      }
      CloseHandle(v15);
      goto LABEL_140;
    }
    goto LABEL_122;
  }
  v10 = (__int64)*(&arrEventTriggerDispatcher + 2 * v5);
  if ( a3 )
  {
    v17 = StringCchLengthW(a3, v10 + 1, &v42);
    v12 = v17;
    if ( v17 < 0 )
    {
      if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 2) == 0 )
        goto LABEL_24;
      v18 = 103;
      goto LABEL_23;
    }
    v7 = v42;
  }
  else
  {
    if ( v10 )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
      {
        WPP_SF_d(v6[2], 101, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, 0);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      v11 = 2147942487LL;
      v12 = -2147024809;
      if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 )
        goto LABEL_15;
      v13 = 102;
      goto LABEL_13;
    }
    v12 = 0;
  }
  v19 = LocalAlloc(0x40u, 0x20u);
  v8 = v19;
  if ( !v19 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = 2147942414LL;
    v12 = -2147024882;
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 )
      goto LABEL_15;
    v13 = 105;
    goto LABEL_13;
  }
  v19[5] = 0;
  if ( a3 )
  {
    v21 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v7 + 2);
    *((_QWORD *)v8 + 3) = v21;
    if ( !v21 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      v11 = 2147942414LL;
      v12 = -2147024882;
      if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 )
        goto LABEL_15;
      v13 = 107;
      goto LABEL_13;
    }
    v17 = StringCchCopyW(v21, v7 + 1, a3);
    v12 = v17;
    if ( v17 < 0 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v18 = 108;
LABEL_23:
      WPP_SF_d(v6[2], v18, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v17);
      v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
      v14 = 0;
      goto LABEL_16;
    }
  }
  if ( a4 )
  {
    v15 = 0;
  }
  else
  {
    if ( !(unsigned int)BdeSvcWorkTracking::StartWorkImpl(v20) )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      v12 = -2147023834;
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 )
      {
        v22 = 110;
LABEL_53:
        WPP_SF_d(v6[2], v22, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v12);
LABEL_140:
        v6 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_141;
      }
      goto LABEL_141;
    }
    hThread = (HANDLE)_o__beginthreadex(0, 0, BdeSvcEventTriggerThread, v8, 4, &v44);
    v15 = hThread;
    if ( !hThread )
    {
      BdeSvcWorkTracking::FinishWorkImpl(v23);
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      v12 = -2147467259;
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 )
      {
        v22 = 112;
        goto LABEL_53;
      }
LABEL_141:
      if ( !v8 )
        goto LABEL_149;
      goto LABEL_144;
    }
    v9 = v8;
    v8 = 0;
  }
  v24 = RpcImpersonateClient(0);
  if ( v24 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v24);
    v25 = GetLastError();
    v12 = v25;
    if ( v25 > 0 )
      v12 = (unsigned __int16)v25 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_15;
    v13 = 114;
    goto LABEL_72;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    v27 = GetLastError();
    v12 = v27;
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v27);
      v28 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (int)v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 0x40) != 0 )
      WPP_SF_d(v28[2], 116, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v12);
    v29 = RpcRevertToSelf();
    if ( v29 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_15;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v29);
    }
LABEL_14:
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_15:
    v14 = 0;
    goto LABEL_16;
  }
  v30 = RpcRevertToSelf();
  v31 = v30;
  if ( v30 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v30);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v31 > 0 )
      v12 = (unsigned __int16)v31 | 0x80070000;
    else
      v12 = v31;
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x40) == 0 )
      goto LABEL_15;
    v13 = 118;
LABEL_72:
    v11 = v12;
LABEL_13:
    WPP_SF_d(v6[2], v13, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v11);
    goto LABEL_14;
  }
  if ( !a4 )
  {
    *((_QWORD *)v9 + 1) = TokenHandle;
    *v9 = 1;
    if ( ResumeThread(v15) == -1 )
    {
      v32 = GetLastError();
      v12 = v32;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v32);
      *v9 = 0;
      v8 = v9;
      v9 = 0;
      if ( (int)v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v12);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      v16 = 0;
    }
    else
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      v16 = 1;
    }
    goto LABEL_107;
  }
  *((_QWORD *)v8 + 1) = TokenHandle;
  *v8 = 1;
  v34 = (*(&funcs_180026E6D + 2 * v5))((struct _EVENT_TRIGGER_PARAMETERS *)v8);
  v12 = v34;
  if ( v34 >= 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_LD(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, v35, 0, v34);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v14 = 0;
LABEL_122:
  if ( !v8 )
    goto LABEL_149;
  if ( v8[4] )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
      WPP_SF_d(v6[2], 124, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v14);
    if ( RevertToSelf() )
    {
      v8[4] = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v36 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v36);
    }
  }
LABEL_144:
  v37 = (void *)*((_QWORD *)v8 + 3);
  if ( v37 )
  {
    LocalFree(v37);
    *((_QWORD *)v8 + 3) = 0;
  }
  v38 = (void *)*((_QWORD *)v8 + 1);
  if ( v38 )
  {
    CloseHandle(v38);
    *((_QWORD *)v8 + 1) = 0;
  }
  LocalFree(v8);
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_149:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_(v6[2], 126, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
  return v12;
}

```

## disassembly

```asm
0x180026720  mov     [rsp+arg_0], rbx
0x180026725  mov     [rsp+arg_18], rbp
0x18002672a  push    rdi
0x18002672b  push    r12
0x18002672d  push    r13
0x18002672f  push    r14
0x180026731  push    r15
0x180026733  sub     rsp, 70h
0x180026737  mov     rax, cs:__security_cookie
0x18002673e  xor     rax, rsp
0x180026741  mov     [rsp+98h+var_38], rax
0x180026746  mov     [rsp+98h+var_60], r9d
0x18002674b  mov     r15, r8
0x18002674e  movsxd  r14, edx
0x180026751  mov     r10, cs:WPP_GLOBAL_Control
0x180026758  lea     r12, WPP_GLOBAL_Control
0x18002675f  cmp     r10, r12
0x180026762  jz      short loc_180026787
0x180026764  test    byte ptr [r10+1Ch], 20h
0x180026769  jz      short loc_180026787
0x18002676b  mov     rcx, [r10+10h]
0x18002676f  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180026776  mov     edx, 62h ; 'b'
0x18002677b  call    WPP_SF_
0x180026780  mov     r10, cs:WPP_GLOBAL_Control
0x180026787  xor     r11d, r11d
0x18002678a  mov     [rsp+98h+var_50], r11
0x18002678f  mov     ebp, r11d
0x180026792  mov     [rsp+98h+hThread], r11
0x180026797  mov     edi, r11d
0x18002679a  mov     [rsp+98h+TokenHandle], r11
0x18002679f  mov     r13d, r11d
0x1800267a2  mov     [rsp+98h+var_64], r11d
0x1800267a7  mov     [rsp+98h+var_40], r11d
0x1800267ac  test    r14d, r14d
0x1800267af  jnz     loc_180026F5D
0x1800267b5  mov     r12, r14
0x1800267b8  lea     rax, ?arrEventTriggerDispatcher@@3PAU_unnamed_type_arrEventTriggerDispatcher_@@A; _unnamed_type_arrEventTriggerDispatcher_ near * arrEventTriggerDispatcher
0x1800267bf  add     r12, r12
0x1800267c2  mov     rdx, [rax+r12*8]
0x1800267c6  test    r15, r15
0x1800267c9  jnz     loc_180026865
0x1800267cf  test    rdx, rdx
0x1800267d2  jz      loc_180026860
0x1800267d8  lea     r12, WPP_GLOBAL_Control
0x1800267df  cmp     r10, r12
0x1800267e2  jz      short loc_180026809
0x1800267e4  test    byte ptr [r10+1Ch], 2
0x1800267e9  jz      short loc_180026809
0x1800267eb  mov     rcx, [r10+10h]
0x1800267ef  lea     edx, [r11+65h]
0x1800267f3  mov     r9d, r14d
0x1800267f6  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x1800267fd  call    WPP_SF_d
0x180026802  mov     r10, cs:WPP_GLOBAL_Control
0x180026809  mov     r9d, 80070057h
0x18002680f  mov     ebx, r9d
0x180026812  cmp     r10, r12
0x180026815  jz      short loc_18002683A
0x180026817  test    byte ptr [r10+1Ch], 40h
0x18002681c  jz      short loc_18002683A
0x18002681e  mov     edx, 66h ; 'f'
0x180026823  mov     rcx, [r10+10h]
0x180026827  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18002682e  call    WPP_SF_d
0x180026833  mov     r10, cs:WPP_GLOBAL_Control
0x18002683a  mov     ebp, r14d
0x18002683d  lea     r12, WPP_GLOBAL_Control
0x180026844  cmp     [rsp+98h+var_60], 0
0x180026849  jnz     loc_180026EB5
0x18002684f  mov     r15, [rsp+98h+hThread]
0x180026854  or      ebp, 0FFFFFFFFh
0x180026857  mov     eax, [rsp+98h+var_64]
0x18002685b  jmp     loc_180026DCF
0x180026860  mov     ebx, r11d
0x180026863  jmp     short loc_1800268B7
0x180026865  inc     rdx; unsigned __int64
0x180026868  lea     r8, [rsp+98h+var_50]; unsigned __int64 *
0x18002686d  mov     rcx, r15; unsigned __int16 *
0x180026870  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180026875  mov     ebx, eax
0x180026877  test    eax, eax
0x180026879  jns     short loc_1800268B2
0x18002687b  lea     r12, WPP_GLOBAL_Control
0x180026882  cmp     r10, r12
0x180026885  jz      short loc_1800268AD
0x180026887  test    byte ptr [r10+1Ch], 2
0x18002688c  jz      short loc_1800268AD
0x18002688e  mov     edx, 67h ; 'g'
0x180026893  mov     rcx, [r10+10h]
0x180026897  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18002689e  mov     r9d, eax
0x1800268a1  call    WPP_SF_d
0x1800268a6  mov     r10, cs:WPP_GLOBAL_Control
0x1800268ad  mov     ebp, r14d
0x1800268b0  jmp     short loc_180026844
0x1800268b2  mov     rbp, [rsp+98h+var_50]
0x1800268b7  mov     edx, 20h ; ' '; uBytes
0x1800268bc  lea     ecx, [rdx+20h]; uFlags
0x1800268bf  call    cs:__imp_LocalAlloc
0x1800268c6  nop     dword ptr [rax+rax+00h]
0x1800268cb  mov     rdi, rax
0x1800268ce  test    rax, rax
0x1800268d1  jnz     short loc_18002692E
0x1800268d3  mov     r10, cs:WPP_GLOBAL_Control
0x1800268da  lea     r12, WPP_GLOBAL_Control
0x1800268e1  cmp     r10, r12
0x1800268e4  jz      short loc_180026907
0x1800268e6  test    byte ptr [r10+1Ch], 2
0x1800268eb  jz      short loc_180026907
0x1800268ed  mov     rcx, [r10+10h]
0x1800268f1  lea     edx, [rax+68h]
0x1800268f4  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x1800268fb  call    WPP_SF_
0x180026900  mov     r10, cs:WPP_GLOBAL_Control
0x180026907  mov     r9d, 8007000Eh
0x18002690d  mov     ebx, r9d
0x180026910  cmp     r10, r12
0x180026913  jz      loc_18002683A
0x180026919  test    byte ptr [r10+1Ch], 40h
0x18002691e  jz      loc_18002683A
0x180026924  mov     edx, 69h ; 'i'
0x180026929  jmp     loc_180026823
0x18002692e  mov     [rax+14h], r14d
0x180026932  test    r15, r15
0x180026935  jz      loc_1800269F9
0x18002693b  lea     rdx, ds:2[rbp*2]; uBytes
0x180026943  mov     ecx, 40h ; '@'; uFlags
0x180026948  call    cs:__imp_LocalAlloc
0x18002694f  nop     dword ptr [rax+rax+00h]
0x180026954  mov     [rdi+18h], rax
0x180026958  test    rax, rax
0x18002695b  jnz     short loc_1800269B8
0x18002695d  mov     r10, cs:WPP_GLOBAL_Control
0x180026964  lea     r12, WPP_GLOBAL_Control
0x18002696b  cmp     r10, r12
0x18002696e  jz      short loc_180026991
0x180026970  test    byte ptr [r10+1Ch], 2
0x180026975  jz      short loc_180026991
0x180026977  mov     rcx, [r10+10h]
0x18002697b  lea     edx, [rax+6Ah]
0x18002697e  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180026985  call    WPP_SF_
0x18002698a  mov     r10, cs:WPP_GLOBAL_Control
0x180026991  mov     r9d, 8007000Eh
0x180026997  mov     ebx, r9d
0x18002699a  cmp     r10, r12
0x18002699d  jz      loc_18002683A
0x1800269a3  test    byte ptr [r10+1Ch], 40h
0x1800269a8  jz      loc_18002683A
0x1800269ae  mov     edx, 6Bh ; 'k'
0x1800269b3  jmp     loc_180026823
0x1800269b8  lea     rdx, [rbp+1]; unsigned __int64
0x1800269bc  mov     r8, r15; unsigned __int16 *
0x1800269bf  mov     rcx, rax; unsigned __int16 *
0x1800269c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800269c7  mov     ebx, eax
0x1800269c9  test    eax, eax
0x1800269cb  jns     short loc_1800269F9
0x1800269cd  mov     r10, cs:WPP_GLOBAL_Control
0x1800269d4  lea     r12, WPP_GLOBAL_Control
0x1800269db  cmp     r10, r12
0x1800269de  jz      loc_1800268AD
0x1800269e4  test    byte ptr [r10+1Ch], 2
0x1800269e9  jz      loc_1800268AD
0x1800269ef  mov     edx, 6Ch ; 'l'
0x1800269f4  jmp     loc_180026893
0x1800269f9  cmp     [rsp+98h+var_60], r13d
0x1800269fe  jnz     loc_180026B14
0x180026a04  call    ?StartWorkImpl@BdeSvcWorkTracking@@AEAAHXZ; BdeSvcWorkTracking::StartWorkImpl(void)
0x180026a09  test    eax, eax
0x180026a0b  jnz     short loc_180026A77
0x180026a0d  mov     r10, cs:WPP_GLOBAL_Control
0x180026a14  lea     r12, WPP_GLOBAL_Control
0x180026a1b  cmp     r10, r12
0x180026a1e  jz      short loc_180026A41
0x180026a20  test    byte ptr [r10+1Ch], 8
0x180026a25  jz      short loc_180026A41
0x180026a27  mov     rcx, [r10+10h]
0x180026a2b  lea     edx, [rax+6Dh]
0x180026a2e  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180026a35  call    WPP_SF_
0x180026a3a  mov     r10, cs:WPP_GLOBAL_Control
0x180026a41  mov     ebx, 80070426h
0x180026a46  cmp     r10, r12
0x180026a49  jz      loc_180026FEE
0x180026a4f  test    byte ptr [r10+1Ch], 40h
0x180026a54  jz      loc_180026FEE
0x180026a5a  mov     edx, 6Eh ; 'n'
0x180026a5f  mov     rcx, [r10+10h]
0x180026a63  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180026a6a  mov     r9d, ebx
0x180026a6d  call    WPP_SF_d
0x180026a72  jmp     loc_180026FE7
0x180026a77  lea     rax, [rsp+98h+var_40]
0x180026a7c  mov     r9, rdi
0x180026a7f  mov     [rsp+98h+var_70], rax
0x180026a84  lea     r8, ?BdeSvcEventTriggerThread@@YAIPEAX@Z; BdeSvcEventTriggerThread(void *)
0x180026a8b  xor     edx, edx
0x180026a8d  mov     [rsp+98h+var_78], 4
0x180026a95  xor     ecx, ecx
0x180026a97  call    cs:__imp__o__beginthreadex
0x180026a9e  nop     dword ptr [rax+rax+00h]
0x180026aa3  mov     [rsp+98h+hThread], rax
0x180026aa8  mov     r15, rax
0x180026aab  test    rax, rax
0x180026aae  jnz     short loc_180026B0D
0x180026ab0  call    ?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::FinishWorkImpl(void)
0x180026ab5  mov     r10, cs:WPP_GLOBAL_Control
0x180026abc  lea     r12, WPP_GLOBAL_Control
0x180026ac3  cmp     r10, r12
0x180026ac6  jz      short loc_180026AEA
0x180026ac8  test    byte ptr [r10+1Ch], 2
0x180026acd  jz      short loc_180026AEA
0x180026acf  mov     rcx, [r10+10h]
0x180026ad3  lea     edx, [r15+6Fh]
0x180026ad7  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180026ade  call    WPP_SF_
0x180026ae3  mov     r10, cs:WPP_GLOBAL_Control
0x180026aea  mov     ebx, 80004005h
0x180026aef  cmp     r10, r12
0x180026af2  jz      loc_180026FEE
0x180026af8  test    byte ptr [r10+1Ch], 40h
0x180026afd  jz      loc_180026FEE
0x180026b03  mov     edx, 70h ; 'p'
0x180026b08  jmp     loc_180026A5F
0x180026b0d  mov     r13, rdi
0x180026b10  xor     edi, edi
0x180026b12  jmp     short loc_180026B17
0x180026b14  mov     r15, r13
0x180026b17  xor     ecx, ecx; BindingHandle
0x180026b19  call    cs:__imp_RpcImpersonateClient
0x180026b20  nop     dword ptr [rax+rax+00h]
0x180026b25  test    eax, eax
0x180026b27  jz      short loc_180026B9D
0x180026b29  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b30  lea     r12, WPP_GLOBAL_Control
0x180026b37  cmp     rcx, r12
0x180026b3a  jz      short loc_180026B5A
0x180026b3c  test    byte ptr [rcx+1Ch], 2
0x180026b40  jz      short loc_180026B5A
0x180026b42  mov     rcx, [rcx+10h]
0x180026b46  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180026b4d  mov     edx, 71h ; 'q'
0x180026b52  mov     r9d, eax
0x180026b55  call    WPP_SF_d
0x180026b5a  call    cs:__imp_GetLastError
0x180026b61  nop     dword ptr [rax+rax+00h]
0x180026b66  mov     ebx, eax
0x180026b68  test    eax, eax
0x180026b6a  jle     short loc_180026B75
0x180026b6c  movzx   ebx, ax
0x180026b6f  or      ebx, 80070000h
0x180026b75  mov     r10, cs:WPP_GLOBAL_Control
0x180026b7c  cmp     r10, r12
0x180026b7f  jz      loc_18002683A
0x180026b85  test    byte ptr [r10+1Ch], 40h
0x180026b8a  jz      loc_18002683A
0x180026b90  mov     edx, 72h ; 'r'
0x180026b95  mov     r9d, ebx
0x180026b98  jmp     loc_180026823
0x180026b9d  call    cs:__imp_GetCurrentThread
0x180026ba4  nop     dword ptr [rax+rax+00h]
0x180026ba9  mov     edx, 0Ch; DesiredAccess
0x180026bae  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x180026bb3  mov     rcx, rax; ThreadHandle
0x180026bb6  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180026bba  call    cs:__imp_OpenThreadToken
0x180026bc1  nop     dword ptr [rax+rax+00h]
0x180026bc6  test    eax, eax
0x180026bc8  jnz     loc_180026C90
0x180026bce  call    cs:__imp_GetLastError
0x180026bd5  nop     dword ptr [rax+rax+00h]
0x180026bda  mov     ebx, eax
0x180026bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180026be3  lea     r12, WPP_GLOBAL_Control
0x180026bea  cmp     rcx, r12
0x180026bed  jz      short loc_180026C14
0x180026bef  test    byte ptr [rcx+1Ch], 2
0x180026bf3  jz      short loc_180026C14
0x180026bf5  mov     rcx, [rcx+10h]
0x180026bf9  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180026c00  mov     edx, 73h ; 's'
0x180026c05  mov     r9d, eax
0x180026c08  call    WPP_SF_d
0x180026c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c14  test    ebx, ebx
0x180026c16  jle     short loc_180026C21
0x180026c18  movzx   ebx, bx
0x180026c1b  or      ebx, 80070000h
0x180026c21  cmp     rcx, r12
0x180026c24  jz      short loc_180026C44
0x180026c26  test    byte ptr [rcx+1Ch], 40h
0x180026c2a  jz      short loc_180026C44
0x180026c2c  mov     rcx, [rcx+10h]
0x180026c30  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180026c37  mov     edx, 74h ; 't'
0x180026c3c  mov     r9d, ebx
0x180026c3f  call    WPP_SF_d
0x180026c44  call    cs:__imp_RpcRevertToSelf
  ... truncated ...
```
