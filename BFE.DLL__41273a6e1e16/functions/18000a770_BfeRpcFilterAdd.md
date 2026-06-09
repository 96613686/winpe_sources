# BfeRpcFilterAdd

- ea: `0x18000a770`
- end: `0x18000ad8f`
- name: `BfeRpcFilterAdd`
- size: `1567`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180006584`
- `0x180008c5c`
- `0x180008ca8`
- `0x180008dd0`
- `0x18000a770`
- `0x18000b3d4`
- `0x18000b5b4`
- `0x18000fb34`
- `0x180011510`
- `0x1800197d0`
- `0x180024ab0`
- `0x180024f20`
- `0x18002681c`
- `0x180026a1c`
- `0x18003576c`
- `0x1800408e4`
- `0x180044954`
- `0x1800572ec`
- `0x1800592f4`
- `0x18005aa60`
- `0x180076208`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a96f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000aa8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a96f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000aa8d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a7eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a7eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a896`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a896`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a93a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000aa58`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000abc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000abde`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a93a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000aa58`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000abc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000abde`
- `RPCRT4!RpcRaiseException` at `0x18000abb8`
- `RPCRT4!RpcRaiseException` at `0x18000ac20`
- `RPCRT4!RpcRaiseException` at `0x18000abb8`
- `RPCRT4!RpcRaiseException` at `0x18000ac20`

## string_xrefs

- `0x18000ac50`: `BfeSecurityDescriptorDecode`
- `0x18000aafa`: `BfeCallCommitEx`
- `0x18000aad9`: `BfeTxnCommit`
- `0x18000acf1`: `BfeObjectCopyPublicState`

## pseudocode

```c
__int64 __fastcall BfeRpcFilterAdd(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v8; // r12
  __int64 v9; // rbx
  __int64 *Value; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 result; // rax
  _DWORD *v18; // rdi
  int v19; // eax
  int v20; // edi
  int v21; // edx
  unsigned int v22; // esi
  __int64 v23; // r8
  BOOL v24; // edi
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rax
  void *v28; // r8
  __int64 v29; // rcx
  _DWORD *v30; // rsi
  int IsEnabledDeviceUsageInline; // eax
  int v32; // edi
  int v33; // edx
  unsigned int v34; // esi
  __int64 v35; // r8
  BOOL v36; // edi
  _QWORD *v37; // rdi
  __int64 v38; // r8
  RPC_STATUS v39; // ecx
  int TickCount64; // edi
  RPC_STATUS v41; // eax
  __int64 v42; // r8
  _QWORD *v43; // [rsp+30h] [rbp-61h] BYREF
  __int64 v44; // [rsp+38h] [rbp-59h] BYREF
  _OWORD TlsValue[2]; // [rsp+40h] [rbp-51h] BYREF
  _BYTE v46[16]; // [rsp+60h] [rbp-31h] BYREF
  const char *v47; // [rsp+70h] [rbp-21h]
  __int64 v48; // [rsp+78h] [rbp-19h]
  _QWORD **v49; // [rsp+80h] [rbp-11h]
  __int64 v50; // [rsp+88h] [rbp-9h]

  v44 = 0;
  v43 = 0;
  v8 = 0;
  memset(TlsValue, 0, sizeof(TlsValue));
  if ( a1 )
    v44 = a3;
  v9 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( v9 )
    goto LABEL_12;
  Value = (__int64 *)TlsGetValue(gBfeContextComponent);
  if ( !Value || (v12 = *Value) == 0 || !*(_DWORD *)(v12 + 88) )
  {
    v9 = BfeFwpmFilterValidate(a3);
    if ( v9 )
      goto LABEL_60;
  }
  if ( !a1 )
  {
    v26 = gBfeObjMgr;
    if ( !*(_DWORD *)(gBfeObjMgr + 2040) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v11);
    v27 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v26 + 2072))(a3, &v44);
    v9 = v27;
    if ( v27 )
    {
      WfpReportError(v27, "BfeObjectCopyPublicState");
      goto LABEL_60;
    }
  }
  v28 = 0;
  if ( a4 && *(_DWORD *)a4 )
  {
    v9 = BfeRelativeSecurityDescriptorValidate(*(PSECURITY_DESCRIPTOR *)(a4 + 8), *(_DWORD *)a4);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v42, 0, (__int64)"BfeSecurityDescriptorDecode", v9);
      }
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
      {
        LODWORD(v43) = v9;
        v49 = &v43;
        v47 = "BfeSecurityDescriptorDecode";
        v48 = 28;
        v50 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v42,
          3,
          (__int64)v46);
      }
      goto LABEL_60;
    }
    v28 = *(void **)(a4 + 8);
  }
  v9 = BfeObjectAdd(5u, &v44, v28, &v43);
  if ( v9 )
  {
LABEL_60:
    if ( v44 )
      BfeObjectTraceAddFailure(5, v44);
    goto LABEL_12;
  }
  if ( *(_QWORD *)&TlsValue[0] && *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
  {
    v9 = 0;
  }
  else
  {
    v30 = (_DWORD *)*((_QWORD *)&TlsValue[0] + 1);
    v9 = 0;
    BfeTxnLockCancelLockTimeout();
    if ( !dword_1800F5CD0 )
    {
      TickCount64 = GetTickCount64();
      v9 = BfeTxnCoordinatorCommit(0);
      dword_1800F5CF8 = GetTickCount64() - TickCount64;
    }
    IsEnabledDeviceUsageInline = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
    *v30 = 0;
    if ( !IsEnabledDeviceUsageInline )
    {
      v32 = qword_1800F5CF0;
      v34 = GetTickCount64() - v32;
      if ( v34 >= dword_1800F5CE4 )
      {
        if ( (byte_1800F6115 & 2) != 0 )
          McTemplateU0qqqq_EtwEventWriteTransfer(
            dword_1800F5CF8,
            v33,
            dword_1800F5CE8,
            v34,
            dword_1800F5CF8,
            dword_1800F5CE4);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v35, (unsigned int)dword_1800F5CE8, v34, dword_1800F5CF8);
        }
      }
    }
    qword_1800F5CC8 = 0;
    v36 = ReleaseSemaphore(gBfeTxnComponent, 1, 0);
    if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v36 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v29);
    if ( gBfePeriodicRundownEnabled && !dword_1800F5CD0 )
      BfeRundownState(v29);
    if ( v9 )
    {
      WfpReportError(v9, "BfeTxnCommit");
      *((_QWORD *)&TlsValue[0] + 1) = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v38, 0, (__int64)"BfeCallCommitEx", v9);
      }
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
      {
        LODWORD(v43) = v9;
        v49 = &v43;
        v47 = "BfeCallCommitEx";
        v48 = 16;
        v50 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v38,
          3,
          (__int64)v46);
      }
      goto LABEL_60;
    }
    *((_QWORD *)&TlsValue[0] + 1) = 0;
  }
  v37 = v43;
  if ( !v43 || !*v43 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v29);
    if ( !v37 || !*v37 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v13);
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD *))(*v37 + 104LL))(v37 + 18);
LABEL_12:
  if ( *((_QWORD *)&TlsValue[0] + 1) )
  {
    if ( *(_QWORD *)&TlsValue[0] && *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
    {
      v14 = *(_QWORD *)&TlsValue[0] + 32LL;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)&TlsValue[0] + 32LL), 2, 1) == 3 )
        BfeTxnAbort(v14, 1);
    }
    else
    {
      v18 = (_DWORD *)*((_QWORD *)&TlsValue[0] + 1);
      BfeTxnLockCancelLockTimeout();
      if ( !dword_1800F5CD0 )
        BfeTxnCoordinatorRollback();
      v19 = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
      *v18 = 0;
      if ( !v19 )
      {
        v20 = qword_1800F5CF0;
        v22 = GetTickCount64() - v20;
        if ( v22 >= dword_1800F5CE4 )
        {
          if ( (byte_1800F6115 & 2) != 0 )
            McTemplateU0qqqq_EtwEventWriteTransfer(
              dword_1800F5CF8,
              v21,
              dword_1800F5CE8,
              v22,
              dword_1800F5CF8,
              dword_1800F5CE4);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_LLL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              v23,
              (unsigned int)dword_1800F5CE8,
              v22,
              dword_1800F5CF8);
          }
        }
      }
      qword_1800F5CC8 = 0;
      v24 = ReleaseSemaphore(gBfeTxnComponent, 1, 0);
      if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v24 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v25);
    }
  }
  TlsSetValue(gBfeContextComponent, 0);
  v16 = gBfeObjMgr;
  if ( !*(_DWORD *)(gBfeObjMgr + 2040) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v15);
  (*(void (__fastcall **)(__int64 *))(v16 + 2080))(&v44);
  if ( a1 )
  {
    if ( v9 )
    {
      if ( !(unsigned int)BfeRpcIsKernelModeCaller() )
      {
        v39 = (unsigned __int16)v9;
        if ( (v9 & 0x1FFF0000) != 0x70000 )
          v39 = v9;
        RpcRaiseException(v39);
      }
      v41 = WfpErrorToNtStatus(v9);
      RpcRaiseException(v41);
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
0x18000a770  push    rbp
0x18000a772  push    rbx
0x18000a773  push    rsi
0x18000a774  push    rdi
0x18000a775  push    r12
0x18000a777  push    r13
0x18000a779  push    r14
0x18000a77b  push    r15
0x18000a77d  lea     rbp, [rsp-17h]
0x18000a782  sub     rsp, 0A8h
0x18000a789  mov     rax, cs:__security_cookie
0x18000a790  xor     rax, rsp
0x18000a793  mov     [rbp+4Fh+var_50], rax
0x18000a797  mov     r14, [rbp+4Fh+arg_20]
0x18000a79b  xor     r13d, r13d
0x18000a79e  mov     [rbp+4Fh+var_A8], r13
0x18000a7a2  xorps   xmm0, xmm0
0x18000a7a5  mov     [rbp+4Fh+var_B0], r13
0x18000a7a9  mov     rdi, r9
0x18000a7ac  mov     rsi, r8
0x18000a7af  mov     r15, rcx
0x18000a7b2  mov     r12d, r13d
0x18000a7b5  movups  [rbp+4Fh+TlsValue], xmm0
0x18000a7b9  movups  [rbp+4Fh+var_90], xmm0
0x18000a7bd  test    rcx, rcx
0x18000a7c0  jz      short loc_18000A7C6
0x18000a7c2  mov     [rbp+4Fh+var_A8], r8
0x18000a7c6  mov     r9d, 1; int
0x18000a7cc  lea     rax, [rbp+4Fh+TlsValue]
0x18000a7d0  mov     r8d, r9d; int
0x18000a7d3  mov     [rsp+0E0h+lpTlsValue], rax; lpTlsValue
0x18000a7d8  call    BfeCallCreate
0x18000a7dd  mov     rbx, rax
0x18000a7e0  test    rax, rax
0x18000a7e3  jnz     short loc_18000A854
0x18000a7e5  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000a7eb  call    cs:__imp_TlsGetValue
0x18000a7f2  nop     dword ptr [rax+rax+00h]
0x18000a7f7  test    rax, rax
0x18000a7fa  jz      short loc_18000A808
0x18000a7fc  mov     rax, [rax]
0x18000a7ff  test    rax, rax
0x18000a802  jnz     loc_18000A9AD
0x18000a808  mov     rcx, rsi
0x18000a80b  call    BfeFwpmFilterValidate
0x18000a810  mov     rbx, rax
0x18000a813  test    rax, rax
0x18000a816  jnz     loc_18000AB35
0x18000a81c  jmp     loc_18000A9B7
0x18000a821  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a826  test    rdi, rdi
0x18000a829  jz      short loc_18000A830
0x18000a82b  cmp     [rdi], r13
0x18000a82e  jnz     short loc_18000A835
0x18000a830  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a835  mov     rax, [rdi]
0x18000a838  lea     rcx, [rdi+90h]
0x18000a83f  mov     rax, [rax+68h]
0x18000a843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a848  mov     r12, rax
0x18000a84b  test    rbx, rbx
0x18000a84e  jnz     loc_18000AB35
0x18000a854  cmp     qword ptr [rbp+4Fh+TlsValue+8], r13
0x18000a858  jz      short loc_18000A88E
0x18000a85a  mov     rax, qword ptr [rbp+4Fh+TlsValue]
0x18000a85e  test    rax, rax
0x18000a861  jz      loc_18000A911
0x18000a867  cmp     [rax+24h], r13d
0x18000a86b  jz      loc_18000A911
0x18000a871  lea     rcx, [rax+20h]
0x18000a875  mov     r8d, 2
0x18000a87b  mov     eax, 1
0x18000a880  lock cmpxchg [rcx], r8d
0x18000a885  cmp     eax, 3
0x18000a888  jz      loc_18000AD50
0x18000a88e  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000a894  xor     edx, edx; lpTlsValue
0x18000a896  call    cs:__imp_TlsSetValue
0x18000a89d  nop     dword ptr [rax+rax+00h]
0x18000a8a2  mov     rdi, cs:gBfeObjMgr
0x18000a8a9  cmp     [rdi+7F8h], r13d
0x18000a8b0  jnz     short loc_18000A8B7
0x18000a8b2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a8b7  mov     rax, [rdi+820h]
0x18000a8be  lea     rcx, [rbp+4Fh+var_A8]
0x18000a8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8c7  test    r15, r15
0x18000a8ca  jnz     loc_18000A99C
0x18000a8d0  mov     ecx, ebx
0x18000a8d2  movzx   eax, bx
0x18000a8d5  and     ecx, 1FFF0000h
0x18000a8db  cmp     ecx, 70000h
0x18000a8e1  cmovnz  eax, ebx
0x18000a8e4  test    eax, eax
0x18000a8e6  jnz     short loc_18000A8F0
0x18000a8e8  test    r14, r14
0x18000a8eb  jz      short loc_18000A8F0
0x18000a8ed  mov     [r14], r12
0x18000a8f0  mov     rcx, [rbp+4Fh+var_50]
0x18000a8f4  xor     rcx, rsp; StackCookie
0x18000a8f7  call    __security_check_cookie
0x18000a8fc  add     rsp, 0A8h
0x18000a903  pop     r15
0x18000a905  pop     r14
0x18000a907  pop     r13
0x18000a909  pop     r12
0x18000a90b  pop     rdi
0x18000a90c  pop     rsi
0x18000a90d  pop     rbx
0x18000a90e  pop     rbp
0x18000a90f  retn
0x18000a911  mov     rdi, qword ptr [rbp+4Fh+TlsValue+8]
0x18000a915  call    BfeTxnLockCancelLockTimeout
0x18000a91a  cmp     cs:dword_1800F5CD0, r13d
0x18000a921  jnz     short loc_18000A928
0x18000a923  call    BfeTxnCoordinatorRollback
0x18000a928  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000a92d  mov     [rdi], r13d
0x18000a930  test    eax, eax
0x18000a932  jnz     short loc_18000A959
0x18000a934  mov     edi, dword ptr cs:qword_1800F5CF0
0x18000a93a  call    cs:__imp_GetTickCount64
0x18000a941  nop     dword ptr [rax+rax+00h]
0x18000a946  mov     rsi, rax
0x18000a949  mov     eax, cs:dword_1800F5CE4
0x18000a94f  sub     esi, edi
0x18000a951  cmp     esi, eax
0x18000a953  jnb     loc_18000AD5F
0x18000a959  mov     rcx, cs:gBfeTxnComponent; hSemaphore
0x18000a960  xor     r8d, r8d; lpPreviousCount
0x18000a963  mov     edx, 1; lReleaseCount
0x18000a968  mov     cs:qword_1800F5CC8, r13
0x18000a96f  call    cs:__imp_ReleaseSemaphore
0x18000a976  nop     dword ptr [rax+rax+00h]
0x18000a97b  mov     edi, eax
0x18000a97d  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000a982  test    eax, eax
0x18000a984  jz      loc_18000A88E
0x18000a98a  test    edi, edi
0x18000a98c  jnz     loc_18000A88E
0x18000a992  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a997  jmp     loc_18000A88E
0x18000a99c  test    rbx, rbx
0x18000a99f  jnz     loc_18000AB9D
0x18000a9a5  mov     eax, r13d
0x18000a9a8  jmp     loc_18000A8E8
0x18000a9ad  cmp     [rax+58h], r13d
0x18000a9b1  jz      loc_18000A808
0x18000a9b7  test    r15, r15
0x18000a9ba  jnz     short loc_18000A9F0
0x18000a9bc  mov     rbx, cs:gBfeObjMgr
0x18000a9c3  cmp     [rbx+7F8h], r13d
0x18000a9ca  jnz     short loc_18000A9D1
0x18000a9cc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a9d1  mov     rax, [rbx+818h]
0x18000a9d8  lea     rdx, [rbp+4Fh+var_A8]
0x18000a9dc  mov     rcx, rsi
0x18000a9df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e4  mov     rbx, rax
0x18000a9e7  test    rax, rax
0x18000a9ea  jnz     loc_18000ACF1
0x18000a9f0  mov     r8, r13
0x18000a9f3  test    rdi, rdi
0x18000a9f6  jnz     loc_18000ACE2
0x18000a9fc  lea     r9, [rbp+4Fh+var_B0]
0x18000aa00  mov     ecx, 5
0x18000aa05  lea     rdx, [rbp+4Fh+var_A8]
0x18000aa09  call    BfeObjectAdd
0x18000aa0e  mov     rbx, rax
0x18000aa11  test    rax, rax
0x18000aa14  jnz     loc_18000AB35
0x18000aa1a  mov     rax, qword ptr [rbp+4Fh+TlsValue]
0x18000aa1e  test    rax, rax
0x18000aa21  jz      short loc_18000AA2D
0x18000aa23  cmp     [rax+24h], r13d
0x18000aa27  jnz     loc_18000ABF7
0x18000aa2d  mov     rsi, qword ptr [rbp+4Fh+TlsValue+8]
0x18000aa31  mov     rbx, r13
0x18000aa34  call    BfeTxnLockCancelLockTimeout
0x18000aa39  cmp     cs:dword_1800F5CD0, r13d
0x18000aa40  jz      loc_18000ABC5
0x18000aa46  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000aa4b  mov     [rsi], r13d
0x18000aa4e  test    eax, eax
0x18000aa50  jnz     short loc_18000AA77
0x18000aa52  mov     edi, dword ptr cs:qword_1800F5CF0
0x18000aa58  call    cs:__imp_GetTickCount64
0x18000aa5f  nop     dword ptr [rax+rax+00h]
0x18000aa64  mov     rsi, rax
0x18000aa67  mov     eax, cs:dword_1800F5CE4
0x18000aa6d  sub     esi, edi
0x18000aa6f  cmp     esi, eax
0x18000aa71  jnb     loc_18000AD0E
0x18000aa77  mov     rcx, cs:gBfeTxnComponent; hSemaphore
0x18000aa7e  xor     r8d, r8d; lpPreviousCount
0x18000aa81  mov     edx, 1; lReleaseCount
0x18000aa86  mov     cs:qword_1800F5CC8, r13
0x18000aa8d  call    cs:__imp_ReleaseSemaphore
0x18000aa94  nop     dword ptr [rax+rax+00h]
0x18000aa99  mov     edi, eax
0x18000aa9b  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000aaa0  test    eax, eax
0x18000aaa2  jnz     loc_18000AD3E
0x18000aaa8  cmp     cs:gBfePeriodicRundownEnabled, r13d
0x18000aaaf  jnz     loc_18000ABFF
0x18000aab5  test    rbx, rbx
0x18000aab8  jnz     short loc_18000AAD9
0x18000aaba  mov     qword ptr [rbp+4Fh+TlsValue+8], r13
0x18000aabe  mov     rdi, [rbp+4Fh+var_B0]
0x18000aac2  test    rdi, rdi
0x18000aac5  jz      loc_18000A821
0x18000aacb  cmp     [rdi], r13
0x18000aace  jz      loc_18000A821
0x18000aad4  jmp     loc_18000A835
0x18000aad9  lea     rdx, aBfetxncommit; "BfeTxnCommit"
0x18000aae0  mov     rcx, rbx
0x18000aae3  call    WfpReportError
0x18000aae8  mov     qword ptr [rbp+4Fh+TlsValue+8], r13
0x18000aaec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaf3  lea     rax, WPP_GLOBAL_Control
0x18000aafa  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x18000ab01  cmp     rcx, rax
0x18000ab04  jz      short loc_18000AB2C
0x18000ab06  cmp     byte ptr [rcx+19h], 2
0x18000ab0a  jb      short loc_18000AB2C
0x18000ab0c  test    byte ptr [rcx+1Ch], 1
0x18000ab10  jz      short loc_18000AB2C
0x18000ab12  mov     rcx, [rcx+10h]
0x18000ab16  mov     edx, 1Ah
0x18000ab1b  mov     [rsp+0E0h+var_B8], ebx
0x18000ab1f  xor     r9d, r9d
0x18000ab22  mov     [rsp+0E0h+lpTlsValue], rdi
0x18000ab27  call    WPP_SF_Ssd
0x18000ab2c  cmp     cs:gWfpLogUserModeErrors, r13d
0x18000ab33  jnz     short loc_18000AB51
0x18000ab35  mov     rdx, [rbp+4Fh+var_A8]
0x18000ab39  test    rdx, rdx
0x18000ab3c  jz      loc_18000A854
0x18000ab42  mov     ecx, 5
0x18000ab47  call    BfeObjectTraceAddFailure
0x18000ab4c  jmp     loc_18000A854
0x18000ab51  test    cs:byte_1800F6115, 1
0x18000ab58  jz      short loc_18000AB35
0x18000ab5a  lea     rax, [rbp+4Fh+var_B0]
0x18000ab5e  mov     dword ptr [rbp+4Fh+var_B0], ebx
0x18000ab61  mov     [rbp+4Fh+var_60], rax
0x18000ab65  lea     rdx, WFP_USERMODE_ERROR
0x18000ab6c  lea     rax, [rbp+4Fh+var_80]
0x18000ab70  mov     [rbp+4Fh+var_70], rdi
0x18000ab74  mov     r9d, 3
0x18000ab7a  mov     [rsp+0E0h+lpTlsValue], rax
0x18000ab7f  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000ab86  mov     [rbp+4Fh+var_68], 10h
0x18000ab8e  mov     [rbp+4Fh+var_58], 4
0x18000ab96  call    McGenEventWrite_EtwEventWriteTransfer
0x18000ab9b  jmp     short loc_18000AB35
0x18000ab9d  call    BfeRpcIsKernelModeCaller
0x18000aba2  test    eax, eax
0x18000aba4  jnz     short loc_18000AC16
0x18000aba6  mov     eax, ebx
0x18000aba8  movzx   ecx, bx
0x18000abab  and     eax, 1FFF0000h
0x18000abb0  cmp     eax, 70000h
0x18000abb5  cmovnz  ecx, ebx; exception
0x18000abb8  call    cs:__imp_RpcRaiseException
0x18000abbf  nop     dword ptr [rax+rax+00h]
0x18000abc4  int     3; Trap to Debugger
0x18000abc5  call    cs:__imp_GetTickCount64
0x18000abcc  nop     dword ptr [rax+rax+00h]
0x18000abd1  xor     ecx, ecx
0x18000abd3  mov     rdi, rax
0x18000abd6  call    BfeTxnCoordinatorCommit
0x18000abdb  mov     rbx, rax
0x18000abde  call    cs:__imp_GetTickCount64
0x18000abe5  nop     dword ptr [rax+rax+00h]
0x18000abea  sub     eax, edi
0x18000abec  mov     cs:dword_1800F5CF8, eax
0x18000abf2  jmp     loc_18000AA46
0x18000abf7  mov     rbx, r13
0x18000abfa  jmp     loc_18000AABE
0x18000abff  cmp     cs:dword_1800F5CD0, r13d
0x18000ac06  jnz     loc_18000AAB5
0x18000ac0c  call    BfeRundownState
0x18000ac11  jmp     loc_18000AAB5
0x18000ac16  mov     rcx, rbx
0x18000ac19  call    WfpErrorToNtStatus
0x18000ac1e  mov     ecx, eax; exception
0x18000ac20  call    cs:__imp_RpcRaiseException
0x18000ac27  nop     dword ptr [rax+rax+00h]
0x18000ac2c  int     3; Trap to Debugger
0x18000ac2d  mov     rcx, [rdi+8]; SecurityDescriptor
0x18000ac31  call    BfeRelativeSecurityDescriptorValidate
0x18000ac36  mov     rbx, rax
0x18000ac39  test    rax, rax
0x18000ac3c  jz      loc_18000AD05
0x18000ac42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac49  lea     rax, WPP_GLOBAL_Control
0x18000ac50  lea     rdi, aBfesecuritydes_0; "BfeSecurityDescriptorDecode"
0x18000ac57  cmp     rcx, rax
0x18000ac5a  jz      short loc_18000AC82
  ... truncated ...
```
