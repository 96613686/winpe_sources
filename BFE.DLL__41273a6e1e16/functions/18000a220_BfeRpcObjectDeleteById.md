# BfeRpcObjectDeleteById

- ea: `0x18000a220`
- end: `0x18000a762`
- name: `BfeRpcObjectDeleteById`
- size: `1346`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048310`
- `0x180049830`

## callees

- `0x1800051f4`
- `0x180008c5c`
- `0x180008ca8`
- `0x180008f60`
- `0x18000a220`
- `0x18000b3d4`
- `0x18000c188`
- `0x18000fb34`
- `0x180011510`
- `0x180012d8c`
- `0x180024ab0`
- `0x18002681c`
- `0x18003576c`
- `0x1800408e4`
- `0x180044954`
- `0x18004b62c`
- `0x1800572ec`
- `0x1800592f4`
- `0x18005aa60`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x18000a471`
- `ntdll!RtlLookupEntryHashTable` at `0x18000a471`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000a5a5`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000a5a5`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000a449`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000a449`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000a4d6`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000a5e5`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000a4d6`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000a5e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a3c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a3c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a2f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a2f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a38c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a38c`
- `RPCRT4!RpcRaiseException` at `0x18000a5d5`
- `RPCRT4!RpcRaiseException` at `0x18000a6eb`
- `RPCRT4!RpcRaiseException` at `0x18000a5d5`
- `RPCRT4!RpcRaiseException` at `0x18000a6eb`

## string_xrefs

- `0x18000a428`: `BfeObjectDeleteById`
- `0x18000a4ea`: `BfeObjectDeleteById`
- `0x18000a5f1`: `BfeObjectDeleteById`
- `0x18000a64a`: `BfeCallCommitEx`

## pseudocode

