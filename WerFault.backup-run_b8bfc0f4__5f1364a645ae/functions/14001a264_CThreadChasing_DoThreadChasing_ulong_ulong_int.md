# CThreadChasing::DoThreadChasing(ulong,ulong,int)

- ea: `0x14001a264`
- end: `0x14001aa84`
- name: `?DoThreadChasing@CThreadChasing@@QEAAJKKH@Z`
- size: `2080`
- prototype: `__int64 __fastcall(CThreadChasing *__hidden this, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400280fc`
- `0x140029a14`

## callees

- `0x140002470`
- `0x14000d2ec`
- `0x14001444c`
- `0x140014474`
- `0x1400144b4`
- `0x140014564`
- `0x140019fc8`
- `0x14001a264`
- `0x14005b770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14001a3a9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14001a3a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001aa19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001aa19`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001a95e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001a95e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a9b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a9b8`
- `wer!CloseThreadWaitChainSession` at `0x14001aa51`
- `wer!CloseThreadWaitChainSession` at `0x14001aa51`
- `wer!GetThreadWaitChain` at `0x14001a407`
- `wer!GetThreadWaitChain` at `0x14001a407`
- `wer!RegisterWaitChainCOMCallback` at `0x14001a301`
- `wer!RegisterWaitChainCOMCallback` at `0x14001a301`
- `wer!OpenThreadWaitChainSession` at `0x14001a313`
- `wer!OpenThreadWaitChainSession` at `0x14001a313`
- `api-ms-win-core-com-private-l1-1-0!CoGetActivationState` at `0x14001a2ed`
- `api-ms-win-core-com-private-l1-1-0!CoGetCallState` at `0x14001a2f4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14001a48d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14001a48d`

## pseudocode

```c
__int64 __fastcall CThreadChasing::DoThreadChasing(HANDLE *this, int a2, DWORD a3, int a4)
{
  void *v8; // rbx
  DWORD v9; // esi
  CUserModeHangReport *v10; // rcx
  DWORD LastError; // eax
  __int64 v12; // rdx
  DWORD v13; // eax
  DWORD v14; // esi
  CUserModeHangReport *v15; // rcx
  __int64 v16; // rdx
  CUserModeHangReport *v17; // rcx
  __int64 v18; // r9
  unsigned int v19; // eax
  unsigned int v20; // ebp
  unsigned int v21; // r15d
  BOOL v22; // edx
  __int64 v23; // rcx
  __int64 v24; // rsi
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  CUserModeHangReport *v30; // rcx
  __int64 v31; // rdx
  HANDLE *v32; // r8
  __int64 v33; // rdx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // eax
  int v39; // r8d
  int v40; // eax
  DWORD v41; // r8d
  char *v42; // r14
  int v43; // r8d
  int v44; // edi
  WINBOOL IsCycle; // [rsp+40h] [rbp-11E8h] BYREF
  DWORD NodeCount; // [rsp+44h] [rbp-11E4h] BYREF
  HWCT v48; // [rsp+48h] [rbp-11E0h]
  HANDLE Handles[2]; // [rsp+50h] [rbp-11D8h] BYREF
  struct _WAITCHAIN_NODE_INFO NodeInfoArray; // [rsp+60h] [rbp-11C8h] BYREF

  NodeCount = 16;
  *(_OWORD *)Handles = 0;
  IsCycle = 0;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids);
  }
  *(_DWORD *)this = 997;
  RegisterWaitChainCOMCallback(CoGetCallState, CoGetActivationState);
  v48 = OpenThreadWaitChainSession(1u, CThreadChasing::StaticWaitChainCallback);
  v8 = v48;
  if ( !v48 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v12 = 21;
      goto LABEL_129;
    }
    goto LABEL_131;
  }
  v9 = a4 != 0 ? 3 : 0;
  if ( ReadDwordCheckBounds(HKEY_LOCAL_MACHINE, L"DisableNetworkWCT", 0, 0, 0xFFFFFFFF) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_7dfea4b94cdd34dca73de5f762289470_Traceguids);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v10 + 2), 22, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids);
    }
  }
  else
  {
    v9 |= 8u;
  }
  if ( !ResetEvent(this[1]) )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v12 = 23;
