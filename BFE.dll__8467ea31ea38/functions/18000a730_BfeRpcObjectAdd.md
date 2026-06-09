# BfeRpcObjectAdd

- ea: `0x18000a730`
- end: `0x18000ad1f`
- name: `BfeRpcObjectAdd`
- size: `1519`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64 (__fastcall *)(__int64), __int64, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003fe40`
- `0x180041370`
- `0x180045c70`

## callees

- `0x1800060a8`
- `0x18000864c`
- `0x180008694`
- `0x1800087a0`
- `0x18000a730`
- `0x18000ad28`
- `0x18000aef4`
- `0x18000f1a8`
- `0x180010ad0`
- `0x180018b74`
- `0x1800223a8`
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

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a930`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000aad1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a930`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000aad1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a7af`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a7af`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a863`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a863`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a8fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000aa97`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ab9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000abad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a8fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000aa97`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ab9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000abad`
- `RPCRT4!RpcRaiseException` at `0x18000ab93`
- `RPCRT4!RpcRaiseException` at `0x18000abef`
- `RPCRT4!RpcRaiseException` at `0x18000ab93`
- `RPCRT4!RpcRaiseException` at `0x18000abef`

## string_xrefs

- `0x18000ac19`: `BfeSecurityDescriptorDecode`
- `0x18000a9ff`: `BfeCallCommitEx`
- `0x18000a9e1`: `BfeTxnCommit`
- `0x18000ac81`: `BfeObjectCopyPublicState`

## pseudocode

