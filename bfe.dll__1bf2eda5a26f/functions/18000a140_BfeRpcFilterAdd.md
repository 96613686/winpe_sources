# BfeRpcFilterAdd

- ea: `0x18000a140`
- end: `0x18000a722`
- name: `BfeRpcFilterAdd`
- size: `1506`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800060a8`
- `0x18000864c`
- `0x180008694`
- `0x1800087a0`
- `0x18000a140`
- `0x18000ad28`
- `0x18000aef4`
- `0x18000f1a8`
- `0x180010ad0`
- `0x180018b74`
- `0x1800223a8`
- `0x180022810`
- `0x180023e78`
- `0x180024078`
- `0x180036a70`
- `0x18003f5dc`
- `0x180042f04`
- `0x180055424`
- `0x1800575c4`
- `0x180058b30`
- `0x180073828`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a32c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a43e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a32c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a43e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a1bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a1bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a260`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a260`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a2fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a40f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a56a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a57d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a2fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a40f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a56a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a57d`
- `RPCRT4!RpcRaiseException` at `0x18000a563`
- `RPCRT4!RpcRaiseException` at `0x18000a5b9`
- `RPCRT4!RpcRaiseException` at `0x18000a563`
- `RPCRT4!RpcRaiseException` at `0x18000a5b9`

## string_xrefs

- `0x18000a5e3`: `BfeSecurityDescriptorDecode`
- `0x18000a4a5`: `BfeCallCommitEx`
- `0x18000a484`: `BfeTxnCommit`
- `0x18000a684`: `BfeObjectCopyPublicState`

## pseudocode