LABEL_129:
      v17 = WPP_GLOBAL_Control;
      goto LABEL_130;
    }
    goto LABEL_131;
  }
  if ( GetThreadWaitChain(v48, (DWORD_PTR)this, v9, a3, &NodeCount, &NodeInfoArray, &IsCycle) || GetLastError() == 997 )
  {
    Handles[0] = this[2];
    Handles[1] = this[1];
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids);
    }
    v13 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    v14 = v13;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v13);
      v15 = WPP_GLOBAL_Control;
    }
    if ( !v14 )
    {
      *(_DWORD *)this = 1223;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_131;
      }
      v16 = 27;
      goto LABEL_32;
    }
    if ( v14 != 1 )
    {
      LastError = GetLastError();
      *(_DWORD *)this = LastError;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 28;
LABEL_130:
        WPP_SF_d(*((_QWORD *)v17 + 2), v12, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, LastError);
        goto LABEL_131;
      }
      goto LABEL_131;
    }
    v18 = *((unsigned int *)this + 1126);
    if ( (_DWORD)v18 == 1 )
    {
      if ( v15 == (CUserModeHangReport *)&WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 4) == 0 )
        goto LABEL_131;
      v16 = 29;
LABEL_32:
      WPP_SF_(*((_QWORD *)v15 + 2), v16, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids);
      goto LABEL_131;
    }
    if ( v15 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v15 + 2), 30, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v18);
    v19 = *((_DWORD *)this + 1126);
    if ( !v19 )
      goto LABEL_131;
    v20 = 0;
    while ( 1 )
    {
      v21 = v20 + 1;
      v22 = 0;
      if ( v20 + 1 < v19 )
      {
        v23 = 35LL * v21;
        if ( LODWORD(this[v23 + 3]) == 8 )
          v22 = LODWORD(this[v23 + 4]) != a2;
      }
      v24 = 35LL * v20;
      v25 = (int)this[v24 + 3];
      if ( v25 > 6 )
        break;
      if ( v25 == 6 )
        goto LABEL_100;
      v26 = v25 - 1;
      if ( !v26 )
      {
        *((_DWORD *)this + 1132) |= 1u;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_121;
        }
        v31 = 34;
        goto LABEL_87;
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
        if ( v22 )
        {
          *((_DWORD *)this + 1132) |= 0x20u;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_121;
          }
          v31 = 40;
        }
        else
        {
          *((_DWORD *)this + 1132) |= 4u;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_121;
          }
          v31 = 41;
        }
        goto LABEL_87;
      }
      v28 = v27 - 1;
      if ( !v28 )
      {
        if ( v22 )
        {
          *((_DWORD *)this + 1132) |= 0x10u;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_121;
          }
          v31 = 38;
        }
        else
        {
          *((_DWORD *)this + 1132) |= 2u;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_121;
          }
          v31 = 39;
        }
        goto LABEL_87;
      }
      v29 = v28 - 1;
      if ( !v29 )
      {
        *((_DWORD *)this + 1132) |= 0x80u;
        v32 = &this[v24 + 4];
        LODWORD(v33) = 0;
        if ( *(_WORD *)v32 )
        {
          while ( (unsigned __int16)(*((_WORD *)v32 + (unsigned int)v33) - 48) > 9u )
          {
            v33 = (unsigned int)(v33 + 1);
            if ( !*((_WORD *)v32 + v33) )
              goto LABEL_66;
          }
        }
        else
        {
LABEL_66:
          *((_DWORD *)this + 1130) = v20;
        }
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
            v20,
            (__int64)&this[v24 + 4]);
        }
        goto LABEL_121;
      }
      if ( v29 == 1 )
      {
        if ( v22 )
        {
          *((_DWORD *)this + 1132) |= 0x40u;
          *((_DWORD *)this + 1131) = v20;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_121;
          }
          v31 = 42;
        }
        else
        {
          *((_DWORD *)this + 1132) |= 8u;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_121;
          }
          v31 = 43;
        }
        goto LABEL_87;
      }
