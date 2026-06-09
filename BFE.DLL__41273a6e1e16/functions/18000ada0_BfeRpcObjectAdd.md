# BfeRpcObjectAdd

- ea: `0x18000ada0`
- end: `0x18000b3cc`
- name: `BfeRpcObjectAdd`
- size: `1580`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180041150`
- `0x180041bd0`
- `0x1800478a0`

## callees

- `0x180006584`
- `0x180008c5c`
- `0x180008ca8`
- `0x180008dd0`
- `0x18000ada0`
- `0x18000b3d4`
- `0x18000b5b4`
- `0x18000fb34`
- `0x180011510`
- `0x1800197d0`
- `0x180024ab0`
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

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000afb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000b160`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000afb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000b160`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ae1f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ae1f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000aed9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000aed9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000af7a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b120`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b235`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b24e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000af7a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b120`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b235`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b24e`
- `RPCRT4!RpcRaiseException` at `0x18000b228`
- `RPCRT4!RpcRaiseException` at `0x18000b296`
- `RPCRT4!RpcRaiseException` at `0x18000b228`
- `RPCRT4!RpcRaiseException` at `0x18000b296`

## string_xrefs

- `0x18000b2c6`: `BfeSecurityDescriptorDecode`
- `0x18000b088`: `BfeCallCommitEx`
- `0x18000b06a`: `BfeTxnCommit`
- `0x18000b32e`: `BfeObjectCopyPublicState`

## pseudocode

