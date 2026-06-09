# BfeRpcObjectDeleteById

- ea: `0x180009c30`
- end: `0x18000a135`
- name: `BfeRpcObjectDeleteById`
- size: `1285`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800463c0`
- `0x180047760`

## callees

- `0x1800052ac`
- `0x18000864c`
- `0x180008694`
- `0x180008930`
- `0x180009c30`
- `0x18000ad28`
- `0x18000ba68`
- `0x18000f1a8`
- `0x180010ad0`
- `0x18001236c`
- `0x1800223a8`
- `0x180023e78`
- `0x180036a70`
- `0x18003f5dc`
- `0x180042f04`
- `0x180049750`
- `0x180055424`
- `0x1800575c4`
- `0x180058b30`
- `0x18008b010`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x180009e68`
- `ntdll!RtlLookupEntryHashTable` at `0x180009e68`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009f90`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009f90`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009e46`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009e46`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009ec7`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009fc4`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009ec7`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009fc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180009dca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180009dca`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009d07`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009d07`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009d95`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009d95`
- `RPCRT4!RpcRaiseException` at `0x180009fba`
- `RPCRT4!RpcRaiseException` at `0x18000a0c4`
- `RPCRT4!RpcRaiseException` at `0x180009fba`
- `RPCRT4!RpcRaiseException` at `0x18000a0c4`

## string_xrefs

- `0x180009e25`: `BfeObjectDeleteById`
- `0x180009ed5`: `BfeObjectDeleteById`
- `0x180009fca`: `BfeObjectDeleteById`
- `0x18000a023`: `BfeCallCommitEx`

## pseudocode