```c
__int64 __fastcall BfeRpcObjectAdd(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 (__fastcall *a4)(__int64),
        __int64 a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v8; // r14
  __int64 v10; // rbx
  __int64 *Value; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 result; // rax
  _DWORD *v16; // rdi
  int v17; // eax
  int v18; // edi
  int v19; // edx
  unsigned int v20; // esi
  __int64 v21; // r8
  BOOL v22; // edi
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // r8
  int v26; // r8d
  const char *v27; // rdi
  _DWORD *v28; // rsi
  int IsEnabledDeviceUsageInline; // eax
  int v30; // edi
  int v31; // edx
  unsigned int v32; // esi
  __int64 v33; // r8
  BOOL v34; // edi
  _QWORD *v35; // rdi
  RPC_STATUS v36; // ecx
  int TickCount64; // edi
  RPC_STATUS v38; // eax
  __int64 v39; // rax
  _QWORD *v40; // [rsp+30h] [rbp-71h] BYREF
  __int64 v41; // [rsp+38h] [rbp-69h] BYREF
  _OWORD TlsValue[2]; // [rsp+40h] [rbp-61h] BYREF
  char v43[16]; // [rsp+60h] [rbp-41h] BYREF
  const char *v44; // [rsp+70h] [rbp-31h]
  __int64 v45; // [rsp+78h] [rbp-29h]
  _QWORD **v46; // [rsp+80h] [rbp-21h]
  __int64 v47; // [rsp+88h] [rbp-19h]

  v8 = a3;
  v41 = 0;
  v40 = 0;
  memset(TlsValue, 0, sizeof(TlsValue));
  if ( a1 )
    v41 = a5;
  v10 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( !v10 )
  {
    Value = (__int64 *)TlsGetValue(gBfeContextComponent);
    if ( !Value || (v12 = *Value) == 0 || !*(_DWORD *)(v12 + 88) )
    {
      v10 = a4(a5);
      if ( v10 )
        goto LABEL_48;
    }
    if ( !a1 )
    {
      v23 = gBfeObjMgr + 408 * v8;
      if ( (unsigned int)v8 >= 7 || !*(_DWORD *)v23 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v23 + 32))(a5, &v41);
      v10 = v24;
      if ( v24 )
      {
        WfpReportError(v24, "BfeObjectCopyPublicState");
        goto LABEL_48;
      }
    }
    v25 = 0;
    if ( a6 && *(_DWORD *)a6 )
    {
      v39 = BfeRelativeSecurityDescriptorValidate(*(PSECURITY_DESCRIPTOR *)(a6 + 8));
      v10 = v39;
      if ( v39 )
      {
        v27 = "BfeSecurityDescriptorDecode";
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v26, 0, (__int64)"BfeSecurityDescriptorDecode", v39);
        }
        if ( !gWfpLogUserModeErrors || (byte_1800F30F5 & 1) == 0 )
          goto LABEL_48;
        v45 = 28;
        goto LABEL_66;
      }
      v25 = *(_QWORD *)(a6 + 8);
    }
    v10 = BfeObjectAdd((unsigned int)v8, &v41, v25, &v40);
    if ( v10 )
    {
LABEL_48:
      if ( v41 )
        BfeObjectTraceAddFailure((unsigned int)v8);
      goto LABEL_13;
    }
    if ( *(_QWORD *)&TlsValue[0] && *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
    {
      v10 = 0;
    }
    else
    {
      v28 = (_DWORD *)*((_QWORD *)&TlsValue[0] + 1);
      v10 = 0;
      BfeTxnLockCancelLockTimeout();
      if ( !dword_1800F2CB0 )
      {
        TickCount64 = GetTickCount64();
        v10 = BfeTxnCoordinatorCommit(0);
        dword_1800F2CD8 = GetTickCount64() - TickCount64;
      }
      IsEnabledDeviceUsageInline = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
      *v28 = 0;
      if ( !IsEnabledDeviceUsageInline )
      {
        v30 = qword_1800F2CD0;
        v32 = GetTickCount64() - v30;
        if ( v32 >= dword_1800F2CC4 )
        {
          if ( (byte_1800F30F5 & 2) != 0 )
            McTemplateU0qqqq_EtwEventWriteTransfer(
              dword_1800F2CD8,
              v31,
              dword_1800F2CC8,
              v32,
              dword_1800F2CD8,
              dword_1800F2CC4);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_LLL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              v33,
              (unsigned int)dword_1800F2CC8,
              v32,
              dword_1800F2CD8);
          }
        }
      }
      qword_1800F2CA8 = 0;
      v34 = ReleaseSemaphore(gBfeTxnComponent, 1, 0);
      if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v34 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( gBfePeriodicRundownEnabled && !dword_1800F2CB0 )
        BfeRundownState();
      if ( v10 )
      {
        WfpReportError(v10, "BfeTxnCommit");
        *((_QWORD *)&TlsValue[0] + 1) = 0;
        v27 = "BfeCallCommitEx";
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v26, 0, (__int64)"BfeCallCommitEx", v10);
        }
        if ( !gWfpLogUserModeErrors || (byte_1800F30F5 & 1) == 0 )
          goto LABEL_48;
        v45 = 16;
LABEL_66:
        v44 = v27;
        v46 = &v40;
        LODWORD(v40) = v10;
        v47 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
          (unsigned int)WFP_USERMODE_ERROR,
          v26,
          3,
          (__int64)v43);
        goto LABEL_48;
      }
      *((_QWORD *)&TlsValue[0] + 1) = 0;
    }
    if ( a7 )
    {
      v35 = v40;
      if ( !v40 || !*v40 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( !v35 || !*v35 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      *a7 = (*(__int64 (__fastcall **)(_QWORD *))(*v35 + 104LL))(v35 + 18);
    }
  }
LABEL_13:
  if ( *((_QWORD *)&TlsValue[0] + 1) )
  {
    if ( *(_QWORD *)&TlsValue[0] && *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
    {
      v13 = *(_QWORD *)&TlsValue[0] + 32LL;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)&TlsValue[0] + 32LL), 2, 1) == 3 )
        BfeTxnAbort(v13, 1);
    }
    else
    {
      v16 = (_DWORD *)*((_QWORD *)&TlsValue[0] + 1);
      BfeTxnLockCancelLockTimeout();
      if ( !dword_1800F2CB0 )
        BfeTxnCoordinatorRollback();
      v17 = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
      *v16 = 0;
      if ( !v17 )
      {
        v18 = qword_1800F2CD0;
        v20 = GetTickCount64() - v18;
        if ( v20 >= dword_1800F2CC4 )
        {
          if ( (byte_1800F30F5 & 2) != 0 )
            McTemplateU0qqqq_EtwEventWriteTransfer(
              dword_1800F2CD8,
              v19,
              dword_1800F2CC8,
              v20,
              dword_1800F2CD8,
              dword_1800F2CC4);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_LLL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              v21,
              (unsigned int)dword_1800F2CC8,
              v20,
              dword_1800F2CD8);
          }
        }
      }
      qword_1800F2CA8 = 0;
      v22 = ReleaseSemaphore(gBfeTxnComponent, 1, 0);
      if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v22 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  TlsSetValue(gBfeContextComponent, 0);
  v14 = gBfeObjMgr + 408 * v8;
  if ( (unsigned int)v8 >= 7 || !*(_DWORD *)v14 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  (*(void (__fastcall **)(__int64 *))(v14 + 40))(&v41);
  if ( a1 )
  {
    if ( v10 )
    {
      if ( !(unsigned int)BfeRpcIsKernelModeCaller() )
      {
        v36 = (unsigned __int16)v10;
        if ( (v10 & 0x1FFF0000) != 0x70000 )
          v36 = v10;
        RpcRaiseException(v36);
      }
      v38 = WfpErrorToNtStatus(v10);
      RpcRaiseException(v38);
    }
    return 0;
  }
  else
  {
    result = (unsigned __int16)v10;
    if ( (v10 & 0x1FFF0000) != 0x70000 )
      return (unsigned int)v10;
  }
  return result;
}

```