```c
__int64 __fastcall BfeRpcFilterAdd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v8; // r12
  __int64 v9; // rbx
  __int64 *Value; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 result; // rax
  _DWORD *v15; // rdi
  int v16; // eax
  int v17; // edi
  int v18; // edx
  unsigned int v19; // esi
  __int64 v20; // r8
  BOOL v21; // edi
  __int64 v22; // rbx
  __int64 v23; // rax
  void *v24; // r8
  _DWORD *v25; // rsi
  int IsEnabledDeviceUsageInline; // eax
  int v27; // edi
  int v28; // edx
  unsigned int v29; // esi
  __int64 v30; // r8
  BOOL v31; // edi
  __int64 v32; // rcx
  _QWORD *v33; // rdi
  __int64 v34; // r8
  RPC_STATUS v35; // ecx
  int TickCount64; // edi
  RPC_STATUS v37; // eax
  __int64 v38; // r8
  _QWORD *v39; // [rsp+30h] [rbp-61h] BYREF
  __int64 v40; // [rsp+38h] [rbp-59h] BYREF
  _OWORD TlsValue[2]; // [rsp+40h] [rbp-51h] BYREF
  _BYTE v42[16]; // [rsp+60h] [rbp-31h] BYREF
  const char *v43; // [rsp+70h] [rbp-21h]
  __int64 v44; // [rsp+78h] [rbp-19h]
  _QWORD **v45; // [rsp+80h] [rbp-11h]
  __int64 v46; // [rsp+88h] [rbp-9h]

  v40 = 0;
  v39 = 0;
  v8 = 0;
  memset(TlsValue, 0, sizeof(TlsValue));
  if ( a1 )
    v40 = a3;
  v9 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( v9 )
    goto LABEL_12;
  Value = (__int64 *)TlsGetValue(gBfeContextComponent);
  if ( !Value || (v11 = *Value) == 0 || !*(_DWORD *)(v11 + 88) )
  {
    v9 = BfeFwpmFilterValidate(a3);
    if ( v9 )
      goto LABEL_60;
  }
  if ( !a1 )
  {
    v22 = *(_QWORD *)&MEMORY[0x1800EF094][7];
    if ( !*(_DWORD *)(*(_QWORD *)&MEMORY[0x1800EF094][7] + 2040LL) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v22 + 2072))(a3, &v40);
    v9 = v23;
    if ( v23 )
    {
      WfpReportError(v23, "BfeObjectCopyPublicState");
      goto LABEL_60;
    }
  }
  v24 = 0;
  if ( a4 && *(_DWORD *)a4 )
  {
    v9 = BfeRelativeSecurityDescriptorValidate(*(PSECURITY_DESCRIPTOR *)(a4 + 8), *(_DWORD *)a4);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v38, 0, (__int64)"BfeSecurityDescriptorDecode", v9);
      }
      if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
      {
        LODWORD(v39) = v9;
        v45 = &v39;
        v43 = "BfeSecurityDescriptorDecode";
        v44 = 28;
        v46 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v38,
          3,
          (__int64)v42);
      }
      goto LABEL_60;
    }
    v24 = *(void **)(a4 + 8);
  }
  v9 = BfeObjectAdd(5u, &v40, v24, &v39);
  if ( v9 )
  {
LABEL_60:
    if ( v40 )
      BfeObjectTraceAddFailure(5, v40);
    goto LABEL_12;
  }
  if ( *(_QWORD *)&TlsValue[0] && *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
  {
    v9 = 0;
  }
  else
  {
    v25 = (_DWORD *)*((_QWORD *)&TlsValue[0] + 1);
    v9 = 0;
    BfeTxnLockCancelLockTimeout();
    if ( !LODWORD(qword_1800F2668[201]) )
    {
      TickCount64 = GetTickCount64();
      v9 = BfeTxnCoordinatorCommit(0);
      LODWORD(qword_1800F2668[206]) = GetTickCount64() - TickCount64;
    }
    IsEnabledDeviceUsageInline = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
    *v25 = 0;
    if ( !IsEnabledDeviceUsageInline )
    {
      v27 = qword_1800F2668[205];
      v29 = GetTickCount64() - v27;
      if ( v29 >= HIDWORD(qword_1800F2668[203]) )
      {
        if ( (qword_1800F2668[337] & 0x20000000000LL) != 0 )
          McTemplateU0qqqq_EtwEventWriteTransfer(
            qword_1800F2668[206],
            v28,
            qword_1800F2668[204],
            v29,
            qword_1800F2668[206],
            SBYTE4(qword_1800F2668[203]));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_LLL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            v30,
            LODWORD(qword_1800F2668[204]),
            v29,
            qword_1800F2668[206]);
        }
      }
    }
    qword_1800F2668[200] = 0;
    v31 = ReleaseSemaphore((HANDLE)qword_1800F2668[199], 1, 0);
    if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v31 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( LODWORD(qword_1800F2668[197]) && !LODWORD(qword_1800F2668[201]) )
      BfeRundownState(v32);
    if ( v9 )
    {
      WfpReportError(v9, "BfeTxnCommit");
      *((_QWORD *)&TlsValue[0] + 1) = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v34, 0, (__int64)"BfeCallCommitEx", v9);
      }
      if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
      {
        LODWORD(v39) = v9;
        v45 = &v39;
        v43 = "BfeCallCommitEx";
        v44 = 16;
        v46 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v34,
          3,
          (__int64)v42);
      }
      goto LABEL_60;
    }
    *((_QWORD *)&TlsValue[0] + 1) = 0;
  }
  v33 = v39;
  if ( !v39 || !*v39 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !v33 || !*v33 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD *))(*v33 + 104LL))(v33 + 18);
LABEL_12:
  if ( *((_QWORD *)&TlsValue[0] + 1) )
  {
    if ( *(_QWORD *)&TlsValue[0] && *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
    {
      v12 = *(_QWORD *)&TlsValue[0] + 32LL;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)&TlsValue[0] + 32LL), 2, 1) == 3 )
        BfeTxnAbort(v12, 1);
    }
    else
    {
      v15 = (_DWORD *)*((_QWORD *)&TlsValue[0] + 1);
      BfeTxnLockCancelLockTimeout();
      if ( !LODWORD(qword_1800F2668[201]) )
        BfeTxnCoordinatorRollback();
      v16 = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
      *v15 = 0;
      if ( !v16 )
      {
        v17 = qword_1800F2668[205];
        v19 = GetTickCount64() - v17;
        if ( v19 >= HIDWORD(qword_1800F2668[203]) )
        {
          if ( (qword_1800F2668[337] & 0x20000000000LL) != 0 )
            McTemplateU0qqqq_EtwEventWriteTransfer(
              qword_1800F2668[206],
              v18,
              qword_1800F2668[204],
              v19,
              qword_1800F2668[206],
              SBYTE4(qword_1800F2668[203]));
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_LLL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              v20,
              LODWORD(qword_1800F2668[204]),
              v19,
              qword_1800F2668[206]);
          }
        }
      }
      qword_1800F2668[200] = 0;
      v21 = ReleaseSemaphore((HANDLE)qword_1800F2668[199], 1, 0);
      if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v21 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  TlsSetValue(gBfeContextComponent, 0);
  v13 = *(_QWORD *)&MEMORY[0x1800EF094][7];
  if ( !*(_DWORD *)(*(_QWORD *)&MEMORY[0x1800EF094][7] + 2040LL) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  (*(void (__fastcall **)(__int64 *))(v13 + 2080))(&v40);
  if ( a1 )
  {
    if ( v9 )
    {
      if ( !(unsigned int)BfeRpcIsKernelModeCaller() )
      {
        v35 = (unsigned __int16)v9;
        if ( (v9 & 0x1FFF0000) != 0x70000 )
          v35 = v9;
        RpcRaiseException(v35);
      }
      v37 = WfpErrorToNtStatus(v9);
      RpcRaiseException(v37);
    }
    result = 0;
    goto LABEL_23;
  }
  result = (unsigned __int16)v9;
  if ( (v9 & 0x1FFF0000) != 0x70000 )
    result = (unsigned int)v9;
  if ( !(_DWORD)result )
  {
LABEL_23:
    if ( a5 )
      *a5 = v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000a140  push    rbp
0x18000a142  push    rbx
0x18000a143  push    rsi
0x18000a144  push    rdi
0x18000a145  push    r12
0x18000a147  push    r13
0x18000a149  push    r14
0x18000a14b  push    r15
0x18000a14d  lea     rbp, [rsp-17h]
0x18000a152  sub     rsp, 0A8h
0x18000a159  mov     rax, cs:__security_cookie
0x18000a160  xor     rax, rsp
0x18000a163  mov     [rbp+4Fh+var_50], rax
0x18000a167  mov     r14, [rbp+4Fh+arg_20]
0x18000a16b  xor     r13d, r13d
0x18000a16e  mov     [rbp+4Fh+var_A8], r13
0x18000a172  xorps   xmm0, xmm0
0x18000a175  mov     [rbp+4Fh+var_B0], r13
0x18000a179  mov     rdi, r9
0x18000a17c  mov     rsi, r8
0x18000a17f  mov     r15, rcx
0x18000a182  mov     r12d, r13d
0x18000a185  movups  [rbp+4Fh+TlsValue], xmm0
0x18000a189  movups  [rbp+4Fh+var_90], xmm0
0x18000a18d  test    rcx, rcx
0x18000a190  jz      short loc_18000A196
0x18000a192  mov     [rbp+4Fh+var_A8], r8
0x18000a196  mov     r9d, 1; int
0x18000a19c  lea     rax, [rbp+4Fh+TlsValue]
0x18000a1a0  mov     r8d, r9d; int
0x18000a1a3  mov     [rsp+0E0h+lpTlsValue], rax; lpTlsValue
0x18000a1a8  call    BfeCallCreate
0x18000a1ad  mov     rbx, rax
0x18000a1b0  test    rax, rax
0x18000a1b3  jnz     short loc_18000A21E
0x18000a1b5  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000a1bb  call    cs:__imp_TlsGetValue
0x18000a1c1  test    rax, rax
0x18000a1c4  jz      short loc_18000A1D2
0x18000a1c6  mov     rax, [rax]
0x18000a1c9  test    rax, rax
0x18000a1cc  jnz     loc_18000A364
0x18000a1d2  mov     rcx, rsi
0x18000a1d5  call    BfeFwpmFilterValidate
0x18000a1da  mov     rbx, rax
0x18000a1dd  test    rax, rax
0x18000a1e0  jnz     loc_18000A4E0
0x18000a1e6  jmp     loc_18000A36E
0x18000a1eb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a1f0  test    rdi, rdi
0x18000a1f3  jz      short loc_18000A1FA
0x18000a1f5  cmp     [rdi], r13
0x18000a1f8  jnz     short loc_18000A1FF
0x18000a1fa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a1ff  mov     rax, [rdi]
0x18000a202  lea     rcx, [rdi+90h]
0x18000a209  mov     rax, [rax+68h]
0x18000a20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a212  mov     r12, rax
0x18000a215  test    rbx, rbx
0x18000a218  jnz     loc_18000A4E0
0x18000a21e  cmp     qword ptr [rbp+4Fh+TlsValue+8], r13
0x18000a222  jz      short loc_18000A258
0x18000a224  mov     rax, qword ptr [rbp+4Fh+TlsValue]
0x18000a228  test    rax, rax
0x18000a22b  jz      loc_18000A2D4
0x18000a231  cmp     [rax+24h], r13d
0x18000a235  jz      loc_18000A2D4
0x18000a23b  lea     rcx, [rax+20h]
0x18000a23f  mov     r8d, 2
0x18000a245  mov     eax, 1
0x18000a24a  lock cmpxchg [rcx], r8d
0x18000a24f  cmp     eax, 3
0x18000a252  jz      loc_18000A6E3
0x18000a258  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000a25e  xor     edx, edx; lpTlsValue
0x18000a260  call    cs:__imp_TlsSetValue
0x18000a266  mov     rdi, cs:1800EF0B0h
0x18000a26d  cmp     [rdi+7F8h], r13d
0x18000a274  jnz     short loc_18000A27B
0x18000a276  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a27b  mov     rax, [rdi+820h]
0x18000a282  lea     rcx, [rbp+4Fh+var_A8]
0x18000a286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a28b  test    r15, r15
0x18000a28e  jnz     loc_18000A353
0x18000a294  mov     ecx, ebx
0x18000a296  movzx   eax, bx
0x18000a299  and     ecx, 1FFF0000h
0x18000a29f  cmp     ecx, 70000h
0x18000a2a5  cmovnz  eax, ebx
0x18000a2a8  test    eax, eax
0x18000a2aa  jnz     short loc_18000A2B4
0x18000a2ac  test    r14, r14
0x18000a2af  jz      short loc_18000A2B4
0x18000a2b1  mov     [r14], r12
0x18000a2b4  mov     rcx, [rbp+4Fh+var_50]
0x18000a2b8  xor     rcx, rsp; StackCookie
0x18000a2bb  call    __security_check_cookie
0x18000a2c0  add     rsp, 0A8h
0x18000a2c7  pop     r15
0x18000a2c9  pop     r14
0x18000a2cb  pop     r13
0x18000a2cd  pop     r12
0x18000a2cf  pop     rdi
0x18000a2d0  pop     rsi
0x18000a2d1  pop     rbx
0x18000a2d2  pop     rbp
0x18000a2d3  retn
0x18000a2d4  mov     rdi, qword ptr [rbp+4Fh+TlsValue+8]
0x18000a2d8  call    BfeTxnLockCancelLockTimeout
0x18000a2dd  cmp     dword ptr cs:qword_1800F2668+648h, r13d
0x18000a2e4  jnz     short loc_18000A2EB
0x18000a2e6  call    BfeTxnCoordinatorRollback
0x18000a2eb  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000a2f0  mov     [rdi], r13d
0x18000a2f3  test    eax, eax
0x18000a2f5  jnz     short loc_18000A316
0x18000a2f7  mov     edi, dword ptr cs:qword_1800F2668+668h
0x18000a2fd  call    cs:__imp_GetTickCount64
0x18000a303  mov     rsi, rax
0x18000a306  mov     eax, dword ptr cs:qword_1800F2668+65Ch
0x18000a30c  sub     esi, edi
0x18000a30e  cmp     esi, eax
0x18000a310  jnb     loc_18000A6F2
0x18000a316  mov     rcx, cs:qword_1800F2668+638h; hSemaphore
0x18000a31d  xor     r8d, r8d; lpPreviousCount
0x18000a320  mov     edx, 1; lReleaseCount
0x18000a325  mov     cs:qword_1800F2668+640h, r13
0x18000a32c  call    cs:__imp_ReleaseSemaphore
0x18000a332  mov     edi, eax
0x18000a334  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000a339  test    eax, eax
0x18000a33b  jz      loc_18000A258
0x18000a341  test    edi, edi
0x18000a343  jnz     loc_18000A258
0x18000a349  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a34e  jmp     loc_18000A258
0x18000a353  test    rbx, rbx
0x18000a356  jnz     loc_18000A548
0x18000a35c  mov     eax, r13d
0x18000a35f  jmp     loc_18000A2AC
0x18000a364  cmp     [rax+58h], r13d
0x18000a368  jz      loc_18000A1D2
0x18000a36e  test    r15, r15
0x18000a371  jnz     short loc_18000A3A7
0x18000a373  mov     rbx, cs:1800EF0B0h
0x18000a37a  cmp     [rbx+7F8h], r13d
0x18000a381  jnz     short loc_18000A388
0x18000a383  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a388  mov     rax, [rbx+818h]
0x18000a38f  lea     rdx, [rbp+4Fh+var_A8]
0x18000a393  mov     rcx, rsi
0x18000a396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a39b  mov     rbx, rax
0x18000a39e  test    rax, rax
0x18000a3a1  jnz     loc_18000A684
0x18000a3a7  mov     r8, r13
0x18000a3aa  test    rdi, rdi
0x18000a3ad  jnz     loc_18000A675
0x18000a3b3  lea     r9, [rbp+4Fh+var_B0]
0x18000a3b7  mov     ecx, 5
0x18000a3bc  lea     rdx, [rbp+4Fh+var_A8]
0x18000a3c0  call    BfeObjectAdd
0x18000a3c5  mov     rbx, rax
0x18000a3c8  test    rax, rax
0x18000a3cb  jnz     loc_18000A4E0
0x18000a3d1  mov     rax, qword ptr [rbp+4Fh+TlsValue]
0x18000a3d5  test    rax, rax
0x18000a3d8  jz      short loc_18000A3E4
0x18000a3da  cmp     [rax+24h], r13d
0x18000a3de  jnz     loc_18000A590
0x18000a3e4  mov     rsi, qword ptr [rbp+4Fh+TlsValue+8]
0x18000a3e8  mov     rbx, r13
0x18000a3eb  call    BfeTxnLockCancelLockTimeout
0x18000a3f0  cmp     dword ptr cs:qword_1800F2668+648h, r13d
0x18000a3f7  jz      loc_18000A56A
0x18000a3fd  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000a402  mov     [rsi], r13d
0x18000a405  test    eax, eax
0x18000a407  jnz     short loc_18000A428
0x18000a409  mov     edi, dword ptr cs:qword_1800F2668+668h
0x18000a40f  call    cs:__imp_GetTickCount64
0x18000a415  mov     rsi, rax
0x18000a418  mov     eax, dword ptr cs:qword_1800F2668+65Ch
0x18000a41e  sub     esi, edi
0x18000a420  cmp     esi, eax
0x18000a422  jnb     loc_18000A6A1
0x18000a428  mov     rcx, cs:qword_1800F2668+638h; hSemaphore
0x18000a42f  xor     r8d, r8d; lpPreviousCount
0x18000a432  mov     edx, 1; lReleaseCount
0x18000a437  mov     cs:qword_1800F2668+640h, r13
0x18000a43e  call    cs:__imp_ReleaseSemaphore
0x18000a444  mov     edi, eax
0x18000a446  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000a44b  test    eax, eax
0x18000a44d  jnz     loc_18000A6D1
0x18000a453  cmp     dword ptr cs:qword_1800F2668+628h, r13d
0x18000a45a  jnz     loc_18000A598
0x18000a460  test    rbx, rbx
0x18000a463  jnz     short loc_18000A484
0x18000a465  mov     qword ptr [rbp+4Fh+TlsValue+8], r13
0x18000a469  mov     rdi, [rbp+4Fh+var_B0]
0x18000a46d  test    rdi, rdi
0x18000a470  jz      loc_18000A1EB
0x18000a476  cmp     [rdi], r13
0x18000a479  jz      loc_18000A1EB
0x18000a47f  jmp     loc_18000A1FF
0x18000a484  lea     rdx, aBfetxncommit; "BfeTxnCommit"
0x18000a48b  mov     rcx, rbx
0x18000a48e  call    WfpReportError
0x18000a493  mov     qword ptr [rbp+4Fh+TlsValue+8], r13
0x18000a497  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a49e  lea     rax, WPP_GLOBAL_Control
0x18000a4a5  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x18000a4ac  cmp     rcx, rax
0x18000a4af  jz      short loc_18000A4D7
0x18000a4b1  cmp     byte ptr [rcx+19h], 2
0x18000a4b5  jb      short loc_18000A4D7
0x18000a4b7  test    byte ptr [rcx+1Ch], 1
0x18000a4bb  jz      short loc_18000A4D7
0x18000a4bd  mov     rcx, [rcx+10h]
0x18000a4c1  mov     edx, 1Ah
0x18000a4c6  mov     [rsp+0E0h+var_B8], ebx
0x18000a4ca  xor     r9d, r9d
0x18000a4cd  mov     [rsp+0E0h+lpTlsValue], rdi
0x18000a4d2  call    WPP_SF_Ssd
0x18000a4d7  cmp     cs:1800EF078h, r13d
0x18000a4de  jnz     short loc_18000A4FC
0x18000a4e0  mov     rdx, [rbp+4Fh+var_A8]
0x18000a4e4  test    rdx, rdx
0x18000a4e7  jz      loc_18000A21E
0x18000a4ed  mov     ecx, 5
0x18000a4f2  call    BfeObjectTraceAddFailure
0x18000a4f7  jmp     loc_18000A21E
0x18000a4fc  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x18000a503  jz      short loc_18000A4E0
0x18000a505  lea     rax, [rbp+4Fh+var_B0]
0x18000a509  mov     dword ptr [rbp+4Fh+var_B0], ebx
0x18000a50c  mov     [rbp+4Fh+var_60], rax
0x18000a510  lea     rdx, WFP_USERMODE_ERROR
0x18000a517  lea     rax, [rbp+4Fh+var_80]
0x18000a51b  mov     [rbp+4Fh+var_70], rdi
0x18000a51f  mov     r9d, 3
0x18000a525  mov     [rsp+0E0h+lpTlsValue], rax
0x18000a52a  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000a531  mov     [rbp+4Fh+var_68], 10h
0x18000a539  mov     [rbp+4Fh+var_58], 4
0x18000a541  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a546  jmp     short loc_18000A4E0
0x18000a548  call    BfeRpcIsKernelModeCaller
0x18000a54d  test    eax, eax
0x18000a54f  jnz     short loc_18000A5AF
0x18000a551  mov     eax, ebx
0x18000a553  movzx   ecx, bx
0x18000a556  and     eax, 1FFF0000h
0x18000a55b  cmp     eax, 70000h
0x18000a560  cmovnz  ecx, ebx; exception
0x18000a563  call    cs:__imp_RpcRaiseException
0x18000a569  int     3; Trap to Debugger
0x18000a56a  call    cs:__imp_GetTickCount64
0x18000a570  xor     ecx, ecx
0x18000a572  mov     rdi, rax
0x18000a575  call    BfeTxnCoordinatorCommit
0x18000a57a  mov     rbx, rax
0x18000a57d  call    cs:__imp_GetTickCount64
0x18000a583  sub     eax, edi
0x18000a585  mov     dword ptr cs:qword_1800F2668+670h, eax
0x18000a58b  jmp     loc_18000A3FD
0x18000a590  mov     rbx, r13
0x18000a593  jmp     loc_18000A469
0x18000a598  cmp     dword ptr cs:qword_1800F2668+648h, r13d
0x18000a59f  jnz     loc_18000A460
0x18000a5a5  call    BfeRundownState
0x18000a5aa  jmp     loc_18000A460
0x18000a5af  mov     rcx, rbx
0x18000a5b2  call    WfpErrorToNtStatus
0x18000a5b7  mov     ecx, eax; exception
0x18000a5b9  call    cs:__imp_RpcRaiseException
0x18000a5bf  int     3; Trap to Debugger
0x18000a5c0  mov     rcx, [rdi+8]; SecurityDescriptor
0x18000a5c4  call    BfeRelativeSecurityDescriptorValidate
0x18000a5c9  mov     rbx, rax
0x18000a5cc  test    rax, rax
0x18000a5cf  jz      loc_18000A698
0x18000a5d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5dc  lea     rax, WPP_GLOBAL_Control
0x18000a5e3  lea     rdi, aBfesecuritydes_0; "BfeSecurityDescriptorDecode"
0x18000a5ea  cmp     rcx, rax
0x18000a5ed  jz      short loc_18000A615
0x18000a5ef  cmp     byte ptr [rcx+19h], 2
0x18000a5f3  jb      short loc_18000A615
0x18000a5f5  test    byte ptr [rcx+1Ch], 1
0x18000a5f9  jz      short loc_18000A615
0x18000a5fb  mov     rcx, [rcx+10h]
0x18000a5ff  mov     edx, 1Ah
0x18000a604  mov     [rsp+0E0h+var_B8], ebx
0x18000a608  xor     r9d, r9d
0x18000a60b  mov     [rsp+0E0h+lpTlsValue], rdi
0x18000a610  call    WPP_SF_Ssd
  ... truncated ...
```