```c
__int64 __fastcall BfeRpcObjectDeleteById(__int64 a1, int a2, unsigned int a3, __int64 a4)
{
  __int64 v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 result; // rax
  _DWORD *v12; // rdi
  int IsEnabledDeviceUsageInline; // eax
  int v14; // edi
  int v15; // edx
  __int64 v16; // r8
  unsigned int v17; // r14d
  BOOL v18; // edi
  __int64 v19; // rcx
  __int64 v20; // r12
  _DWORD *v21; // rbx
  _DWORD *v22; // r14
  _DWORD *v23; // r13
  __int64 v24; // rdx
  __int64 i; // rax
  __int64 v26; // rcx
  _BYTE *v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r8
  RPC_STATUS v31; // ecx
  __int64 v32; // r8
  RPC_STATUS v33; // eax
  __int64 v34; // rbx
  int v35; // eax
  int v36; // edx
  int v37; // r8d
  int v38; // [rsp+38h] [rbp-49h] BYREF
  _OWORD TlsValue[2]; // [rsp+40h] [rbp-41h] BYREF
  __int128 v40; // [rsp+60h] [rbp-21h] BYREF
  const char *v41; // [rsp+70h] [rbp-11h]
  __int64 v42; // [rsp+78h] [rbp-9h]
  int *v43; // [rsp+80h] [rbp-1h]
  __int64 v44; // [rsp+88h] [rbp+7h]

  v7 = (int)a3;
  memset(TlsValue, 0, sizeof(TlsValue));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v34 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v35 = BfeObjectTypeIdToString(a3);
    WPP_SF_SI(v34, v36, v37, v35, a4);
  }
  v9 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( v9 )
    goto LABEL_4;
  v20 = 408 * v7;
  v40 = 0;
  v41 = 0;
  v21 = (_DWORD *)(408 * v7 + gBfeObjMgr);
  if ( (unsigned int)v7 >= 7 || !*v21 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
  if ( v21[84] )
  {
    v22 = v21 + 82;
    RtlAcquireSRWLockShared(v21 + 82);
    v23 = v21 + 72;
    v24 = -1;
    if ( a4 )
      v24 = a4;
    for ( i = RtlLookupEntryHashTable(v21 + 72, v24, &v40); i; i = RtlGetNextEntryHashTable(v23, &v40) )
    {
      v27 = (_BYTE *)(i - 40);
      if ( i == 40 || !*(_QWORD *)v27 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v26);
      if ( (v27[8] & 8) == 0 )
      {
        if ( !*(_QWORD *)v27 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v26);
          if ( !*(_QWORD *)v27 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v28);
        }
        if ( (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v27 + 104LL))(v27 + 144) == a4 )
        {
          RtlReleaseSRWLockShared(v22);
          v29 = BfeObjectDelete(v27);
          goto LABEL_40;
        }
      }
    }
    RtlReleaseSRWLockShared(v22);
  }
  v29 = WfpReportSysErrorAsWinError(v8, "BfeObjectDeleteById", *(unsigned int *)(v20 + gBfeObjMgr + 72));
LABEL_40:
  v9 = v29;
  if ( v29 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v30, 0, (__int64)"BfeObjectDeleteById", v29);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v38 = v9;
      v43 = &v38;
      v41 = "BfeObjectDeleteById";
      v42 = 20;
      v44 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        &MICROSOFT_WFP_PROVIDER_Context,
        (__int64)WFP_USERMODE_ERROR,
        v30,
        3,
        (__int64)&v40);
    }
LABEL_4:
    v10 = *(_QWORD *)&TlsValue[0];
    goto LABEL_5;
  }
  v10 = *(_QWORD *)&TlsValue[0];
  if ( !*(_QWORD *)&TlsValue[0] || (v9 = 0, !*(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL)) )
  {
    v9 = BfeTxnCommit(*((_QWORD *)&TlsValue[0] + 1), 0, v30);
    *((_QWORD *)&TlsValue[0] + 1) = 0;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v32, 0, (__int64)"BfeCallCommitEx", v9);
      }
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
      {
        v38 = v9;
        v43 = &v38;
        v41 = "BfeCallCommitEx";
        v42 = 16;
        v44 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v32,
          3,
          (__int64)&v40);
      }
    }
    v10 = *(_QWORD *)&TlsValue[0];
  }
LABEL_5:
  if ( *((_QWORD *)&TlsValue[0] + 1) )
  {
    if ( v10 && *(_DWORD *)(v10 + 36) )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 32), 2, 1) == 3 )
        BfeTxnAbort(v10 + 32, 1);
    }
    else
    {
      v12 = (_DWORD *)*((_QWORD *)&TlsValue[0] + 1);
      BfeTxnLockCancelLockTimeout();
      if ( !dword_1800F5CD0 )
        BfeTxnCoordinatorRollback();
      IsEnabledDeviceUsageInline = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
      *v12 = 0;
      if ( !IsEnabledDeviceUsageInline )
      {
        v14 = qword_1800F5CF0;
        v17 = GetTickCount64() - v14;
        if ( v17 >= dword_1800F5CE4 )
        {
          if ( (byte_1800F6115 & 2) != 0 )
            McTemplateU0qqqq_EtwEventWriteTransfer(
              dword_1800F5CF8,
              v15,
              dword_1800F5CE8,
              v17,
              dword_1800F5CF8,
              dword_1800F5CE4);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_LLL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              v16,
              (unsigned int)dword_1800F5CE8,
              v17,
              dword_1800F5CF8);
          }
        }
      }
      qword_1800F5CC8 = 0;
      v18 = ReleaseSemaphore(gBfeTxnComponent, 1, 0);
      if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v18 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v19);
    }
  }
  TlsSetValue(gBfeContextComponent, 0);
  if ( a1 )
  {
    if ( v9 )
    {
      if ( !(unsigned int)BfeRpcIsKernelModeCaller() )
      {
        v31 = (unsigned __int16)v9;
        if ( (v9 & 0x1FFF0000) != 0x70000 )
          v31 = v9;
        RpcRaiseException(v31);
      }
      v33 = WfpErrorToNtStatus(v9);
      RpcRaiseException(v33);
    }
    return 0;
  }
  else
  {
    result = (unsigned __int16)v9;
    if ( (v9 & 0x1FFF0000) != 0x70000 )
      return (unsigned int)v9;
  }
  return result;
}

```

## disassembly

