# CThreadChasing::DoThreadChasing(ulong,ulong,int)

- ea: `0x14001b24c`
- end: `0x14001babb`
- name: `?DoThreadChasing@CThreadChasing@@QEAAJKKH@Z`
- size: `2159`
- prototype: `__int64 __fastcall(CThreadChasing *__hidden this, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140029bb0`
- `0x14002b5d8`

## callees

- `0x140002490`
- `0x14000d5ac`
- `0x140014ee4`
- `0x140014f14`
- `0x140014f58`
- `0x140015014`
- `0x14001af94`
- `0x14001b24c`
- `0x14005f510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14001b39d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14001b39d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b51d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ba43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b51d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ba43`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001b97c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001b97c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b9dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b9dc`
- `wer!CloseThreadWaitChainSession` at `0x14001ba81`
- `wer!CloseThreadWaitChainSession` at `0x14001ba81`
- `wer!GetThreadWaitChain` at `0x14001b407`
- `wer!GetThreadWaitChain` at `0x14001b407`
- `wer!RegisterWaitChainCOMCallback` at `0x14001b2e9`
- `wer!RegisterWaitChainCOMCallback` at `0x14001b2e9`
- `wer!OpenThreadWaitChainSession` at `0x14001b301`
- `wer!OpenThreadWaitChainSession` at `0x14001b301`
- `api-ms-win-core-com-private-l1-1-0!CoGetActivationState` at `0x14001b2d5`
- `api-ms-win-core-com-private-l1-1-0!CoGetCallState` at `0x14001b2dc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14001b49f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14001b49f`

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
              WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids);
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
0x14001b24c  mov     [rsp+arg_8], rbx
0x14001b251  push    rbp
0x14001b252  push    rsi
0x14001b253  push    rdi
0x14001b254  push    r12
0x14001b256  push    r13
0x14001b258  push    r14
0x14001b25a  push    r15
0x14001b25c  mov     eax, 11F0h
0x14001b261  call    _alloca_probe
0x14001b266  sub     rsp, rax
0x14001b269  mov     rax, cs:__security_cookie
0x14001b270  xor     rax, rsp
0x14001b273  mov     [rsp+1228h+var_48], rax
0x14001b27b  xorps   xmm0, xmm0
0x14001b27e  mov     [rsp+1228h+var_11E4], 10h
0x14001b286  movups  xmmword ptr [rsp+1228h+Handles], xmm0
0x14001b28b  mov     esi, r9d
0x14001b28e  mov     [rsp+1228h+var_11E8], 0
0x14001b296  mov     ebp, r8d
0x14001b299  mov     r12d, edx
0x14001b29c  mov     rdi, rcx
0x14001b29f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b2a6  lea     r13, WPP_GLOBAL_Control
0x14001b2ad  lea     r15, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001b2b4  mov     r14d, 4
0x14001b2ba  cmp     rcx, r13
0x14001b2bd  jz      short loc_14001B2D5
0x14001b2bf  test    [rcx+1Ch], r14b
0x14001b2c3  jz      short loc_14001B2D5
0x14001b2c5  mov     rcx, [rcx+10h]
0x14001b2c9  lea     edx, [r14+10h]
0x14001b2cd  mov     r8, r15
0x14001b2d0  call    WPP_SF_
0x14001b2d5  mov     rdx, cs:__imp_CoGetActivationState; ActivationStateCallback
0x14001b2dc  mov     rcx, cs:__imp_CoGetCallState; CallStateCallback
0x14001b2e3  mov     dword ptr [rdi], 3E5h
0x14001b2e9  call    cs:__imp_RegisterWaitChainCOMCallback
0x14001b2f0  nop     dword ptr [rax+rax+00h]
0x14001b2f5  lea     rdx, ?StaticWaitChainCallback@CThreadChasing@@KAXPEAX_KKPEAKPEAU_WAITCHAIN_NODE_INFO@@PEAH@Z; callback
0x14001b2fc  mov     ecx, 1; Flags
0x14001b301  call    cs:__imp_OpenThreadWaitChainSession
0x14001b308  nop     dword ptr [rax+rax+00h]
0x14001b30d  mov     [rsp+1228h+var_11E0], rax
0x14001b312  mov     rbx, rax
0x14001b315  test    rax, rax
0x14001b318  jz      loc_14001BA31
0x14001b31e  neg     esi
0x14001b320  mov     dword ptr [rsp+1228h+NodeCount], 0FFFFFFFFh; unsigned int
0x14001b328  lea     rdx, aDisablenetwork; "DisableNetworkWCT"
0x14001b32f  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x14001b336  sbb     esi, esi
0x14001b338  xor     r9d, r9d; unsigned int
0x14001b33b  xor     r8d, r8d; unsigned int
0x14001b33e  and     esi, 3
0x14001b341  call    ?ReadDwordCheckBounds@@YAKPEAUHKEY__@@PEB_WKKK@Z; ReadDwordCheckBounds(HKEY__ *,wchar_t const *,ulong,ulong,ulong)
0x14001b346  test    eax, eax
0x14001b348  jz      short loc_14001B396
0x14001b34a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b351  cmp     rcx, r13
0x14001b354  jz      short loc_14001B399
0x14001b356  test    [rcx+1Ch], r14b
0x14001b35a  jz      short loc_14001B378
0x14001b35c  mov     rcx, [rcx+10h]
0x14001b360  lea     r8, WPP_7dfea4b94cdd34dca73de5f762289470_Traceguids
0x14001b367  mov     edx, 0Fh
0x14001b36c  call    WPP_SF_
0x14001b371  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b378  cmp     rcx, r13
0x14001b37b  jz      short loc_14001B399
0x14001b37d  test    [rcx+1Ch], r14b
0x14001b381  jz      short loc_14001B399
0x14001b383  mov     rcx, [rcx+10h]
0x14001b387  mov     edx, 16h
0x14001b38c  mov     r8, r15
0x14001b38f  call    WPP_SF_
0x14001b394  jmp     short loc_14001B399
0x14001b396  or      esi, 8
0x14001b399  mov     rcx, [rdi+8]; hEvent
0x14001b39d  call    cs:__imp_ResetEvent
0x14001b3a4  nop     dword ptr [rax+rax+00h]
0x14001b3a9  test    eax, eax
0x14001b3ab  jnz     short loc_14001B3DD
0x14001b3ad  mov     rax, cs:WPP_GLOBAL_Control
0x14001b3b4  cmp     rax, r13
0x14001b3b7  jz      loc_14001BA6A
0x14001b3bd  test    byte ptr [rax+1Ch], 1
0x14001b3c1  jz      loc_14001BA6A
0x14001b3c7  call    cs:__imp_GetLastError
0x14001b3ce  nop     dword ptr [rax+rax+00h]
0x14001b3d3  mov     edx, 17h
0x14001b3d8  jmp     loc_14001BA54
0x14001b3dd  lea     rax, [rsp+1228h+var_11E8]
0x14001b3e2  mov     r9d, ebp; ThreadId
0x14001b3e5  mov     [rsp+1228h+IsCycle], rax; IsCycle
0x14001b3ea  mov     r8d, esi; Flags
0x14001b3ed  lea     rax, [rsp+1228h+var_11C8]
0x14001b3f2  mov     rdx, rdi; Context
0x14001b3f5  mov     [rsp+1228h+NodeInfoArray], rax; NodeInfoArray
0x14001b3fa  mov     rcx, rbx; WctHandle
0x14001b3fd  lea     rax, [rsp+1228h+var_11E4]
0x14001b402  mov     [rsp+1228h+NodeCount], rax; NodeCount
0x14001b407  call    cs:__imp_GetThreadWaitChain
0x14001b40e  nop     dword ptr [rax+rax+00h]
0x14001b413  test    eax, eax
0x14001b415  jnz     short loc_14001B45A
0x14001b417  call    cs:__imp_GetLastError
0x14001b41e  nop     dword ptr [rax+rax+00h]
0x14001b423  cmp     eax, 3E5h
0x14001b428  jz      short loc_14001B45A
0x14001b42a  mov     rax, cs:WPP_GLOBAL_Control
0x14001b431  cmp     rax, r13
0x14001b434  jz      loc_14001BA6A
0x14001b43a  test    byte ptr [rax+1Ch], 1
0x14001b43e  jz      loc_14001BA6A
0x14001b444  call    cs:__imp_GetLastError
0x14001b44b  nop     dword ptr [rax+rax+00h]
0x14001b450  mov     edx, 18h
0x14001b455  jmp     loc_14001BA54
0x14001b45a  mov     rax, [rdi+10h]
0x14001b45e  mov     [rsp+1228h+Handles], rax
0x14001b463  mov     rax, [rdi+8]
0x14001b467  mov     [rsp+1228h+Handles+8], rax
0x14001b46c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b473  cmp     rcx, r13
0x14001b476  jz      short loc_14001B48F
0x14001b478  test    [rcx+1Ch], r14b
0x14001b47c  jz      short loc_14001B48F
0x14001b47e  mov     rcx, [rcx+10h]
0x14001b482  mov     edx, 19h
0x14001b487  mov     r8, r15
0x14001b48a  call    WPP_SF_
0x14001b48f  xor     r8d, r8d; bWaitAll
0x14001b492  lea     rdx, [rsp+1228h+Handles]; lpHandles
0x14001b497  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14001b49b  lea     ecx, [r8+2]; nCount
0x14001b49f  call    cs:__imp_WaitForMultipleObjects
0x14001b4a6  nop     dword ptr [rax+rax+00h]
0x14001b4ab  mov     esi, eax
0x14001b4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b4b4  cmp     rcx, r13
0x14001b4b7  jz      short loc_14001B4DA
0x14001b4b9  test    [rcx+1Ch], r14b
0x14001b4bd  jz      short loc_14001B4DA
0x14001b4bf  mov     rcx, [rcx+10h]
0x14001b4c3  mov     edx, 1Ah
0x14001b4c8  mov     r9d, eax
0x14001b4cb  mov     r8, r15
0x14001b4ce  call    WPP_SF_d
0x14001b4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b4da  test    esi, esi
0x14001b4dc  jnz     short loc_14001B512
0x14001b4de  mov     dword ptr [rdi], 4C7h
0x14001b4e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b4eb  cmp     rcx, r13
0x14001b4ee  jz      loc_14001BA6A
0x14001b4f4  test    [rcx+1Ch], r14b
0x14001b4f8  jz      loc_14001BA6A
0x14001b4fe  lea     edx, [rsi+1Bh]
0x14001b501  mov     rcx, [rcx+10h]
0x14001b505  mov     r8, r15
0x14001b508  call    WPP_SF_
0x14001b50d  jmp     loc_14001BA6A
0x14001b512  mov     r10d, 1
0x14001b518  cmp     esi, r10d
0x14001b51b  jz      short loc_14001B54F
0x14001b51d  call    cs:__imp_GetLastError
0x14001b524  nop     dword ptr [rax+rax+00h]
0x14001b529  mov     [rdi], eax
0x14001b52b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b532  cmp     rcx, r13
0x14001b535  jz      loc_14001BA6A
0x14001b53b  test    byte ptr [rcx+1Ch], 1
0x14001b53f  jz      loc_14001BA6A
0x14001b545  mov     edx, 1Ch
0x14001b54a  jmp     loc_14001BA5B
0x14001b54f  mov     r9d, [rdi+1198h]
0x14001b556  cmp     r9d, r10d
0x14001b559  jnz     short loc_14001B575
0x14001b55b  cmp     rcx, r13
0x14001b55e  jz      loc_14001BA6A
0x14001b564  test    [rcx+1Ch], r14b
0x14001b568  jz      loc_14001BA6A
0x14001b56e  mov     edx, 1Dh
0x14001b573  jmp     short loc_14001B501
0x14001b575  cmp     rcx, r13
0x14001b578  jz      short loc_14001B597
0x14001b57a  test    [rcx+1Ch], r14b
0x14001b57e  jz      short loc_14001B597
0x14001b580  mov     rcx, [rcx+10h]
0x14001b584  mov     edx, 1Eh
0x14001b589  mov     r8, r15
0x14001b58c  call    WPP_SF_d
0x14001b591  mov     r10d, 1
0x14001b597  mov     eax, [rdi+1198h]
0x14001b59d  test    eax, eax
0x14001b59f  jz      loc_14001BA6A
0x14001b5a5  xor     ebx, ebx
0x14001b5a7  mov     ebp, ebx
0x14001b5a9  lea     r15d, [rbp+1]
0x14001b5ad  mov     edx, ebx
0x14001b5af  cmp     r15d, eax
0x14001b5b2  jnb     short loc_14001B5CE
0x14001b5b4  mov     eax, r15d
0x14001b5b7  imul    rcx, rax, 118h
0x14001b5be  cmp     dword ptr [rcx+rdi+18h], 8
0x14001b5c3  jnz     short loc_14001B5CE
0x14001b5c5  cmp     [rcx+rdi+20h], r12d
0x14001b5ca  cmovnz  edx, r10d
0x14001b5ce  mov     eax, ebp
0x14001b5d0  imul    rsi, rax, 118h
0x14001b5d7  mov     ecx, [rsi+rdi+18h]
0x14001b5db  cmp     ecx, 6
0x14001b5de  jg      loc_14001B7D6
0x14001b5e4  jz      loc_14001B858
0x14001b5ea  sub     ecx, 1
0x14001b5ed  jz      loc_14001B792
0x14001b5f3  sub     ecx, 1
0x14001b5f6  jz      loc_14001B73E
0x14001b5fc  sub     ecx, 1
0x14001b5ff  jz      loc_14001B6E7
0x14001b605  sub     ecx, 1
0x14001b608  jz      short loc_14001B673
0x14001b60a  cmp     ecx, 1
0x14001b60d  jnz     loc_14001B9F4
0x14001b613  test    edx, edx
0x14001b615  jz      short loc_14001B648
0x14001b617  or      dword ptr [rdi+11B0h], 40h
0x14001b61e  mov     [rdi+11ACh], ebp
0x14001b624  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b62b  cmp     rcx, r13
0x14001b62e  jz      loc_14001B9F4
0x14001b634  test    [rcx+1Ch], r14b
0x14001b638  jz      loc_14001B9F4
0x14001b63e  mov     edx, 2Ah ; '*'
0x14001b643  jmp     loc_14001B7B8
0x14001b648  or      dword ptr [rdi+11B0h], 8
0x14001b64f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b656  cmp     rcx, r13
0x14001b659  jz      loc_14001B9F4
0x14001b65f  test    [rcx+1Ch], r14b
0x14001b663  jz      loc_14001B9F4
0x14001b669  mov     edx, 2Bh ; '+'
0x14001b66e  jmp     loc_14001B7B8
0x14001b673  bts     dword ptr [rdi+11B0h], 7
0x14001b67b  lea     r8, [rdi+20h]
0x14001b67f  add     r8, rsi
0x14001b682  mov     edx, ebx
0x14001b684  cmp     [r8], bx
0x14001b688  jz      short loc_14001B6A5
0x14001b68a  mov     eax, edx
0x14001b68c  movzx   ecx, word ptr [r8+rax*2]
0x14001b691  sub     cx, 30h ; '0'
0x14001b695  cmp     cx, 9
0x14001b699  jbe     short loc_14001B6AB
0x14001b69b  add     edx, r10d
0x14001b69e  cmp     [r8+rdx*2], bx
0x14001b6a3  jnz     short loc_14001B68A
0x14001b6a5  mov     [rdi+11A8h], ebp
0x14001b6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b6b2  cmp     rcx, r13
0x14001b6b5  jz      loc_14001B9F4
0x14001b6bb  test    [rcx+1Ch], r14b
0x14001b6bf  jz      loc_14001B9F4
0x14001b6c5  mov     rcx, [rcx+10h]
0x14001b6c9  mov     edx, 23h ; '#'
0x14001b6ce  mov     [rsp+1228h+NodeCount], r8
0x14001b6d3  mov     r9d, ebp
0x14001b6d6  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001b6dd  call    WPP_SF_dS
0x14001b6e2  jmp     loc_14001B7CB
0x14001b6e7  test    edx, edx
0x14001b6e9  jz      short loc_14001B716
0x14001b6eb  or      dword ptr [rdi+11B0h], 10h
0x14001b6f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b6f9  cmp     rcx, r13
0x14001b6fc  jz      loc_14001B9F4
0x14001b702  test    [rcx+1Ch], r14b
0x14001b706  jz      loc_14001B9F4
0x14001b70c  mov     edx, 26h ; '&'
0x14001b711  jmp     loc_14001B7B8
0x14001b716  or      dword ptr [rdi+11B0h], 2
0x14001b71d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b724  cmp     rcx, r13
0x14001b727  jz      loc_14001B9F4
0x14001b72d  test    [rcx+1Ch], r14b
0x14001b731  jz      loc_14001B9F4
0x14001b737  mov     edx, 27h ; '''
0x14001b73c  jmp     short loc_14001B7B8
0x14001b73e  test    edx, edx
0x14001b740  jz      short loc_14001B76A
0x14001b742  or      dword ptr [rdi+11B0h], 20h
0x14001b749  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b750  cmp     rcx, r13
0x14001b753  jz      loc_14001B9F4
0x14001b759  test    [rcx+1Ch], r14b
0x14001b75d  jz      loc_14001B9F4
0x14001b763  mov     edx, 28h ; '('
0x14001b768  jmp     short loc_14001B7B8
0x14001b76a  or      [rdi+11B0h], r14d
  ... truncated ...
```