LABEL_121:
      v19 = *((_DWORD *)this + 1126);
      ++v20;
      if ( v21 >= v19 )
      {
        v8 = v48;
        goto LABEL_131;
      }
    }
    v34 = v25 - 7;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( !v35 )
      {
        v39 = (int)this[v24 + 4];
        if ( v39 == a2 )
        {
          v41 = HIDWORD(this[v24 + 4]);
          if ( v41 )
          {
            v42 = (char *)OpenThread(0x1FFFFFu, 0, v41);
            if ( v42 != (char *)-1LL && v42 + 1 != (char *)1 )
            {
              v43 = HIDWORD(this[v24 + 4]);
              *((_DWORD *)this + 1129) = v43;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_DDD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  33,
                  WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
                  v20,
                  a2,
                  v43);
              }
              CloseHandle(v42);
            }
          }
        }
        else
        {
          *((_DWORD *)this + 1127) = v39;
          if ( (unsigned int)(HIDWORD(this[v24 + 3]) - 4) <= 1 )
          {
            *((_DWORD *)this + 1128) = 0;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                32,
                WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
                v20,
                v39);
            }
          }
          else
          {
            v40 = HIDWORD(this[v24 + 4]);
            *((_DWORD *)this + 1128) = v40;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_DDD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
                v20,
                v39,
                v40);
            }
          }
        }
        goto LABEL_121;
      }
      v36 = v35 - 1;
      if ( v36 )
      {
        v37 = v36 - 2;
        if ( v37 )
        {
          if ( v37 != 1 )
            goto LABEL_121;
          *((_DWORD *)this + 1132) |= 0x80000u;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_121;
          }
          v31 = 37;
        }
        else
        {
          *((_DWORD *)this + 1132) |= 0x40000u;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_121;
          }
          v31 = 36;
        }
      }
      else
      {
        *((_DWORD *)this + 1132) |= 0x10000u;
LABEL_100:
        v38 = *((_DWORD *)this + 1132);
        if ( v22 )
        {
          *((_DWORD *)this + 1132) = v38 | 0x100000;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_121;
          }
          v31 = 44;
        }
        else
        {
          *((_DWORD *)this + 1132) = v38 | 0x4000;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_121;
          }
          v31 = 45;
        }
      }
    }
    else
    {
      *((_DWORD *)this + 1132) |= 0x8000u;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_121;
      }
      v31 = 46;
    }
LABEL_87:
    WPP_SF_d(*((_QWORD *)v30 + 2), v31, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v20);
    goto LABEL_121;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    v12 = 24;
    goto LABEL_129;
  }
LABEL_131:
  v44 = *(_DWORD *)this;
  if ( v44 > 0 )
    v44 = (unsigned __int16)v44 | 0x80070000;
  if ( v8 )
    CloseThreadWaitChainSession(v8);
  return (unsigned int)v44;
}