```asm
0x18000a220  mov     r11, rsp
0x18000a223  push    rbp
0x18000a224  push    rbx
0x18000a225  lea     rbp, [r11-5Fh]
0x18000a229  sub     rsp, 0C8h
0x18000a230  mov     rax, cs:__security_cookie
0x18000a237  xor     rax, rsp
0x18000a23a  mov     [rbp+57h+var_48], rax
0x18000a23e  mov     [r11-18h], rsi
0x18000a242  xorps   xmm0, xmm0
0x18000a245  mov     [r11-20h], rdi
0x18000a249  mov     rsi, rcx
0x18000a24c  mov     [r11-28h], r12
0x18000a250  mov     rdi, rdx
0x18000a253  mov     [r11-38h], r14
0x18000a257  mov     [r11-40h], r15
0x18000a25b  mov     r15, r9
0x18000a25e  movsxd  r14, r8d
0x18000a261  movups  [rbp+57h+TlsValue], xmm0
0x18000a265  movups  [rbp+57h+var_88], xmm0
0x18000a269  mov     rbx, cs:WPP_GLOBAL_Control
0x18000a270  lea     r12, WPP_GLOBAL_Control
0x18000a277  cmp     rbx, r12
0x18000a27a  jz      short loc_18000A286
0x18000a27c  cmp     byte ptr [rbx+19h], 4
0x18000a280  jnb     loc_18000A6F8
0x18000a286  mov     r9d, 1; int
0x18000a28c  lea     rax, [rbp+57h+TlsValue]
0x18000a290  mov     r8d, r9d; int
0x18000a293  mov     [rsp+0D0h+lpTlsValue], rax; lpTlsValue
0x18000a298  mov     rdx, rdi; int
0x18000a29b  call    BfeCallCreate
0x18000a2a0  mov     rbx, rax
0x18000a2a3  test    rax, rax
0x18000a2a6  jz      loc_18000A3F4
0x18000a2ac  mov     rax, qword ptr [rbp+57h+TlsValue]
0x18000a2b0  cmp     qword ptr [rbp+57h+TlsValue+8], 0
0x18000a2b5  mov     r15, [rsp+0D0h+var_38]
0x18000a2bd  jz      short loc_18000A2EF
0x18000a2bf  test    rax, rax
0x18000a2c2  jz      loc_18000A360
0x18000a2c8  cmp     dword ptr [rax+24h], 0
0x18000a2cc  jz      loc_18000A360
0x18000a2d2  lea     rcx, [rax+20h]
0x18000a2d6  mov     r8d, 2
0x18000a2dc  mov     eax, 1
0x18000a2e1  lock cmpxchg [rcx], r8d
0x18000a2e6  cmp     eax, 3
0x18000a2e9  jz      loc_18000A723
0x18000a2ef  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000a2f5  xor     edx, edx; lpTlsValue
0x18000a2f7  call    cs:__imp_TlsSetValue
0x18000a2fe  nop     dword ptr [rax+rax+00h]
0x18000a303  mov     r14, [rsp+0D0h+var_30]
0x18000a30b  test    rsi, rsi
0x18000a30e  mov     rsi, [rsp+0C0h]
0x18000a316  mov     r12, [rsp+0D0h+var_20]
0x18000a31e  mov     rdi, [rsp+0D0h+var_18]
0x18000a326  jz      short loc_18000A335
0x18000a328  test    rbx, rbx
0x18000a32b  jnz     loc_18000A5B6
0x18000a331  xor     eax, eax
0x18000a333  jmp     short loc_18000A349
0x18000a335  mov     ecx, ebx
0x18000a337  movzx   eax, bx
0x18000a33a  and     ecx, 1FFF0000h
0x18000a340  cmp     ecx, 70000h
0x18000a346  cmovnz  eax, ebx
0x18000a349  mov     rcx, [rbp+57h+var_48]
0x18000a34d  xor     rcx, rsp; StackCookie
0x18000a350  call    __security_check_cookie
0x18000a355  add     rsp, 0C8h
0x18000a35c  pop     rbx
0x18000a35d  pop     rbp
0x18000a35e  retn
0x18000a360  mov     rdi, qword ptr [rbp+57h+TlsValue+8]
0x18000a364  call    BfeTxnLockCancelLockTimeout
0x18000a369  cmp     cs:dword_1800F5CD0, 0
0x18000a370  jnz     short loc_18000A377
0x18000a372  call    BfeTxnCoordinatorRollback
0x18000a377  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000a37c  mov     dword ptr [rdi], 0
0x18000a382  test    eax, eax
0x18000a384  jnz     short loc_18000A3AD
0x18000a386  mov     edi, dword ptr cs:qword_1800F5CF0
0x18000a38c  call    cs:__imp_GetTickCount64
0x18000a393  nop     dword ptr [rax+rax+00h]
0x18000a398  mov     r14, rax
0x18000a39b  mov     eax, cs:dword_1800F5CE4
0x18000a3a1  sub     r14d, edi
0x18000a3a4  cmp     r14d, eax
0x18000a3a7  jnb     loc_18000A732
0x18000a3ad  mov     rcx, cs:gBfeTxnComponent; hSemaphore
0x18000a3b4  xor     r8d, r8d; lpPreviousCount
0x18000a3b7  mov     edx, 1; lReleaseCount
0x18000a3bc  mov     cs:qword_1800F5CC8, 0
0x18000a3c7  call    cs:__imp_ReleaseSemaphore
0x18000a3ce  nop     dword ptr [rax+rax+00h]
0x18000a3d3  mov     edi, eax
0x18000a3d5  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18000a3da  test    eax, eax
0x18000a3dc  jz      loc_18000A2EF
0x18000a3e2  test    edi, edi
0x18000a3e4  jnz     loc_18000A2EF
0x18000a3ea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a3ef  jmp     loc_18000A2EF
0x18000a3f4  mov     rbx, cs:gBfeObjMgr
0x18000a3fb  xor     eax, eax
0x18000a3fd  imul    r12, r14, 198h
0x18000a404  xorps   xmm0, xmm0
0x18000a407  movups  [rbp+57h+var_78], xmm0
0x18000a40b  mov     [rbp+57h+var_68], rax
0x18000a40f  add     rbx, r12
0x18000a412  cmp     r14d, 7
0x18000a416  jnb     short loc_18000A41C
0x18000a418  cmp     [rbx], eax
0x18000a41a  jnz     short loc_18000A421
0x18000a41c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a421  cmp     dword ptr [rbx+150h], 0
0x18000a428  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x18000a42f  mov     [rsp+0D0h+var_28], r13
0x18000a437  jz      loc_18000A5F8
0x18000a43d  lea     r14, [rbx+148h]
0x18000a444  xor     edi, edi
0x18000a446  mov     rcx, r14
0x18000a449  call    cs:__imp_RtlAcquireSRWLockShared
0x18000a450  nop     dword ptr [rax+rax+00h]
0x18000a455  test    r15, r15
0x18000a458  lea     r13, [rbx+120h]
0x18000a45f  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000a466  lea     r8, [rbp+57h+var_78]
0x18000a46a  cmovnz  rdx, r15
0x18000a46e  mov     rcx, r13
0x18000a471  call    cs:__imp_RtlLookupEntryHashTable
0x18000a478  nop     dword ptr [rax+rax+00h]
0x18000a47d  test    rax, rax
0x18000a480  jz      loc_18000A5E2
0x18000a486  lea     rbx, [rax-28h]
0x18000a48a  test    rbx, rbx
0x18000a48d  jz      short loc_18000A494
0x18000a48f  cmp     [rbx], rdi
0x18000a492  jnz     short loc_18000A499
0x18000a494  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a499  test    byte ptr [rbx+8], 8
0x18000a49d  jnz     loc_18000A59E
0x18000a4a3  cmp     [rbx], rdi
0x18000a4a6  jnz     short loc_18000A4B7
0x18000a4a8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a4ad  cmp     [rbx], rdi
0x18000a4b0  jnz     short loc_18000A4B7
0x18000a4b2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a4b7  mov     rax, [rbx]
0x18000a4ba  lea     rcx, [rbx+90h]
0x18000a4c1  mov     rax, [rax+68h]
0x18000a4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ca  cmp     rax, r15
0x18000a4cd  jnz     loc_18000A59E
0x18000a4d3  mov     rcx, r14
0x18000a4d6  call    cs:__imp_RtlReleaseSRWLockShared
0x18000a4dd  nop     dword ptr [rax+rax+00h]
0x18000a4e2  mov     rcx, rbx
0x18000a4e5  call    BfeObjectDelete
0x18000a4ea  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x18000a4f1  mov     rbx, rax
0x18000a4f4  mov     r13, [rsp+0D0h+var_28]
0x18000a4fc  test    rax, rax
0x18000a4ff  jz      loc_18000A611
0x18000a505  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a50c  lea     r12, WPP_GLOBAL_Control
0x18000a513  cmp     rcx, r12
0x18000a516  jz      short loc_18000A53E
0x18000a518  cmp     byte ptr [rcx+19h], 2
0x18000a51c  jb      short loc_18000A53E
0x18000a51e  test    byte ptr [rcx+1Ch], 1
0x18000a522  jz      short loc_18000A53E
0x18000a524  mov     rcx, [rcx+10h]
0x18000a528  mov     edx, 1Ah
0x18000a52d  mov     [rsp+28h], ebx
0x18000a531  xor     r9d, r9d
0x18000a534  mov     [rsp+0D0h+lpTlsValue], rdi
0x18000a539  call    WPP_SF_Ssd
0x18000a53e  cmp     cs:gWfpLogUserModeErrors, 0
0x18000a545  jz      loc_18000A2AC
0x18000a54b  test    cs:byte_1800F6115, 1
0x18000a552  jz      loc_18000A2AC
0x18000a558  lea     rax, [rbp+57h+var_A0]
0x18000a55c  mov     [rbp+57h+var_A0], ebx
0x18000a55f  mov     [rbp+57h+var_58], rax
0x18000a563  lea     rdx, WFP_USERMODE_ERROR
0x18000a56a  lea     rax, [rbp+57h+var_78]
0x18000a56e  mov     [rbp+57h+var_68], rdi
0x18000a572  mov     r9d, 3
0x18000a578  mov     [rsp+0D0h+lpTlsValue], rax
0x18000a57d  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000a584  mov     [rbp+57h+var_60], 14h
0x18000a58c  mov     [rbp+57h+var_50], 4
0x18000a594  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a599  jmp     loc_18000A2AC
0x18000a59e  lea     rdx, [rbp+57h+var_78]
0x18000a5a2  mov     rcx, r13
0x18000a5a5  call    cs:__imp_RtlGetNextEntryHashTable
0x18000a5ac  nop     dword ptr [rax+rax+00h]
0x18000a5b1  jmp     loc_18000A47D
0x18000a5b6  call    BfeRpcIsKernelModeCaller
0x18000a5bb  test    eax, eax
0x18000a5bd  jnz     loc_18000A6E1
0x18000a5c3  mov     eax, ebx
0x18000a5c5  movzx   ecx, bx
0x18000a5c8  and     eax, 1FFF0000h
0x18000a5cd  cmp     eax, 70000h
0x18000a5d2  cmovnz  ecx, ebx; exception
0x18000a5d5  call    cs:__imp_RpcRaiseException
0x18000a5dc  nop     dword ptr [rax+rax+00h]
0x18000a5e1  int     3; Trap to Debugger
0x18000a5e2  mov     rcx, r14
0x18000a5e5  call    cs:__imp_RtlReleaseSRWLockShared
0x18000a5ec  nop     dword ptr [rax+rax+00h]
0x18000a5f1  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x18000a5f8  mov     r8, cs:gBfeObjMgr
0x18000a5ff  mov     rdx, rdi
0x18000a602  mov     r8d, [r12+r8+48h]
0x18000a607  call    WfpReportSysErrorAsWinError
0x18000a60c  jmp     loc_18000A4F1
0x18000a611  mov     rax, qword ptr [rbp+57h+TlsValue]
0x18000a615  test    rax, rax
0x18000a618  jz      short loc_18000A621
0x18000a61a  xor     ebx, ebx
0x18000a61c  cmp     [rax+24h], ebx
0x18000a61f  jnz     short loc_18000A689
0x18000a621  mov     rcx, qword ptr [rbp+57h+TlsValue+8]
0x18000a625  xor     edx, edx
0x18000a627  call    BfeTxnCommit
0x18000a62c  mov     rbx, rax
0x18000a62f  mov     qword ptr [rbp+57h+TlsValue+8], 0
0x18000a637  test    rax, rax
0x18000a63a  jz      short loc_18000A685
0x18000a63c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a643  lea     rax, WPP_GLOBAL_Control
0x18000a64a  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x18000a651  cmp     rcx, rax
0x18000a654  jz      short loc_18000A67C
0x18000a656  cmp     byte ptr [rcx+19h], 2
0x18000a65a  jb      short loc_18000A67C
0x18000a65c  test    byte ptr [rcx+1Ch], 1
0x18000a660  jz      short loc_18000A67C
0x18000a662  mov     rcx, [rcx+10h]
0x18000a666  mov     edx, 1Ah
0x18000a66b  mov     [rsp+28h], ebx
0x18000a66f  xor     r9d, r9d
0x18000a672  mov     [rsp+0D0h+lpTlsValue], rdi
0x18000a677  call    WPP_SF_Ssd
0x18000a67c  cmp     cs:gWfpLogUserModeErrors, 0
0x18000a683  jnz     short loc_18000A695
0x18000a685  mov     rax, qword ptr [rbp+57h+TlsValue]
0x18000a689  lea     r12, WPP_GLOBAL_Control
0x18000a690  jmp     loc_18000A2B0
0x18000a695  test    cs:byte_1800F6115, 1
0x18000a69c  jz      short loc_18000A685
0x18000a69e  lea     rax, [rbp+57h+var_A0]
0x18000a6a2  mov     [rbp+57h+var_A0], ebx
0x18000a6a5  mov     [rbp+57h+var_58], rax
0x18000a6a9  lea     rdx, WFP_USERMODE_ERROR
0x18000a6b0  lea     rax, [rbp+57h+var_78]
0x18000a6b4  mov     [rbp+57h+var_68], rdi
0x18000a6b8  mov     r9d, 3
0x18000a6be  mov     [rsp+0D0h+lpTlsValue], rax
0x18000a6c3  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000a6ca  mov     [rbp+57h+var_60], 10h
0x18000a6d2  mov     [rbp+57h+var_50], 4
0x18000a6da  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a6df  jmp     short loc_18000A685
0x18000a6e1  mov     rcx, rbx
0x18000a6e4  call    WfpErrorToNtStatus
0x18000a6e9  mov     ecx, eax; exception
0x18000a6eb  call    cs:__imp_RpcRaiseException
0x18000a6f2  nop     dword ptr [rax+rax+00h]
0x18000a6f7  int     3; Trap to Debugger
0x18000a6f8  test    byte ptr [rbx+1Ch], 2
0x18000a6fc  jz      loc_18000A286
0x18000a702  mov     rbx, [rbx+10h]
0x18000a706  mov     ecx, r14d
0x18000a709  call    BfeObjectTypeIdToString
0x18000a70e  mov     r9, rax
0x18000a711  mov     [rsp+0D0h+lpTlsValue], r15
0x18000a716  mov     rcx, rbx
0x18000a719  call    WPP_SF_SI
0x18000a71e  jmp     loc_18000A286
0x18000a723  mov     edx, 1
0x18000a728  call    BfeTxnAbort
0x18000a72d  jmp     loc_18000A2EF
0x18000a732  test    cs:byte_1800F6115, 2
0x18000a739  jz      loc_18008B714
0x18000a73f  mov     ecx, cs:dword_1800F5CF8
0x18000a745  mov     r9d, r14d
0x18000a748  mov     r8d, cs:dword_1800F5CE8
0x18000a74f  mov     [rsp+28h], eax
0x18000a753  mov     dword ptr [rsp+0D0h+lpTlsValue], ecx
0x18000a757  call    McTemplateU0qqqq_EtwEventWriteTransfer
0x18000a75c  nop
0x18000a75d  jmp     loc_18008B714
  ... truncated ...
```