## disassembly

```asm
0x18000a730  push    rbp
0x18000a732  push    rbx
0x18000a733  push    rsi
0x18000a734  push    rdi
0x18000a735  push    r12
0x18000a737  push    r13
0x18000a739  push    r14
0x18000a73b  push    r15
0x18000a73d  lea     rbp, [rsp-7]
0x18000a742  sub     rsp, 0A8h
0x18000a749  mov     rax, cs:__security_cookie
0x18000a750  xor     rax, rsp
0x18000a753  mov     [rbp+3Fh+var_50], rax
0x18000a757  mov     rdi, [rbp+3Fh+arg_28]
0x18000a75b  xor     eax, eax
0x18000a75d  mov     rsi, [rbp+3Fh+arg_20]
0x18000a761  xorps   xmm0, xmm0
0x18000a764  mov     r12, [rbp+3Fh+arg_30]
0x18000a768  mov     r15, r9
0x18000a76b  movsxd  r14, r8d
0x18000a76e  mov     r13, rcx
0x18000a771  mov     [rbp+3Fh+var_A8], rax
0x18000a775  mov     [rbp+3Fh+var_B0], rax
0x18000a779  movups  [rbp+3Fh+TlsValue], xmm0
0x18000a77d  movups  [rbp+3Fh+var_90], xmm0
0x18000a781  test    rcx, rcx
0x18000a784  jz      short loc_18000A78A
0x18000a786  mov     [rbp+3Fh+var_A8], rsi
0x18000a78a  mov     r9d, 1; int
0x18000a790  lea     rax, [rbp+3Fh+TlsValue]
0x18000a794  mov     r8d, r9d; int
0x18000a797  mov     [rsp+0E0h+lpTlsValue], rax; lpTlsValue
0x18000a79c  call    BfeCallCreate
0x18000a7a1  mov     rbx, rax
0x18000a7a4  test    rax, rax
0x18000a7a7  jnz     short loc_18000A7E2
0x18000a7a9  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000a7af  call    cs:__imp_TlsGetValue
0x18000a7b5  test    rax, rax
0x18000a7b8  jz      short loc_18000A7C6
0x18000a7ba  mov     rax, [rax]
0x18000a7bd  test    rax, rax
0x18000a7c0  jnz     loc_18000A967
0x18000a7c6  mov     rcx, rsi
0x18000a7c9  mov     rax, r15
0x18000a7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d1  mov     rbx, rax
0x18000a7d4  test    rax, rax
0x18000a7d7  jnz     loc_18000A9D8
0x18000a7dd  jmp     loc_18000A971
0x18000a7e2  lea     r15, WPP_GLOBAL_Control
0x18000a7e9  jmp     short loc_18000A820
0x18000a7eb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a7f0  test    rdi, rdi
0x18000a7f3  jz      short loc_18000A7FB
0x18000a7f5  cmp     qword ptr [rdi], 0
0x18000a7f9  jnz     short loc_18000A800
0x18000a7fb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a800  mov     rax, [rdi]
0x18000a803  lea     rcx, [rdi+90h]
0x18000a80a  mov     rax, [rax+68h]
0x18000a80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a813  mov     [r12], rax
0x18000a817  test    rbx, rbx
0x18000a81a  jnz     loc_18000AA3E
0x18000a820  cmp     qword ptr [rbp+3Fh+TlsValue+8], 0
0x18000a825  jz      short loc_18000A85B
0x18000a827  mov     rax, qword ptr [rbp+3Fh+TlsValue]
0x18000a82b  test    rax, rax
0x18000a82e  jz      loc_18000A8D1
0x18000a834  cmp     dword ptr [rax+24h], 0
0x18000a838  jz      loc_18000A8D1
0x18000a83e  lea     rcx, [rax+20h]
0x18000a842  mov     r8d, 2
0x18000a848  mov     eax, 1
0x18000a84d  lock cmpxchg [rcx], r8d
0x18000a852  cmp     eax, 3
0x18000a855  jz      loc_18000ACE0
0x18000a85b  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000a861  xor     edx, edx; lpTlsValue
0x18000a863  call    cs:__imp_TlsSetValue
0x18000a869  imul    rdi, r14, 198h
0x18000a870  add     rdi, cs:gBfeObjMgr
0x18000a877  cmp     r14d, 7
0x18000a87b  jnb     short loc_18000A882
0x18000a87d  cmp     dword ptr [rdi], 0
0x18000a880  jnz     short loc_18000A887
0x18000a882  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a887  mov     rax, [rdi+28h]
0x18000a88b  lea     rcx, [rbp+3Fh+var_A8]
0x18000a88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a894  test    r13, r13
0x18000a897  jnz     loc_18000A957
0x18000a89d  mov     ecx, ebx
0x18000a89f  movzx   eax, bx
0x18000a8a2  and     ecx, 1FFF0000h
0x18000a8a8  cmp     ecx, 70000h
0x18000a8ae  cmovnz  eax, ebx
0x18000a8b1  mov     rcx, [rbp+3Fh+var_50]
0x18000a8b5  xor     rcx, rsp; StackCookie
0x18000a8b8  call    __security_check_cookie
0x18000a8bd  add     rsp, 0A8h
0x18000a8c4  pop     r15
0x18000a8c6  pop     r14
0x18000a8c8  pop     r13
0x18000a8ca  pop     r12
0x18000a8cc  pop     rdi
0x18000a8cd  pop     rsi
0x18000a8ce  pop     rbx
0x18000a8cf  pop     rbp
0x18000a8d0  retn
0x18000a8d1  mov     rdi, qword ptr [rbp+3Fh+TlsValue+8]
0x18000a8d5  call    BfeTxnLockCancelLockTimeout
0x18000a8da  cmp     cs:dword_1800F2CB0, 0
0x18000a8e1  jnz     short loc_18000A8E8
0x18000a8e3  call    BfeTxnCoordinatorRollback
0x18000a8e8  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000a8ed  mov     dword ptr [rdi], 0
0x18000a8f3  test    eax, eax
0x18000a8f5  jnz     short loc_18000A916
0x18000a8f7  mov     edi, dword ptr cs:qword_1800F2CD0
0x18000a8fd  call    cs:__imp_GetTickCount64
0x18000a903  mov     rsi, rax
0x18000a906  mov     eax, cs:dword_1800F2CC4
0x18000a90c  sub     esi, edi
0x18000a90e  cmp     esi, eax
0x18000a910  jnb     loc_18000ACEF
0x18000a916  mov     rcx, cs:gBfeTxnComponent; hSemaphore
0x18000a91d  xor     r8d, r8d; lpPreviousCount
0x18000a920  mov     edx, 1; lReleaseCount
0x18000a925  mov     cs:qword_1800F2CA8, 0
0x18000a930  call    cs:__imp_ReleaseSemaphore
0x18000a936  mov     edi, eax
0x18000a938  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000a93d  test    eax, eax
0x18000a93f  jz      loc_18000A85B
0x18000a945  test    edi, edi
0x18000a947  jnz     loc_18000A85B
0x18000a94d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a952  jmp     loc_18000A85B
0x18000a957  test    rbx, rbx
0x18000a95a  jnz     loc_18000AB78
0x18000a960  xor     eax, eax
0x18000a962  jmp     loc_18000A8B1
0x18000a967  cmp     dword ptr [rax+58h], 0
0x18000a96b  jz      loc_18000A7C6
0x18000a971  test    r13, r13
0x18000a974  jnz     short loc_18000A9B0
0x18000a976  imul    rbx, r14, 198h
0x18000a97d  add     rbx, cs:gBfeObjMgr
0x18000a984  cmp     r14d, 7
0x18000a988  jnb     short loc_18000A98F
0x18000a98a  cmp     [rbx], r13d
0x18000a98d  jnz     short loc_18000A994
0x18000a98f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a994  mov     rax, [rbx+20h]
0x18000a998  lea     rdx, [rbp+3Fh+var_A8]
0x18000a99c  mov     rcx, rsi
0x18000a99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9a4  mov     rbx, rax
0x18000a9a7  test    rax, rax
0x18000a9aa  jnz     loc_18000AC81
0x18000a9b0  xor     r8d, r8d
0x18000a9b3  test    rdi, rdi
0x18000a9b6  jnz     loc_18000AC72
0x18000a9bc  lea     r9, [rbp+3Fh+var_B0]
0x18000a9c0  mov     ecx, r14d
0x18000a9c3  lea     rdx, [rbp+3Fh+var_A8]
0x18000a9c7  call    BfeObjectAdd
0x18000a9cc  mov     rbx, rax
0x18000a9cf  test    rax, rax
0x18000a9d2  jz      loc_18000AA58
0x18000a9d8  lea     r15, WPP_GLOBAL_Control
0x18000a9df  jmp     short loc_18000AA3E
0x18000a9e1  lea     rdx, aBfetxncommit; "BfeTxnCommit"
0x18000a9e8  mov     rcx, rbx
0x18000a9eb  call    WfpReportError
0x18000a9f0  mov     qword ptr [rbp+3Fh+TlsValue+8], 0
0x18000a9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9ff  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x18000aa06  cmp     rcx, r15
0x18000aa09  jz      short loc_18000AA31
0x18000aa0b  cmp     byte ptr [rcx+19h], 2
0x18000aa0f  jb      short loc_18000AA31
0x18000aa11  test    byte ptr [rcx+1Ch], 1
0x18000aa15  jz      short loc_18000AA31
0x18000aa17  mov     rcx, [rcx+10h]
0x18000aa1b  mov     edx, 1Ah
0x18000aa20  mov     [rsp+0E0h+var_B8], ebx
0x18000aa24  xor     r9d, r9d
0x18000aa27  mov     [rsp+0E0h+lpTlsValue], rdi
0x18000aa2c  call    WPP_SF_Ssd
0x18000aa31  cmp     cs:gWfpLogUserModeErrors, 0
0x18000aa38  jnz     loc_18000AB25
0x18000aa3e  mov     rdx, [rbp+3Fh+var_A8]
0x18000aa42  test    rdx, rdx
0x18000aa45  jz      loc_18000A820
0x18000aa4b  mov     ecx, r14d
0x18000aa4e  call    BfeObjectTraceAddFailure
0x18000aa53  jmp     loc_18000A820
0x18000aa58  mov     rax, qword ptr [rbp+3Fh+TlsValue]
0x18000aa5c  test    rax, rax
0x18000aa5f  jz      short loc_18000AA6B
0x18000aa61  cmp     dword ptr [rax+24h], 0
0x18000aa65  jnz     loc_18000ABC0
0x18000aa6b  mov     rsi, qword ptr [rbp+3Fh+TlsValue+8]
0x18000aa6f  xor     ebx, ebx
0x18000aa71  call    BfeTxnLockCancelLockTimeout
0x18000aa76  cmp     cs:dword_1800F2CB0, ebx
0x18000aa7c  jz      loc_18000AB9A
0x18000aa82  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000aa87  mov     dword ptr [rsi], 0
0x18000aa8d  test    eax, eax
0x18000aa8f  jnz     short loc_18000AAB0
0x18000aa91  mov     edi, dword ptr cs:qword_1800F2CD0
0x18000aa97  call    cs:__imp_GetTickCount64
0x18000aa9d  mov     rsi, rax
0x18000aaa0  mov     eax, cs:dword_1800F2CC4
0x18000aaa6  sub     esi, edi
0x18000aaa8  cmp     esi, eax
0x18000aaaa  jnb     loc_18000AC9E
0x18000aab0  lea     r15, WPP_GLOBAL_Control
0x18000aab7  mov     rcx, cs:gBfeTxnComponent; hSemaphore
0x18000aabe  xor     r8d, r8d; lpPreviousCount
0x18000aac1  mov     edx, 1; lReleaseCount
0x18000aac6  mov     cs:qword_1800F2CA8, 0
0x18000aad1  call    cs:__imp_ReleaseSemaphore
0x18000aad7  mov     edi, eax
0x18000aad9  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000aade  test    eax, eax
0x18000aae0  jnz     loc_18000ACCE
0x18000aae6  cmp     cs:gBfePeriodicRundownEnabled, 0
0x18000aaed  jnz     loc_18000ABCE
0x18000aaf3  test    rbx, rbx
0x18000aaf6  jnz     loc_18000A9E1
0x18000aafc  mov     qword ptr [rbp+3Fh+TlsValue+8], rbx
0x18000ab00  test    r12, r12
0x18000ab03  jz      loc_18000A820
0x18000ab09  mov     rdi, [rbp+3Fh+var_B0]
0x18000ab0d  test    rdi, rdi
0x18000ab10  jz      loc_18000A7EB
0x18000ab16  cmp     qword ptr [rdi], 0
0x18000ab1a  jz      loc_18000A7EB
0x18000ab20  jmp     loc_18000A800
0x18000ab25  test    cs:byte_1800F30F5, 1
0x18000ab2c  jz      loc_18000AA3E
0x18000ab32  mov     [rbp+3Fh+var_68], 10h
0x18000ab3a  lea     rax, [rbp+3Fh+var_B0]
0x18000ab3e  mov     [rbp+3Fh+var_70], rdi
0x18000ab42  mov     [rbp+3Fh+var_60], rax
0x18000ab46  lea     rdx, WFP_USERMODE_ERROR
0x18000ab4d  lea     rax, [rbp+3Fh+var_80]
0x18000ab51  mov     dword ptr [rbp+3Fh+var_B0], ebx
0x18000ab54  mov     r9d, 3
0x18000ab5a  mov     [rsp+0E0h+lpTlsValue], rax
0x18000ab5f  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000ab66  mov     [rbp+3Fh+var_58], 4
0x18000ab6e  call    McGenEventWrite_EtwEventWriteTransfer
0x18000ab73  jmp     loc_18000AA3E
0x18000ab78  call    BfeRpcIsKernelModeCaller
0x18000ab7d  test    eax, eax
0x18000ab7f  jnz     short loc_18000ABE5
0x18000ab81  mov     eax, ebx
0x18000ab83  movzx   ecx, bx
0x18000ab86  and     eax, 1FFF0000h
0x18000ab8b  cmp     eax, 70000h
0x18000ab90  cmovnz  ecx, ebx; exception
0x18000ab93  call    cs:__imp_RpcRaiseException
0x18000ab99  int     3; Trap to Debugger
0x18000ab9a  call    cs:__imp_GetTickCount64
0x18000aba0  xor     ecx, ecx
0x18000aba2  mov     rdi, rax
0x18000aba5  call    BfeTxnCoordinatorCommit
0x18000abaa  mov     rbx, rax
0x18000abad  call    cs:__imp_GetTickCount64
0x18000abb3  sub     eax, edi
0x18000abb5  mov     cs:dword_1800F2CD8, eax
0x18000abbb  jmp     loc_18000AA82
0x18000abc0  xor     ebx, ebx
0x18000abc2  lea     r15, WPP_GLOBAL_Control
0x18000abc9  jmp     loc_18000AB00
0x18000abce  cmp     cs:dword_1800F2CB0, 0
0x18000abd5  jnz     loc_18000AAF3
0x18000abdb  call    BfeRundownState
0x18000abe0  jmp     loc_18000AAF3
0x18000abe5  mov     rcx, rbx
0x18000abe8  call    WfpErrorToNtStatus
0x18000abed  mov     ecx, eax; exception
0x18000abef  call    cs:__imp_RpcRaiseException
0x18000abf5  int     3; Trap to Debugger
0x18000abf6  mov     rcx, [rdi+8]; SecurityDescriptor
0x18000abfa  call    BfeRelativeSecurityDescriptorValidate
0x18000abff  mov     rbx, rax
0x18000ac02  test    rax, rax
0x18000ac05  jz      loc_18000AC95
0x18000ac0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac12  lea     r15, WPP_GLOBAL_Control
0x18000ac19  lea     rdi, aBfesecuritydes_0; "BfeSecurityDescriptorDecode"
0x18000ac20  cmp     rcx, r15
0x18000ac23  jz      short loc_18000AC4B
  ... truncated ...
```