```

## disassembly

```asm
0x14001a264  mov     [rsp+arg_8], rbx
0x14001a269  push    rbp
0x14001a26a  push    rsi
0x14001a26b  push    rdi
0x14001a26c  push    r12
0x14001a26e  push    r13
0x14001a270  push    r14
0x14001a272  push    r15
0x14001a274  mov     eax, 11F0h
0x14001a279  call    _alloca_probe
0x14001a27e  sub     rsp, rax
0x14001a281  mov     rax, cs:__security_cookie
0x14001a288  xor     rax, rsp
0x14001a28b  mov     [rsp+1228h+var_48], rax
0x14001a293  xorps   xmm0, xmm0
0x14001a296  mov     [rsp+1228h+var_11E4], 10h
0x14001a29e  movups  xmmword ptr [rsp+1228h+Handles], xmm0
0x14001a2a3  mov     esi, r9d
0x14001a2a6  mov     [rsp+1228h+var_11E8], 0
0x14001a2ae  mov     ebp, r8d
0x14001a2b1  mov     r12d, edx
0x14001a2b4  mov     rdi, rcx
0x14001a2b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a2be  lea     r13, WPP_GLOBAL_Control
0x14001a2c5  lea     r15, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001a2cc  mov     r14d, 4
0x14001a2d2  cmp     rcx, r13
0x14001a2d5  jz      short loc_14001A2ED
0x14001a2d7  test    [rcx+1Ch], r14b
0x14001a2db  jz      short loc_14001A2ED
0x14001a2dd  mov     rcx, [rcx+10h]
0x14001a2e1  lea     edx, [r14+10h]
0x14001a2e5  mov     r8, r15
0x14001a2e8  call    WPP_SF_
0x14001a2ed  mov     rdx, cs:__imp_CoGetActivationState; ActivationStateCallback
0x14001a2f4  mov     rcx, cs:__imp_CoGetCallState; CallStateCallback
0x14001a2fb  mov     dword ptr [rdi], 3E5h
0x14001a301  call    cs:__imp_RegisterWaitChainCOMCallback
0x14001a307  lea     rdx, ?StaticWaitChainCallback@CThreadChasing@@KAXPEAX_KKPEAKPEAU_WAITCHAIN_NODE_INFO@@PEAH@Z; callback
0x14001a30e  mov     ecx, 1; Flags
0x14001a313  call    cs:__imp_OpenThreadWaitChainSession
0x14001a319  mov     [rsp+1228h+var_11E0], rax
0x14001a31e  mov     rbx, rax
0x14001a321  test    rax, rax
0x14001a324  jz      loc_14001AA07
0x14001a32a  neg     esi
0x14001a32c  mov     dword ptr [rsp+1228h+NodeCount], 0FFFFFFFFh; unsigned int
0x14001a334  lea     rdx, aDisablenetwork; "DisableNetworkWCT"
0x14001a33b  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x14001a342  sbb     esi, esi
0x14001a344  xor     r9d, r9d; unsigned int
0x14001a347  xor     r8d, r8d; unsigned int
0x14001a34a  and     esi, 3
0x14001a34d  call    ?ReadDwordCheckBounds@@YAKPEAUHKEY__@@PEB_WKKK@Z; ReadDwordCheckBounds(HKEY__ *,wchar_t const *,ulong,ulong,ulong)
0x14001a352  test    eax, eax
0x14001a354  jz      short loc_14001A3A2
0x14001a356  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a35d  cmp     rcx, r13
0x14001a360  jz      short loc_14001A3A5
0x14001a362  test    [rcx+1Ch], r14b
0x14001a366  jz      short loc_14001A384
0x14001a368  mov     rcx, [rcx+10h]
0x14001a36c  lea     r8, WPP_7dfea4b94cdd34dca73de5f762289470_Traceguids
0x14001a373  mov     edx, 0Fh
0x14001a378  call    WPP_SF_
0x14001a37d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a384  cmp     rcx, r13
0x14001a387  jz      short loc_14001A3A5
0x14001a389  test    [rcx+1Ch], r14b
0x14001a38d  jz      short loc_14001A3A5
0x14001a38f  mov     rcx, [rcx+10h]
0x14001a393  mov     edx, 16h
0x14001a398  mov     r8, r15
0x14001a39b  call    WPP_SF_
0x14001a3a0  jmp     short loc_14001A3A5
0x14001a3a2  or      esi, 8
0x14001a3a5  mov     rcx, [rdi+8]; hEvent
0x14001a3a9  call    cs:__imp_ResetEvent
0x14001a3af  test    eax, eax
0x14001a3b1  jnz     short loc_14001A3DD
0x14001a3b3  mov     rax, cs:WPP_GLOBAL_Control
0x14001a3ba  cmp     rax, r13
0x14001a3bd  jz      loc_14001AA3A
0x14001a3c3  test    byte ptr [rax+1Ch], 1
0x14001a3c7  jz      loc_14001AA3A
0x14001a3cd  call    cs:__imp_GetLastError
0x14001a3d3  mov     edx, 17h
0x14001a3d8  jmp     loc_14001AA24
0x14001a3dd  lea     rax, [rsp+1228h+var_11E8]
0x14001a3e2  mov     r9d, ebp; ThreadId
0x14001a3e5  mov     [rsp+1228h+IsCycle], rax; IsCycle
0x14001a3ea  mov     r8d, esi; Flags
0x14001a3ed  lea     rax, [rsp+1228h+var_11C8]
0x14001a3f2  mov     rdx, rdi; Context
0x14001a3f5  mov     [rsp+1228h+NodeInfoArray], rax; NodeInfoArray
0x14001a3fa  mov     rcx, rbx; WctHandle
0x14001a3fd  lea     rax, [rsp+1228h+var_11E4]
0x14001a402  mov     [rsp+1228h+NodeCount], rax; NodeCount
0x14001a407  call    cs:__imp_GetThreadWaitChain
0x14001a40d  test    eax, eax
0x14001a40f  jnz     short loc_14001A448
0x14001a411  call    cs:__imp_GetLastError
0x14001a417  cmp     eax, 3E5h
0x14001a41c  jz      short loc_14001A448
0x14001a41e  mov     rax, cs:WPP_GLOBAL_Control
0x14001a425  cmp     rax, r13
0x14001a428  jz      loc_14001AA3A
0x14001a42e  test    byte ptr [rax+1Ch], 1
0x14001a432  jz      loc_14001AA3A
0x14001a438  call    cs:__imp_GetLastError
0x14001a43e  mov     edx, 18h
0x14001a443  jmp     loc_14001AA24
0x14001a448  mov     rax, [rdi+10h]
0x14001a44c  mov     [rsp+1228h+Handles], rax
0x14001a451  mov     rax, [rdi+8]
0x14001a455  mov     [rsp+1228h+Handles+8], rax
0x14001a45a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a461  cmp     rcx, r13
0x14001a464  jz      short loc_14001A47D
0x14001a466  test    [rcx+1Ch], r14b
0x14001a46a  jz      short loc_14001A47D
0x14001a46c  mov     rcx, [rcx+10h]
0x14001a470  mov     edx, 19h
0x14001a475  mov     r8, r15
0x14001a478  call    WPP_SF_
0x14001a47d  xor     r8d, r8d; bWaitAll
0x14001a480  lea     rdx, [rsp+1228h+Handles]; lpHandles
0x14001a485  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14001a489  lea     ecx, [r8+2]; nCount
0x14001a48d  call    cs:__imp_WaitForMultipleObjects
0x14001a493  mov     esi, eax
0x14001a495  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a49c  cmp     rcx, r13
0x14001a49f  jz      short loc_14001A4C2
0x14001a4a1  test    [rcx+1Ch], r14b
0x14001a4a5  jz      short loc_14001A4C2
0x14001a4a7  mov     rcx, [rcx+10h]
0x14001a4ab  mov     edx, 1Ah
0x14001a4b0  mov     r9d, eax
0x14001a4b3  mov     r8, r15
0x14001a4b6  call    WPP_SF_d
0x14001a4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4c2  test    esi, esi
0x14001a4c4  jnz     short loc_14001A4FA
0x14001a4c6  mov     dword ptr [rdi], 4C7h
0x14001a4cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4d3  cmp     rcx, r13
0x14001a4d6  jz      loc_14001AA3A
0x14001a4dc  test    [rcx+1Ch], r14b
0x14001a4e0  jz      loc_14001AA3A
0x14001a4e6  lea     edx, [rsi+1Bh]
0x14001a4e9  mov     rcx, [rcx+10h]
0x14001a4ed  mov     r8, r15
0x14001a4f0  call    WPP_SF_
0x14001a4f5  jmp     loc_14001AA3A
0x14001a4fa  mov     r10d, 1
0x14001a500  cmp     esi, r10d
0x14001a503  jz      short loc_14001A531
0x14001a505  call    cs:__imp_GetLastError
0x14001a50b  mov     [rdi], eax
0x14001a50d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a514  cmp     rcx, r13
0x14001a517  jz      loc_14001AA3A
0x14001a51d  test    byte ptr [rcx+1Ch], 1
0x14001a521  jz      loc_14001AA3A
0x14001a527  mov     edx, 1Ch
0x14001a52c  jmp     loc_14001AA2B
0x14001a531  mov     r9d, [rdi+1198h]
0x14001a538  cmp     r9d, r10d
0x14001a53b  jnz     short loc_14001A557
0x14001a53d  cmp     rcx, r13
0x14001a540  jz      loc_14001AA3A
0x14001a546  test    [rcx+1Ch], r14b
0x14001a54a  jz      loc_14001AA3A
0x14001a550  mov     edx, 1Dh
0x14001a555  jmp     short loc_14001A4E9
0x14001a557  cmp     rcx, r13
0x14001a55a  jz      short loc_14001A579
0x14001a55c  test    [rcx+1Ch], r14b
0x14001a560  jz      short loc_14001A579
0x14001a562  mov     rcx, [rcx+10h]
0x14001a566  mov     edx, 1Eh
0x14001a56b  mov     r8, r15
0x14001a56e  call    WPP_SF_d
0x14001a573  mov     r10d, 1
0x14001a579  mov     eax, [rdi+1198h]
0x14001a57f  test    eax, eax
0x14001a581  jz      loc_14001AA3A
0x14001a587  xor     ebx, ebx
0x14001a589  mov     ebp, ebx
0x14001a58b  lea     r15d, [rbp+1]
0x14001a58f  mov     edx, ebx
0x14001a591  cmp     r15d, eax
0x14001a594  jnb     short loc_14001A5B0
0x14001a596  mov     eax, r15d
0x14001a599  imul    rcx, rax, 118h
0x14001a5a0  cmp     dword ptr [rcx+rdi+18h], 8
0x14001a5a5  jnz     short loc_14001A5B0
0x14001a5a7  cmp     [rcx+rdi+20h], r12d
0x14001a5ac  cmovnz  edx, r10d
0x14001a5b0  mov     eax, ebp
0x14001a5b2  imul    rsi, rax, 118h
0x14001a5b9  mov     ecx, [rsi+rdi+18h]
0x14001a5bd  cmp     ecx, 6
0x14001a5c0  jg      loc_14001A7B8
0x14001a5c6  jz      loc_14001A83A
0x14001a5cc  sub     ecx, 1
0x14001a5cf  jz      loc_14001A774
0x14001a5d5  sub     ecx, 1
0x14001a5d8  jz      loc_14001A720
0x14001a5de  sub     ecx, 1
0x14001a5e1  jz      loc_14001A6C9
0x14001a5e7  sub     ecx, 1
0x14001a5ea  jz      short loc_14001A655
0x14001a5ec  cmp     ecx, 1
0x14001a5ef  jnz     loc_14001A9CA
0x14001a5f5  test    edx, edx
0x14001a5f7  jz      short loc_14001A62A
0x14001a5f9  or      dword ptr [rdi+11B0h], 40h
0x14001a600  mov     [rdi+11ACh], ebp
0x14001a606  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a60d  cmp     rcx, r13
0x14001a610  jz      loc_14001A9CA
0x14001a616  test    [rcx+1Ch], r14b
0x14001a61a  jz      loc_14001A9CA
0x14001a620  mov     edx, 2Ah ; '*'
0x14001a625  jmp     loc_14001A79A
0x14001a62a  or      dword ptr [rdi+11B0h], 8
0x14001a631  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a638  cmp     rcx, r13
0x14001a63b  jz      loc_14001A9CA
0x14001a641  test    [rcx+1Ch], r14b
0x14001a645  jz      loc_14001A9CA
0x14001a64b  mov     edx, 2Bh ; '+'
0x14001a650  jmp     loc_14001A79A
0x14001a655  bts     dword ptr [rdi+11B0h], 7
0x14001a65d  lea     r8, [rdi+20h]
0x14001a661  add     r8, rsi
0x14001a664  mov     edx, ebx
0x14001a666  cmp     [r8], bx
0x14001a66a  jz      short loc_14001A687
0x14001a66c  mov     eax, edx
0x14001a66e  movzx   ecx, word ptr [r8+rax*2]
0x14001a673  sub     cx, 30h ; '0'
0x14001a677  cmp     cx, 9
0x14001a67b  jbe     short loc_14001A68D
0x14001a67d  add     edx, r10d
0x14001a680  cmp     [r8+rdx*2], bx
0x14001a685  jnz     short loc_14001A66C
0x14001a687  mov     [rdi+11A8h], ebp
0x14001a68d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a694  cmp     rcx, r13
0x14001a697  jz      loc_14001A9CA
0x14001a69d  test    [rcx+1Ch], r14b
0x14001a6a1  jz      loc_14001A9CA
0x14001a6a7  mov     rcx, [rcx+10h]
0x14001a6ab  mov     edx, 23h ; '#'
0x14001a6b0  mov     [rsp+1228h+NodeCount], r8
0x14001a6b5  mov     r9d, ebp
0x14001a6b8  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001a6bf  call    WPP_SF_dS
0x14001a6c4  jmp     loc_14001A7AD
0x14001a6c9  test    edx, edx
0x14001a6cb  jz      short loc_14001A6F8
0x14001a6cd  or      dword ptr [rdi+11B0h], 10h
0x14001a6d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6db  cmp     rcx, r13
0x14001a6de  jz      loc_14001A9CA
0x14001a6e4  test    [rcx+1Ch], r14b
0x14001a6e8  jz      loc_14001A9CA
0x14001a6ee  mov     edx, 26h ; '&'
0x14001a6f3  jmp     loc_14001A79A
0x14001a6f8  or      dword ptr [rdi+11B0h], 2
0x14001a6ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a706  cmp     rcx, r13
0x14001a709  jz      loc_14001A9CA
0x14001a70f  test    [rcx+1Ch], r14b
0x14001a713  jz      loc_14001A9CA
0x14001a719  mov     edx, 27h ; '''
0x14001a71e  jmp     short loc_14001A79A
0x14001a720  test    edx, edx
0x14001a722  jz      short loc_14001A74C
0x14001a724  or      dword ptr [rdi+11B0h], 20h
0x14001a72b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a732  cmp     rcx, r13
0x14001a735  jz      loc_14001A9CA
0x14001a73b  test    [rcx+1Ch], r14b
0x14001a73f  jz      loc_14001A9CA
0x14001a745  mov     edx, 28h ; '('
0x14001a74a  jmp     short loc_14001A79A
0x14001a74c  or      [rdi+11B0h], r14d
0x14001a753  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a75a  cmp     rcx, r13
0x14001a75d  jz      loc_14001A9CA
0x14001a763  test    [rcx+1Ch], r14b
0x14001a767  jz      loc_14001A9CA
0x14001a76d  mov     edx, 29h ; ')'
0x14001a772  jmp     short loc_14001A79A
0x14001a774  or      [rdi+11B0h], r10d
0x14001a77b  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