```c
__int64 __fastcall BfeRpcObjectAdd(
        __int64 a1,
        int a2,
        int a3,
        __int64 (__fastcall *a4)(__int64),
        __int64 a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v8; // r14
  __int64 v10; // rbx
  __int64 *Value; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 result; // rax
  _DWORD *v19; // rdi
  int v20; // eax
  int v21; // edi
  int v22; // edx
  unsigned int v23; // esi
  __int64 v24; // r8
  BOOL v25; // edi
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rax
  void *v29; // r8
  __int64 v30; // rcx
  __int64 v31; // r8
  const char *v32; // rdi
  _DWORD *v33; // rsi
  int IsEnabledDeviceUsageInline; // eax
  int v35; // edi
  int v36; // edx
  unsigned int v37; // esi
  __int64 v38; // r8
  BOOL v39; // edi
  _QWORD *v40; // rdi
  RPC_STATUS v41; // ecx
  int TickCount64; // edi
  RPC_STATUS v43; // eax
  __int64 v44; // rax
  _QWORD *v45; // [rsp+30h] [rbp-71h] BYREF
  __int64 v46; // [rsp+38h] [rbp-69h] BYREF
  _OWORD TlsValue[2]; // [rsp+40h] [rbp-61h] BYREF
  char v48[16]; // [rsp+60h] [rbp-41h] BYREF
  const char *v49; // [rsp+70h] [rbp-31h]
  __int64 v50; // [rsp+78h] [rbp-29h]
  _QWORD **v51; // [rsp+80h] [rbp-21h]
  __int64 v52; // [rsp+88h] [rbp-19h]

  v8 = a3;
  v46 = 0;
  v45 = 0;
  memset(TlsValue, 0, sizeof(TlsValue));
  if ( a1 )
    v46 = a5;
  v10 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( !v10 )
  {
    Value = (__int64 *)TlsGetValue(gBfeContextComponent);
    if ( !Value || (v13 = *Value) == 0 || !*(_DWORD *)(v13 + 88) )
    {
      v10 = a4(a5);
      if ( v10 )
        goto LABEL_48;
    }
    if ( !a1 )
    {
      v27 = gBfeObjMgr + 408 * v8;
      if ( (unsigned int)v8 >= 7 || !*(_DWORD *)v27 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v12);
      v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v27 + 32))(a5, &v46);
      v10 = v28;
      if ( v28 )
      {
        WfpReportError(v28, "BfeObjectCopyPublicState");
        goto LABEL_48;
      }
    }
    v29 = 0;
    if ( a6 && *(_DWORD *)a6 )
    {
      v44 = BfeRelativeSecurityDescriptorValidate(*(PSECURITY_DESCRIPTOR *)(a6 + 8), *(_DWORD *)a6);
      v10 = v44;
      if ( v44 )
      {
        v32 = "BfeSecurityDescriptorDecode";
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v31, 0, (__int64)"BfeSecurityDescriptorDecode", v44);
        }
        if ( !gWfpLogUserModeErrors || (byte_1800F6115 & 1) == 0 )
          goto LABEL_48;
        v50 = 28;
        goto LABEL_66;
      }
      v29 = *(void **)(a6 + 8);
    }
    v10 = BfeObjectAdd(v8, &v46, v29, &v45);
    if ( v10 )
    {
LABEL_48:
      if ( v46 )
        BfeObjectTraceAddFailure((unsigned int)v8, v46);
      goto LABEL_13;
    }
    if ( *(_QWORD *)&TlsValue[0] && *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
    {
      v10 = 0;
    }
    else
    {
      v33 = (_DWORD *)*((_QWORD *)&TlsValue[0] + 1);
      v10 = 0;
      BfeTxnLockCancelLockTimeout();
      if ( !dword_1800F5CD0 )
      {
        TickCount64 = GetTickCount64();
        v10 = BfeTxnCoordinatorCommit(0);
        dword_1800F5CF8 = GetTickCount64() - TickCount64;
      }
      IsEnabledDeviceUsageInline = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
      *v33 = 0;
      if ( !IsEnabledDeviceUsageInline )
      {
        v35 = qword_1800F5CF0;
        v37 = GetTickCount64() - v35;
        if ( v37 >= dword_1800F5CE4 )
        {
          if ( (byte_1800F6115 & 2) != 0 )
            McTemplateU0qqqq_EtwEventWriteTransfer(
              dword_1800F5CF8,
              v36,
              dword_1800F5CE8,
              v37,
              dword_1800F5CF8,
              dword_1800F5CE4);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_LLL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              v38,
              (unsigned int)dword_1800F5CE8,
              v37,
              dword_1800F5CF8);
          }
        }
      }
      qword_1800F5CC8 = 0;
      v39 = ReleaseSemaphore(gBfeTxnComponent, 1, 0);
      if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v39 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v30);
      if ( gBfePeriodicRundownEnabled && !dword_1800F5CD0 )
        BfeRundownState(v30);
      if ( v10 )
      {
        WfpReportError(v10, "BfeTxnCommit");
        *((_QWORD *)&TlsValue[0] + 1) = 0;
        v32 = "BfeCallCommitEx";
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v31, 0, (__int64)"BfeCallCommitEx", v10);
        }
        if ( !gWfpLogUserModeErrors || (byte_1800F6115 & 1) == 0 )
          goto LABEL_48;
        v50 = 16;
LABEL_66:
        v49 = v32;
        v51 = &v45;
        LODWORD(v45) = v10;
        v52 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v31,
          3,
          (__int64)v48);
        goto LABEL_48;
      }
      *((_QWORD *)&TlsValue[0] + 1) = 0;
    }
    if ( a7 )
    {
      v40 = v45;
      if ( !v45 || !*v45 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v30);
        if ( !v40 || !*v40 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v14);
      }
      *a7 = (*(__int64 (__fastcall **)(_QWORD *))(*v40 + 104LL))(v40 + 18);
    }
  }
LABEL_13:
  if ( *((_QWORD *)&TlsValue[0] + 1) )
  {
    if ( *(_QWORD *)&TlsValue[0] && *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
    {
      v15 = *(_QWORD *)&TlsValue[0] + 32LL;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)&TlsValue[0] + 32LL), 2, 1) == 3 )
        BfeTxnAbort(v15, 1);
    }
    else
    {
      v19 = (_DWORD *)*((_QWORD *)&TlsValue[0] + 1);
      BfeTxnLockCancelLockTimeout();
      if ( !dword_1800F5CD0 )
        BfeTxnCoordinatorRollback();
      v20 = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
      *v19 = 0;
      if ( !v20 )
      {
        v21 = qword_1800F5CF0;
        v23 = GetTickCount64() - v21;
        if ( v23 >= dword_1800F5CE4 )
        {
          if ( (byte_1800F6115 & 2) != 0 )
            McTemplateU0qqqq_EtwEventWriteTransfer(
              dword_1800F5CF8,
              v22,
              dword_1800F5CE8,
              v23,
              dword_1800F5CF8,
              dword_1800F5CE4);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_LLL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              v24,
              (unsigned int)dword_1800F5CE8,
              v23,
              dword_1800F5CF8);
          }
        }
      }
      qword_1800F5CC8 = 0;
      v25 = ReleaseSemaphore(gBfeTxnComponent, 1, 0);
      if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v25 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v26);
    }
  }
  TlsSetValue(gBfeContextComponent, 0);
  v17 = gBfeObjMgr + 408 * v8;
  if ( (unsigned int)v8 >= 7 || !*(_DWORD *)v17 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v16);
  (*(void (__fastcall **)(__int64 *))(v17 + 40))(&v46);
  if ( a1 )
  {
    if ( v10 )
    {
      if ( !(unsigned int)BfeRpcIsKernelModeCaller() )
      {
        v41 = (unsigned __int16)v10;
        if ( (v10 & 0x1FFF0000) != 0x70000 )
          v41 = v10;
        RpcRaiseException(v41);
      }
      v43 = WfpErrorToNtStatus(v10);
      RpcRaiseException(v43);
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
0x18000ada0  push    rbp
0x18000ada2  push    rbx
0x18000ada3  push    rsi
0x18000ada4  push    rdi
0x18000ada5  push    r12
0x18000ada7  push    r13
0x18000ada9  push    r14
0x18000adab  push    r15
0x18000adad  lea     rbp, [rsp-7]
0x18000adb2  sub     rsp, 0A8h
0x18000adb9  mov     rax, cs:__security_cookie
0x18000adc0  xor     rax, rsp
0x18000adc3  mov     [rbp+3Fh+var_50], rax
0x18000adc7  mov     rdi, [rbp+3Fh+arg_28]
0x18000adcb  xor     eax, eax
0x18000adcd  mov     rsi, [rbp+3Fh+arg_20]
0x18000add1  xorps   xmm0, xmm0
0x18000add4  mov     r12, [rbp+3Fh+arg_30]
0x18000add8  mov     r15, r9
0x18000addb  movsxd  r14, r8d
0x18000adde  mov     r13, rcx
0x18000ade1  mov     [rbp+3Fh+var_A8], rax
0x18000ade5  mov     [rbp+3Fh+var_B0], rax
0x18000ade9  movups  [rbp+3Fh+TlsValue], xmm0
0x18000aded  movups  [rbp+3Fh+var_90], xmm0
0x18000adf1  test    rcx, rcx
0x18000adf4  jz      short loc_18000ADFA
0x18000adf6  mov     [rbp+3Fh+var_A8], rsi
0x18000adfa  mov     r9d, 1; int
0x18000ae00  lea     rax, [rbp+3Fh+TlsValue]
0x18000ae04  mov     r8d, r9d; int
0x18000ae07  mov     [rsp+0E0h+lpTlsValue], rax; lpTlsValue
0x18000ae0c  call    BfeCallCreate
0x18000ae11  mov     rbx, rax
0x18000ae14  test    rax, rax
0x18000ae17  jnz     short loc_18000AE58
0x18000ae19  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000ae1f  call    cs:__imp_TlsGetValue
0x18000ae26  nop     dword ptr [rax+rax+00h]
0x18000ae2b  test    rax, rax
0x18000ae2e  jz      short loc_18000AE3C
0x18000ae30  mov     rax, [rax]
0x18000ae33  test    rax, rax
0x18000ae36  jnz     loc_18000AFF0
0x18000ae3c  mov     rcx, rsi
0x18000ae3f  mov     rax, r15
0x18000ae42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae47  mov     rbx, rax
0x18000ae4a  test    rax, rax
0x18000ae4d  jnz     loc_18000B061
0x18000ae53  jmp     loc_18000AFFA
0x18000ae58  lea     r15, WPP_GLOBAL_Control
0x18000ae5f  jmp     short loc_18000AE96
0x18000ae61  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ae66  test    rdi, rdi
0x18000ae69  jz      short loc_18000AE71
0x18000ae6b  cmp     qword ptr [rdi], 0
0x18000ae6f  jnz     short loc_18000AE76
0x18000ae71  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ae76  mov     rax, [rdi]
0x18000ae79  lea     rcx, [rdi+90h]
0x18000ae80  mov     rax, [rax+68h]
0x18000ae84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae89  mov     [r12], rax
0x18000ae8d  test    rbx, rbx
0x18000ae90  jnz     loc_18000B0C7
0x18000ae96  cmp     qword ptr [rbp+3Fh+TlsValue+8], 0
0x18000ae9b  jz      short loc_18000AED1
0x18000ae9d  mov     rax, qword ptr [rbp+3Fh+TlsValue]
0x18000aea1  test    rax, rax
0x18000aea4  jz      loc_18000AF4E
0x18000aeaa  cmp     dword ptr [rax+24h], 0
0x18000aeae  jz      loc_18000AF4E
0x18000aeb4  lea     rcx, [rax+20h]
0x18000aeb8  mov     r8d, 2
0x18000aebe  mov     eax, 1
0x18000aec3  lock cmpxchg [rcx], r8d
0x18000aec8  cmp     eax, 3
0x18000aecb  jz      loc_18000B38D
0x18000aed1  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000aed7  xor     edx, edx; lpTlsValue
0x18000aed9  call    cs:__imp_TlsSetValue
0x18000aee0  nop     dword ptr [rax+rax+00h]
0x18000aee5  imul    rdi, r14, 198h
0x18000aeec  add     rdi, cs:gBfeObjMgr
0x18000aef3  cmp     r14d, 7
0x18000aef7  jnb     short loc_18000AEFE
0x18000aef9  cmp     dword ptr [rdi], 0
0x18000aefc  jnz     short loc_18000AF03
0x18000aefe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000af03  mov     rax, [rdi+28h]
0x18000af07  lea     rcx, [rbp+3Fh+var_A8]
0x18000af0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af10  test    r13, r13
0x18000af13  jnz     loc_18000AFE0
0x18000af19  mov     ecx, ebx
0x18000af1b  movzx   eax, bx
0x18000af1e  and     ecx, 1FFF0000h
0x18000af24  cmp     ecx, 70000h
0x18000af2a  cmovnz  eax, ebx
0x18000af2d  mov     rcx, [rbp+3Fh+var_50]
0x18000af31  xor     rcx, rsp; StackCookie
0x18000af34  call    __security_check_cookie
0x18000af39  add     rsp, 0A8h
0x18000af40  pop     r15
0x18000af42  pop     r14
0x18000af44  pop     r13
0x18000af46  pop     r12
0x18000af48  pop     rdi
0x18000af49  pop     rsi
0x18000af4a  pop     rbx
0x18000af4b  pop     rbp
0x18000af4c  retn
0x18000af4e  mov     rdi, qword ptr [rbp+3Fh+TlsValue+8]
0x18000af52  call    BfeTxnLockCancelLockTimeout
0x18000af57  cmp     cs:dword_1800F5CD0, 0
0x18000af5e  jnz     short loc_18000AF65
0x18000af60  call    BfeTxnCoordinatorRollback
0x18000af65  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000af6a  mov     dword ptr [rdi], 0
0x18000af70  test    eax, eax
0x18000af72  jnz     short loc_18000AF99
0x18000af74  mov     edi, dword ptr cs:qword_1800F5CF0
0x18000af7a  call    cs:__imp_GetTickCount64
0x18000af81  nop     dword ptr [rax+rax+00h]
0x18000af86  mov     rsi, rax
0x18000af89  mov     eax, cs:dword_1800F5CE4
0x18000af8f  sub     esi, edi
0x18000af91  cmp     esi, eax
0x18000af93  jnb     loc_18000B39C
0x18000af99  mov     rcx, cs:gBfeTxnComponent; hSemaphore
0x18000afa0  xor     r8d, r8d; lpPreviousCount
0x18000afa3  mov     edx, 1; lReleaseCount
0x18000afa8  mov     cs:qword_1800F5CC8, 0
0x18000afb3  call    cs:__imp_ReleaseSemaphore
0x18000afba  nop     dword ptr [rax+rax+00h]
0x18000afbf  mov     edi, eax
0x18000afc1  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000afc6  test    eax, eax
0x18000afc8  jz      loc_18000AED1
0x18000afce  test    edi, edi
0x18000afd0  jnz     loc_18000AED1
0x18000afd6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000afdb  jmp     loc_18000AED1
0x18000afe0  test    rbx, rbx
0x18000afe3  jnz     loc_18000B20D
0x18000afe9  xor     eax, eax
0x18000afeb  jmp     loc_18000AF2D
0x18000aff0  cmp     dword ptr [rax+58h], 0
0x18000aff4  jz      loc_18000AE3C
0x18000affa  test    r13, r13
0x18000affd  jnz     short loc_18000B039
0x18000afff  imul    rbx, r14, 198h
0x18000b006  add     rbx, cs:gBfeObjMgr
0x18000b00d  cmp     r14d, 7
0x18000b011  jnb     short loc_18000B018
0x18000b013  cmp     [rbx], r13d
0x18000b016  jnz     short loc_18000B01D
0x18000b018  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b01d  mov     rax, [rbx+20h]
0x18000b021  lea     rdx, [rbp+3Fh+var_A8]
0x18000b025  mov     rcx, rsi
0x18000b028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b02d  mov     rbx, rax
0x18000b030  test    rax, rax
0x18000b033  jnz     loc_18000B32E
0x18000b039  xor     r8d, r8d
0x18000b03c  test    rdi, rdi
0x18000b03f  jnz     loc_18000B31F
0x18000b045  lea     r9, [rbp+3Fh+var_B0]
0x18000b049  mov     ecx, r14d
0x18000b04c  lea     rdx, [rbp+3Fh+var_A8]
0x18000b050  call    BfeObjectAdd
0x18000b055  mov     rbx, rax
0x18000b058  test    rax, rax
0x18000b05b  jz      loc_18000B0E1
0x18000b061  lea     r15, WPP_GLOBAL_Control
0x18000b068  jmp     short loc_18000B0C7
0x18000b06a  lea     rdx, aBfetxncommit; "BfeTxnCommit"
0x18000b071  mov     rcx, rbx
0x18000b074  call    WfpReportError
0x18000b079  mov     qword ptr [rbp+3Fh+TlsValue+8], 0
0x18000b081  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b088  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x18000b08f  cmp     rcx, r15
0x18000b092  jz      short loc_18000B0BA
0x18000b094  cmp     byte ptr [rcx+19h], 2
0x18000b098  jb      short loc_18000B0BA
0x18000b09a  test    byte ptr [rcx+1Ch], 1
0x18000b09e  jz      short loc_18000B0BA
0x18000b0a0  mov     rcx, [rcx+10h]
0x18000b0a4  mov     edx, 1Ah
0x18000b0a9  mov     [rsp+0E0h+var_B8], ebx
0x18000b0ad  xor     r9d, r9d
0x18000b0b0  mov     [rsp+0E0h+lpTlsValue], rdi
0x18000b0b5  call    WPP_SF_Ssd
0x18000b0ba  cmp     cs:gWfpLogUserModeErrors, 0
0x18000b0c1  jnz     loc_18000B1BA
0x18000b0c7  mov     rdx, [rbp+3Fh+var_A8]
0x18000b0cb  test    rdx, rdx
0x18000b0ce  jz      loc_18000AE96
0x18000b0d4  mov     ecx, r14d
0x18000b0d7  call    BfeObjectTraceAddFailure
0x18000b0dc  jmp     loc_18000AE96
0x18000b0e1  mov     rax, qword ptr [rbp+3Fh+TlsValue]
0x18000b0e5  test    rax, rax
0x18000b0e8  jz      short loc_18000B0F4
0x18000b0ea  cmp     dword ptr [rax+24h], 0
0x18000b0ee  jnz     loc_18000B267
0x18000b0f4  mov     rsi, qword ptr [rbp+3Fh+TlsValue+8]
0x18000b0f8  xor     ebx, ebx
0x18000b0fa  call    BfeTxnLockCancelLockTimeout
0x18000b0ff  cmp     cs:dword_1800F5CD0, ebx
0x18000b105  jz      loc_18000B235
0x18000b10b  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000b110  mov     dword ptr [rsi], 0
0x18000b116  test    eax, eax
0x18000b118  jnz     short loc_18000B13F
0x18000b11a  mov     edi, dword ptr cs:qword_1800F5CF0
0x18000b120  call    cs:__imp_GetTickCount64
0x18000b127  nop     dword ptr [rax+rax+00h]
0x18000b12c  mov     rsi, rax
0x18000b12f  mov     eax, cs:dword_1800F5CE4
0x18000b135  sub     esi, edi
0x18000b137  cmp     esi, eax
0x18000b139  jnb     loc_18000B34B
0x18000b13f  lea     r15, WPP_GLOBAL_Control
0x18000b146  mov     rcx, cs:gBfeTxnComponent; hSemaphore
0x18000b14d  xor     r8d, r8d; lpPreviousCount
0x18000b150  mov     edx, 1; lReleaseCount
0x18000b155  mov     cs:qword_1800F5CC8, 0
0x18000b160  call    cs:__imp_ReleaseSemaphore
0x18000b167  nop     dword ptr [rax+rax+00h]
0x18000b16c  mov     edi, eax
0x18000b16e  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000b173  test    eax, eax
0x18000b175  jnz     loc_18000B37B
0x18000b17b  cmp     cs:gBfePeriodicRundownEnabled, 0
0x18000b182  jnz     loc_18000B275
0x18000b188  test    rbx, rbx
0x18000b18b  jnz     loc_18000B06A
0x18000b191  mov     qword ptr [rbp+3Fh+TlsValue+8], rbx
0x18000b195  test    r12, r12
0x18000b198  jz      loc_18000AE96
0x18000b19e  mov     rdi, [rbp+3Fh+var_B0]
0x18000b1a2  test    rdi, rdi
0x18000b1a5  jz      loc_18000AE61
0x18000b1ab  cmp     qword ptr [rdi], 0
0x18000b1af  jz      loc_18000AE61
0x18000b1b5  jmp     loc_18000AE76
0x18000b1ba  test    cs:byte_1800F6115, 1
0x18000b1c1  jz      loc_18000B0C7
0x18000b1c7  mov     [rbp+3Fh+var_68], 10h
0x18000b1cf  lea     rax, [rbp+3Fh+var_B0]
0x18000b1d3  mov     [rbp+3Fh+var_70], rdi
0x18000b1d7  mov     [rbp+3Fh+var_60], rax
0x18000b1db  lea     rdx, WFP_USERMODE_ERROR
0x18000b1e2  lea     rax, [rbp+3Fh+var_80]
0x18000b1e6  mov     dword ptr [rbp+3Fh+var_B0], ebx
0x18000b1e9  mov     r9d, 3
0x18000b1ef  mov     [rsp+0E0h+lpTlsValue], rax
0x18000b1f4  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000b1fb  mov     [rbp+3Fh+var_58], 4
0x18000b203  call    McGenEventWrite_EtwEventWriteTransfer
0x18000b208  jmp     loc_18000B0C7
0x18000b20d  call    BfeRpcIsKernelModeCaller
0x18000b212  test    eax, eax
0x18000b214  jnz     short loc_18000B28C
0x18000b216  mov     eax, ebx
0x18000b218  movzx   ecx, bx
0x18000b21b  and     eax, 1FFF0000h
0x18000b220  cmp     eax, 70000h
0x18000b225  cmovnz  ecx, ebx; exception
0x18000b228  call    cs:__imp_RpcRaiseException
0x18000b22f  nop     dword ptr [rax+rax+00h]
0x18000b234  int     3; Trap to Debugger
0x18000b235  call    cs:__imp_GetTickCount64
0x18000b23c  nop     dword ptr [rax+rax+00h]
0x18000b241  xor     ecx, ecx
0x18000b243  mov     rdi, rax
0x18000b246  call    BfeTxnCoordinatorCommit
0x18000b24b  mov     rbx, rax
0x18000b24e  call    cs:__imp_GetTickCount64
0x18000b255  nop     dword ptr [rax+rax+00h]
0x18000b25a  sub     eax, edi
0x18000b25c  mov     cs:dword_1800F5CF8, eax
0x18000b262  jmp     loc_18000B10B
0x18000b267  xor     ebx, ebx
0x18000b269  lea     r15, WPP_GLOBAL_Control
0x18000b270  jmp     loc_18000B195
0x18000b275  cmp     cs:dword_1800F5CD0, 0
0x18000b27c  jnz     loc_18000B188
0x18000b282  call    BfeRundownState
0x18000b287  jmp     loc_18000B188
0x18000b28c  mov     rcx, rbx
0x18000b28f  call    WfpErrorToNtStatus
0x18000b294  mov     ecx, eax; exception
0x18000b296  call    cs:__imp_RpcRaiseException
0x18000b29d  nop     dword ptr [rax+rax+00h]
0x18000b2a2  int     3; Trap to Debugger
  ... truncated ...
```