```c
__int64 __fastcall BfeRpcObjectDeleteById(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
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
  __int64 v19; // r12
  _DWORD *v20; // rbx
  _DWORD *v21; // r14
  _DWORD *v22; // r13
  __int64 v23; // rdx
  __int64 i; // rax
  _BYTE *v25; // rbx
  __int64 v26; // rax
  __int64 v27; // r8
  RPC_STATUS v28; // ecx
  __int64 v29; // r8
  RPC_STATUS v30; // eax
  __int64 v31; // rbx
  int v32; // eax
  int v33; // edx
  int v34; // r8d
  int v35; // [rsp+38h] [rbp-49h] BYREF
  _OWORD TlsValue[2]; // [rsp+40h] [rbp-41h] BYREF
  __int128 v37; // [rsp+60h] [rbp-21h] BYREF
  const char *v38; // [rsp+70h] [rbp-11h]
  __int64 v39; // [rsp+78h] [rbp-9h]
  int *v40; // [rsp+80h] [rbp-1h]
  __int64 v41; // [rsp+88h] [rbp+7h]

  v7 = (int)a3;
  memset(TlsValue, 0, sizeof(TlsValue));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v31 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v32 = BfeObjectTypeIdToString(a3);
    WPP_SF_SI(v31, v33, v34, v32, a4);
  }
  v9 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( v9 )
    goto LABEL_4;
  v19 = 408 * v7;
  v37 = 0;
  v38 = 0;
  v20 = (_DWORD *)(408 * v7 + *(_QWORD *)&MEMORY[0x1800EF094][7]);
  if ( (unsigned int)v7 >= 7 || !*v20 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( v20[84] )
  {
    v21 = v20 + 82;
    RtlAcquireSRWLockShared(v20 + 82);
    v22 = v20 + 72;
    v23 = -1;
    if ( a4 )
      v23 = a4;
    for ( i = RtlLookupEntryHashTable(v20 + 72, v23, &v37); i; i = RtlGetNextEntryHashTable(v22, &v37) )
    {
      v25 = (_BYTE *)(i - 40);
      if ( i == 40 || !*(_QWORD *)v25 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( (v25[8] & 8) == 0 )
      {
        if ( !*(_QWORD *)v25 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( !*(_QWORD *)v25 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        if ( (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v25 + 104LL))(v25 + 144) == a4 )
        {
          RtlReleaseSRWLockShared(v21);
          v26 = BfeObjectDelete(v25);
          goto LABEL_40;
        }
      }
    }
    RtlReleaseSRWLockShared(v21);
  }
  v26 = WfpReportSysErrorAsWinError(
          v8,
          "BfeObjectDeleteById",
          *(unsigned int *)(v19 + *(_QWORD *)&MEMORY[0x1800EF094][7] + 72));
LABEL_40:
  v9 = v26;
  if ( v26 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v27, 0, (__int64)"BfeObjectDeleteById", v26);
    }
    if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
    {
      v35 = v9;
      v40 = &v35;
      v38 = "BfeObjectDeleteById";
      v39 = 20;
      v41 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        &MICROSOFT_WFP_PROVIDER_Context,
        (__int64)WFP_USERMODE_ERROR,
        v27,
        3,
        (__int64)&v37);
    }
LABEL_4:
    v10 = *(_QWORD *)&TlsValue[0];
    goto LABEL_5;
  }
  v10 = *(_QWORD *)&TlsValue[0];
  if ( !*(_QWORD *)&TlsValue[0] || (v9 = 0, !*(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL)) )
  {
    v9 = BfeTxnCommit(*((_QWORD *)&TlsValue[0] + 1), 0, v27);
    *((_QWORD *)&TlsValue[0] + 1) = 0;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v29, 0, (__int64)"BfeCallCommitEx", v9);
      }
      if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
      {
        v35 = v9;
        v40 = &v35;
        v38 = "BfeCallCommitEx";
        v39 = 16;
        v41 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v29,
          3,
          (__int64)&v37);
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
      if ( !LODWORD(qword_1800F2668[201]) )
        BfeTxnCoordinatorRollback();
      IsEnabledDeviceUsageInline = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
      *v12 = 0;
      if ( !IsEnabledDeviceUsageInline )
      {
        v14 = qword_1800F2668[205];
        v17 = GetTickCount64() - v14;
        if ( v17 >= HIDWORD(qword_1800F2668[203]) )
        {
          if ( (qword_1800F2668[337] & 0x20000000000LL) != 0 )
            McTemplateU0qqqq_EtwEventWriteTransfer(
              qword_1800F2668[206],
              v15,
              qword_1800F2668[204],
              v17,
              qword_1800F2668[206],
              SBYTE4(qword_1800F2668[203]));
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_LLL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              v16,
              LODWORD(qword_1800F2668[204]),
              v17,
              qword_1800F2668[206]);
          }
        }
      }
      qword_1800F2668[200] = 0;
      v18 = ReleaseSemaphore((HANDLE)qword_1800F2668[199], 1, 0);
      if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v18 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  TlsSetValue(gBfeContextComponent, 0);
  if ( a1 )
  {
    if ( v9 )
    {
      if ( !(unsigned int)BfeRpcIsKernelModeCaller() )
      {
        v28 = (unsigned __int16)v9;
        if ( (v9 & 0x1FFF0000) != 0x70000 )
          v28 = v9;
        RpcRaiseException(v28);
      }
      v30 = WfpErrorToNtStatus(v9);
      RpcRaiseException(v30);
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
0x180009c30  mov     r11, rsp
0x180009c33  push    rbp
0x180009c34  push    rbx
0x180009c35  lea     rbp, [r11-5Fh]
0x180009c39  sub     rsp, 0C8h
0x180009c40  mov     rax, cs:__security_cookie
0x180009c47  xor     rax, rsp
0x180009c4a  mov     [rbp+57h+var_48], rax
0x180009c4e  mov     [r11-18h], rsi
0x180009c52  xorps   xmm0, xmm0
0x180009c55  mov     [r11-20h], rdi
0x180009c59  mov     rsi, rcx
0x180009c5c  mov     [r11-28h], r12
0x180009c60  mov     rdi, rdx
0x180009c63  mov     [r11-38h], r14
0x180009c67  mov     [r11-40h], r15
0x180009c6b  mov     r15, r9
0x180009c6e  movsxd  r14, r8d
0x180009c71  movups  [rbp+57h+TlsValue], xmm0
0x180009c75  movups  [rbp+57h+var_88], xmm0
0x180009c79  mov     rbx, cs:WPP_GLOBAL_Control
0x180009c80  lea     r12, WPP_GLOBAL_Control
0x180009c87  cmp     rbx, r12
0x180009c8a  jz      short loc_180009C96
0x180009c8c  cmp     byte ptr [rbx+19h], 4
0x180009c90  jnb     loc_18000A0CB
0x180009c96  mov     r9d, 1; int
0x180009c9c  lea     rax, [rbp+57h+TlsValue]
0x180009ca0  mov     r8d, r9d; int
0x180009ca3  mov     [rsp+0D0h+lpTlsValue], rax; lpTlsValue
0x180009ca8  mov     rdx, rdi; int
0x180009cab  call    BfeCallCreate
0x180009cb0  mov     rbx, rax
0x180009cb3  test    rax, rax
0x180009cb6  jz      loc_180009DF1
0x180009cbc  mov     rax, qword ptr [rbp+57h+TlsValue]
0x180009cc0  cmp     qword ptr [rbp+57h+TlsValue+8], 0
0x180009cc5  mov     r15, [rsp+0D0h+var_38]
0x180009ccd  jz      short loc_180009CFF
0x180009ccf  test    rax, rax
0x180009cd2  jz      loc_180009D69
0x180009cd8  cmp     dword ptr [rax+24h], 0
0x180009cdc  jz      loc_180009D69
0x180009ce2  lea     rcx, [rax+20h]
0x180009ce6  mov     r8d, 2
0x180009cec  mov     eax, 1
0x180009cf1  lock cmpxchg [rcx], r8d
0x180009cf6  cmp     eax, 3
0x180009cf9  jz      loc_18000A0F6
0x180009cff  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180009d05  xor     edx, edx; lpTlsValue
0x180009d07  call    cs:__imp_TlsSetValue
0x180009d0d  mov     r14, [rsp+0D0h+var_30]
0x180009d15  test    rsi, rsi
0x180009d18  mov     rsi, [rsp+0C0h]
0x180009d20  mov     r12, [rsp+0D0h+var_20]
0x180009d28  mov     rdi, [rsp+0D0h+var_18]
0x180009d30  jz      short loc_180009D3F
0x180009d32  test    rbx, rbx
0x180009d35  jnz     loc_180009F9B
0x180009d3b  xor     eax, eax
0x180009d3d  jmp     short loc_180009D53
0x180009d3f  mov     ecx, ebx
0x180009d41  movzx   eax, bx
0x180009d44  and     ecx, 1FFF0000h
0x180009d4a  cmp     ecx, 70000h
0x180009d50  cmovnz  eax, ebx
0x180009d53  mov     rcx, [rbp+57h+var_48]
0x180009d57  xor     rcx, rsp; StackCookie
0x180009d5a  call    __security_check_cookie
0x180009d5f  add     rsp, 0C8h
0x180009d66  pop     rbx
0x180009d67  pop     rbp
0x180009d68  retn
0x180009d69  mov     rdi, qword ptr [rbp+57h+TlsValue+8]
0x180009d6d  call    BfeTxnLockCancelLockTimeout
0x180009d72  cmp     dword ptr cs:qword_1800F2668+648h, 0
0x180009d79  jnz     short loc_180009D80
0x180009d7b  call    BfeTxnCoordinatorRollback
0x180009d80  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x180009d85  mov     dword ptr [rdi], 0
0x180009d8b  test    eax, eax
0x180009d8d  jnz     short loc_180009DB0
0x180009d8f  mov     edi, dword ptr cs:qword_1800F2668+668h
0x180009d95  call    cs:__imp_GetTickCount64
0x180009d9b  mov     r14, rax
0x180009d9e  mov     eax, dword ptr cs:qword_1800F2668+65Ch
0x180009da4  sub     r14d, edi
0x180009da7  cmp     r14d, eax
0x180009daa  jnb     loc_18000A105
0x180009db0  mov     rcx, cs:qword_1800F2668+638h; hSemaphore
0x180009db7  xor     r8d, r8d; lpPreviousCount
0x180009dba  mov     edx, 1; lReleaseCount
0x180009dbf  mov     cs:qword_1800F2668+640h, 0
0x180009dca  call    cs:__imp_ReleaseSemaphore
0x180009dd0  mov     edi, eax
0x180009dd2  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x180009dd7  test    eax, eax
0x180009dd9  jz      loc_180009CFF
0x180009ddf  test    edi, edi
0x180009de1  jnz     loc_180009CFF
0x180009de7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009dec  jmp     loc_180009CFF
0x180009df1  mov     rbx, cs:1800EF0B0h
0x180009df8  xor     eax, eax
0x180009dfa  imul    r12, r14, 198h
0x180009e01  xorps   xmm0, xmm0
0x180009e04  movups  [rbp+57h+var_78], xmm0
0x180009e08  mov     [rbp+57h+var_68], rax
0x180009e0c  add     rbx, r12
0x180009e0f  cmp     r14d, 7
0x180009e13  jnb     short loc_180009E19
0x180009e15  cmp     [rbx], eax
0x180009e17  jnz     short loc_180009E1E
0x180009e19  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009e1e  cmp     dword ptr [rbx+150h], 0
0x180009e25  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x180009e2c  mov     [rsp+0D0h+var_28], r13
0x180009e34  jz      loc_180009FD1
0x180009e3a  lea     r14, [rbx+148h]
0x180009e41  xor     edi, edi
0x180009e43  mov     rcx, r14
0x180009e46  call    cs:__imp_RtlAcquireSRWLockShared
0x180009e4c  test    r15, r15
0x180009e4f  lea     r13, [rbx+120h]
0x180009e56  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180009e5d  lea     r8, [rbp+57h+var_78]
0x180009e61  cmovnz  rdx, r15
0x180009e65  mov     rcx, r13
0x180009e68  call    cs:__imp_RtlLookupEntryHashTable
0x180009e6e  test    rax, rax
0x180009e71  jz      loc_180009FC1
0x180009e77  lea     rbx, [rax-28h]
0x180009e7b  test    rbx, rbx
0x180009e7e  jz      short loc_180009E85
0x180009e80  cmp     [rbx], rdi
0x180009e83  jnz     short loc_180009E8A
0x180009e85  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009e8a  test    byte ptr [rbx+8], 8
0x180009e8e  jnz     loc_180009F89
0x180009e94  cmp     [rbx], rdi
0x180009e97  jnz     short loc_180009EA8
0x180009e99  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009e9e  cmp     [rbx], rdi
0x180009ea1  jnz     short loc_180009EA8
0x180009ea3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009ea8  mov     rax, [rbx]
0x180009eab  lea     rcx, [rbx+90h]
0x180009eb2  mov     rax, [rax+68h]
0x180009eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ebb  cmp     rax, r15
0x180009ebe  jnz     loc_180009F89
0x180009ec4  mov     rcx, r14
0x180009ec7  call    cs:__imp_RtlReleaseSRWLockShared
0x180009ecd  mov     rcx, rbx
0x180009ed0  call    BfeObjectDelete
0x180009ed5  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x180009edc  mov     rbx, rax
0x180009edf  mov     r13, [rsp+0D0h+var_28]
0x180009ee7  test    rax, rax
0x180009eea  jz      loc_180009FEA
0x180009ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ef7  lea     r12, WPP_GLOBAL_Control
0x180009efe  cmp     rcx, r12
0x180009f01  jz      short loc_180009F29
0x180009f03  cmp     byte ptr [rcx+19h], 2
0x180009f07  jb      short loc_180009F29
0x180009f09  test    byte ptr [rcx+1Ch], 1
0x180009f0d  jz      short loc_180009F29
0x180009f0f  mov     rcx, [rcx+10h]
0x180009f13  mov     edx, 1Ah
0x180009f18  mov     [rsp+28h], ebx
0x180009f1c  xor     r9d, r9d
0x180009f1f  mov     [rsp+0D0h+lpTlsValue], rdi
0x180009f24  call    WPP_SF_Ssd
0x180009f29  cmp     dword ptr cs:1800EF078h, 0
0x180009f30  jz      loc_180009CBC
0x180009f36  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x180009f3d  jz      loc_180009CBC
0x180009f43  lea     rax, [rbp+57h+var_A0]
0x180009f47  mov     [rbp+57h+var_A0], ebx
0x180009f4a  mov     [rbp+57h+var_58], rax
0x180009f4e  lea     rdx, WFP_USERMODE_ERROR
0x180009f55  lea     rax, [rbp+57h+var_78]
0x180009f59  mov     [rbp+57h+var_68], rdi
0x180009f5d  mov     r9d, 3
0x180009f63  mov     [rsp+0D0h+lpTlsValue], rax
0x180009f68  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180009f6f  mov     [rbp+57h+var_60], 14h
0x180009f77  mov     [rbp+57h+var_50], 4
0x180009f7f  call    McGenEventWrite_EtwEventWriteTransfer
0x180009f84  jmp     loc_180009CBC
0x180009f89  lea     rdx, [rbp+57h+var_78]
0x180009f8d  mov     rcx, r13
0x180009f90  call    cs:__imp_RtlGetNextEntryHashTable
0x180009f96  jmp     loc_180009E6E
0x180009f9b  call    BfeRpcIsKernelModeCaller
0x180009fa0  test    eax, eax
0x180009fa2  jnz     loc_18000A0BA
0x180009fa8  mov     eax, ebx
0x180009faa  movzx   ecx, bx
0x180009fad  and     eax, 1FFF0000h
0x180009fb2  cmp     eax, 70000h
0x180009fb7  cmovnz  ecx, ebx; exception
0x180009fba  call    cs:__imp_RpcRaiseException
0x180009fc0  int     3; Trap to Debugger
0x180009fc1  mov     rcx, r14
0x180009fc4  call    cs:__imp_RtlReleaseSRWLockShared
0x180009fca  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x180009fd1  mov     r8, cs:1800EF0B0h
0x180009fd8  mov     rdx, rdi
0x180009fdb  mov     r8d, [r12+r8+48h]
0x180009fe0  call    WfpReportSysErrorAsWinError
0x180009fe5  jmp     loc_180009EDC
0x180009fea  mov     rax, qword ptr [rbp+57h+TlsValue]
0x180009fee  test    rax, rax
0x180009ff1  jz      short loc_180009FFA
0x180009ff3  xor     ebx, ebx
0x180009ff5  cmp     [rax+24h], ebx
0x180009ff8  jnz     short loc_18000A062
0x180009ffa  mov     rcx, qword ptr [rbp+57h+TlsValue+8]
0x180009ffe  xor     edx, edx
0x18000a000  call    BfeTxnCommit
0x18000a005  mov     rbx, rax
0x18000a008  mov     qword ptr [rbp+57h+TlsValue+8], 0
0x18000a010  test    rax, rax
0x18000a013  jz      short loc_18000A05E
0x18000a015  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a01c  lea     rax, WPP_GLOBAL_Control
0x18000a023  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x18000a02a  cmp     rcx, rax
0x18000a02d  jz      short loc_18000A055
0x18000a02f  cmp     byte ptr [rcx+19h], 2
0x18000a033  jb      short loc_18000A055
0x18000a035  test    byte ptr [rcx+1Ch], 1
0x18000a039  jz      short loc_18000A055
0x18000a03b  mov     rcx, [rcx+10h]
0x18000a03f  mov     edx, 1Ah
0x18000a044  mov     [rsp+28h], ebx
0x18000a048  xor     r9d, r9d
0x18000a04b  mov     [rsp+0D0h+lpTlsValue], rdi
0x18000a050  call    WPP_SF_Ssd
0x18000a055  cmp     dword ptr cs:1800EF078h, 0
0x18000a05c  jnz     short loc_18000A06E
0x18000a05e  mov     rax, qword ptr [rbp+57h+TlsValue]
0x18000a062  lea     r12, WPP_GLOBAL_Control
0x18000a069  jmp     loc_180009CC0
0x18000a06e  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x18000a075  jz      short loc_18000A05E
0x18000a077  lea     rax, [rbp+57h+var_A0]
0x18000a07b  mov     [rbp+57h+var_A0], ebx
0x18000a07e  mov     [rbp+57h+var_58], rax
0x18000a082  lea     rdx, WFP_USERMODE_ERROR
0x18000a089  lea     rax, [rbp+57h+var_78]
0x18000a08d  mov     [rbp+57h+var_68], rdi
0x18000a091  mov     r9d, 3
0x18000a097  mov     [rsp+0D0h+lpTlsValue], rax
0x18000a09c  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000a0a3  mov     [rbp+57h+var_60], 10h
0x18000a0ab  mov     [rbp+57h+var_50], 4
0x18000a0b3  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a0b8  jmp     short loc_18000A05E
0x18000a0ba  mov     rcx, rbx
0x18000a0bd  call    WfpErrorToNtStatus
0x18000a0c2  mov     ecx, eax; exception
0x18000a0c4  call    cs:__imp_RpcRaiseException
0x18000a0ca  int     3; Trap to Debugger
0x18000a0cb  test    byte ptr [rbx+1Ch], 2
0x18000a0cf  jz      loc_180009C96
0x18000a0d5  mov     rbx, [rbx+10h]
0x18000a0d9  mov     ecx, r14d
0x18000a0dc  call    BfeObjectTypeIdToString
0x18000a0e1  mov     r9, rax
0x18000a0e4  mov     [rsp+0D0h+lpTlsValue], r15
0x18000a0e9  mov     rcx, rbx
0x18000a0ec  call    WPP_SF_SI
0x18000a0f1  jmp     loc_180009C96
0x18000a0f6  mov     edx, 1
0x18000a0fb  call    BfeTxnAbort
0x18000a100  jmp     loc_180009CFF
0x18000a105  test    byte ptr cs:qword_1800F2668+0A8Dh, 2
0x18000a10c  jz      loc_180088832
0x18000a112  mov     ecx, dword ptr cs:qword_1800F2668+670h
0x18000a118  mov     r9d, r14d
0x18000a11b  mov     r8d, dword ptr cs:qword_1800F2668+660h
0x18000a122  mov     [rsp+28h], eax
0x18000a126  mov     dword ptr [rsp+0D0h+lpTlsValue], ecx
0x18000a12a  call    McTemplateU0qqqq_EtwEventWriteTransfer
0x18000a12f  nop
0x18000a130  jmp     loc_180088832
0x180088832  mov     rcx, cs:WPP_GLOBAL_Control
0x180088839  cmp     rcx, r12
0x18008883c  jz      loc_180009DB0
0x180088842  cmp     byte ptr [rcx+19h], 3
0x180088846  jb      loc_180009DB0
0x18008884c  test    byte ptr [rcx+1Ch], 2
0x180088850  jz      loc_180009DB0
0x180088856  mov     eax, dword ptr cs:qword_1800F2668+670h
0x18008885c  mov     edx, 0Bh
0x180088861  mov     r9d, dword ptr cs:qword_1800F2668+660h
  ... truncated ...
```
