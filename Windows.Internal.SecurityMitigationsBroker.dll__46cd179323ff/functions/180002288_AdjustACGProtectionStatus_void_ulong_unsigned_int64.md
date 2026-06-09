# AdjustACGProtectionStatus(void *,ulong,unsigned __int64)

- ea: `0x180002288`
- end: `0x1800025ee`
- name: `?AdjustACGProtectionStatus@@YAJPEAXK_K@Z`
- size: `870`
- prototype: `signed int __fastcall(HANDLE ProcessHandle, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002d70`

## callees

- `0x180002288`
- `0x1800025f4`
- `0x180003060`
- `0x18000342c`
- `0x180006980`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x1800022ce`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x1800022ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000234d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000234d`
- `ntdll!NtSetInformationProcess` at `0x180002568`
- `ntdll!NtSetInformationProcess` at `0x180002568`
- `ntdll!RtlNtStatusToDosError` at `0x1800025e3`
- `ntdll!RtlNtStatusToDosError` at `0x1800025e3`

## pseudocode

```c
signed int __fastcall AdjustACGProtectionStatus(HANDLE ProcessHandle, unsigned int a2, unsigned __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // r8
  signed int result; // eax
  char v11; // al
  __int64 *v12; // rdx
  bool v13; // cl
  __int64 v14; // rcx
  __int64 v15; // r8
  NTSTATUS v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  NTSTATUS v19; // r14d
  DWORD LastError; // [rsp+30h] [rbp-A8h] BYREF
  bool v21; // [rsp+38h] [rbp-A0h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-98h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-90h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-88h] BYREF
  __int64 ProcessInformation; // [rsp+58h] [rbp-80h] BYREF
  _BYTE v26[16]; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int64 *v27; // [rsp+70h] [rbp-68h]
  __int64 v28; // [rsp+78h] [rbp-60h]
  DWORD *v29; // [rsp+80h] [rbp-58h]
  __int64 v30; // [rsp+88h] [rbp-50h]
  DWORD *p_LastError; // [rsp+90h] [rbp-48h]
  __int64 v32; // [rsp+98h] [rbp-40h]

  v24 = 0;
  if ( !(unsigned int)GetProcessMitigationPolicy(ProcessHandle, 2, &v24, 4) )
  {
    if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 8) != 0 )
    {
      v23 = a2;
      LastError = GetLastError();
      v22 = a3;
      v27 = &v22;
      v29 = &v23;
      p_LastError = &LastError;
      v28 = 8;
      v30 = 4;
      v32 = 4;
      McGenEventWrite_EventWriteTransfer(v8, GetProcessMitigationPolicyFailed, v9, 4, v26);
    }
    result = GetLastError();
LABEL_5:
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v11 = Microsoft_Windows_SecurityMitigationsBrokerEnableBits;
  if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
  {
    v23 = v24;
    LastError = a2;
    v27 = &v22;
    v29 = &LastError;
    p_LastError = &v23;
    v22 = a3;
    v28 = 8;
    v30 = 4;
    v32 = 4;
    McGenEventWrite_EventWriteTransfer(v6, ProcessACGState, v7, 4, v26);
    v11 = Microsoft_Windows_SecurityMitigationsBrokerEnableBits;
  }
  if ( (v24 & 1) == 0 )
  {
    if ( (v11 & 4) != 0 )
    {
      v12 = ProcessACGOff;
LABEL_15:
      LastError = a2;
      v27 = &v22;
      v22 = a3;
      v29 = &LastError;
      v28 = 8;
      v30 = 4;
      McGenEventWrite_EventWriteTransfer(v24, v12, v7, 3, v26);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  if ( (v24 & 2) != 0 )
  {
    if ( (v11 & 4) != 0 )
    {
      v12 = ProcessIsInTelemetryMode;
      goto LABEL_15;
    }
LABEL_16:
    v13 = 0;
LABEL_17:
    CacheACGStatusForTroubleshooting(v13);
    return 0;
  }
  if ( (v24 & 4) == 0 )
  {
    if ( (v11 & 4) != 0 )
    {
      LastError = a2;
      v27 = &v22;
      v22 = a3;
      v29 = &LastError;
      v28 = 8;
      v30 = 4;
      McGenEventWrite_EventWriteTransfer(v24, ProcessDoesNotAllowRemoteDowngrade, v7, 3, v26);
    }
    v13 = 1;
    goto LABEL_17;
  }
  v21 = 0;
  result = QueryACGPolicyForDriverId(a3, a2, &v21);
  if ( result >= 0 && !v21 )
  {
    if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
    {
      LastError = a2;
      v27 = &v22;
      v22 = a3;
      v29 = &LastError;
      v28 = 8;
      v30 = 4;
      McGenEventWrite_EventWriteTransfer(v14, TurnOffACGDueToUnsupportiveDriver, v15, 3, v26);
    }
    v24 = 0;
    ProcessInformation = 2;
    v16 = NtSetInformationProcess(ProcessHandle, ProcessCookie|ProcessUserModeIOPL, &ProcessInformation, 8u);
    v19 = v16;
    if ( v16 < 0 )
    {
      if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 8) != 0 )
      {
        v23 = v16;
        LastError = a2;
        v27 = &v22;
        v22 = a3;
        v29 = &LastError;
        p_LastError = &v23;
        v28 = 8;
        v30 = 4;
        v32 = 4;
        McGenEventWrite_EventWriteTransfer(v17, SetProcessMitigationPolicyFailed, v18, 4, v26);
      }
      result = RtlNtStatusToDosError(v19);
      goto LABEL_5;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002288  mov     [rsp+arg_18], rbx
0x18000228d  push    rsi
0x18000228e  push    rdi
0x18000228f  push    r12
0x180002291  push    r14
0x180002293  push    r15
0x180002295  sub     rsp, 0B0h
0x18000229c  mov     rax, cs:__security_cookie
0x1800022a3  xor     rax, rsp
0x1800022a6  mov     [rsp+0D8h+var_38], rax
0x1800022ae  xor     r15d, r15d
0x1800022b1  mov     rsi, r8
0x1800022b4  mov     edi, edx
0x1800022b6  mov     [rsp+0D8h+var_88], r15d
0x1800022bb  lea     r8, [rsp+0D8h+var_88]
0x1800022c0  mov     r14, rcx
0x1800022c3  lea     r12d, [r15+4]
0x1800022c7  mov     r9d, r12d
0x1800022ca  lea     edx, [r15+2]
0x1800022ce  call    cs:__imp_GetProcessMitigationPolicy
0x1800022d4  lea     ebx, [r15+8]
0x1800022d8  test    eax, eax
0x1800022da  jnz     loc_180002368
0x1800022e0  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, bl
0x1800022e6  jz      short loc_18000234D
0x1800022e8  call    cs:__imp_GetLastError
0x1800022ee  mov     r9d, r12d
0x1800022f1  mov     [rsp+0D8h+var_90], edi
0x1800022f5  mov     [rsp+0D8h+var_A8], eax
0x1800022f9  lea     rdx, GetProcessMitigationPolicyFailed
0x180002300  lea     rax, [rsp+0D8h+var_98]
0x180002305  mov     [rsp+0D8h+var_98], rsi
0x18000230a  mov     [rsp+0D8h+var_68], rax
0x18000230f  lea     rax, [rsp+0D8h+var_90]
0x180002314  mov     [rsp+0D8h+var_58], rax
0x18000231c  lea     rax, [rsp+0D8h+var_A8]
0x180002321  mov     [rsp+0D8h+var_48], rax
0x180002329  lea     rax, [rsp+0D8h+var_78]
0x18000232e  mov     [rsp+0D8h+var_B8], rax
0x180002333  mov     [rsp+0D8h+var_60], rbx
0x180002338  mov     [rsp+0D8h+var_50], r12
0x180002340  mov     [rsp+0D8h+var_40], r12
0x180002348  call    McGenEventWrite_EventWriteTransfer
0x18000234d  call    cs:__imp_GetLastError
0x180002353  test    eax, eax
0x180002355  jle     loc_18000244F
0x18000235b  movzx   eax, ax
0x18000235e  or      eax, 80070000h
0x180002363  jmp     loc_18000244F
0x180002368  mov     eax, cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits
0x18000236e  test    r12b, al
0x180002371  jz      short loc_1800023DC
0x180002373  mov     eax, [rsp+0D8h+var_88]
0x180002377  lea     rdx, ProcessACGState
0x18000237e  mov     [rsp+0D8h+var_90], eax
0x180002382  mov     r9d, r12d
0x180002385  lea     rax, [rsp+0D8h+var_98]
0x18000238a  mov     [rsp+0D8h+var_A8], edi
0x18000238e  mov     [rsp+0D8h+var_68], rax
0x180002393  lea     rax, [rsp+0D8h+var_A8]
0x180002398  mov     [rsp+0D8h+var_58], rax
0x1800023a0  lea     rax, [rsp+0D8h+var_90]
0x1800023a5  mov     [rsp+0D8h+var_48], rax
0x1800023ad  lea     rax, [rsp+0D8h+var_78]
0x1800023b2  mov     [rsp+0D8h+var_B8], rax
0x1800023b7  mov     [rsp+0D8h+var_98], rsi
0x1800023bc  mov     [rsp+0D8h+var_60], rbx
0x1800023c1  mov     [rsp+0D8h+var_50], r12
0x1800023c9  mov     [rsp+0D8h+var_40], r12
0x1800023d1  call    McGenEventWrite_EventWriteTransfer
0x1800023d6  mov     eax, cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits
0x1800023dc  mov     ecx, [rsp+0D8h+var_88]
0x1800023e0  test    cl, 1
0x1800023e3  jnz     short loc_1800023F3
0x1800023e5  test    r12b, al
0x1800023e8  jz      short loc_180002446
0x1800023ea  lea     rdx, ProcessACGOff
0x1800023f1  jmp     short loc_180002404
0x1800023f3  test    cl, 2
0x1800023f6  jz      short loc_180002477
0x1800023f8  test    r12b, al
0x1800023fb  jz      short loc_180002446
0x1800023fd  lea     rdx, ProcessIsInTelemetryMode
0x180002404  lea     rax, [rsp+0D8h+var_98]
0x180002409  mov     [rsp+0D8h+var_A8], edi
0x18000240d  mov     [rsp+0D8h+var_68], rax
0x180002412  mov     r9d, 3
0x180002418  lea     rax, [rsp+0D8h+var_A8]
0x18000241d  mov     [rsp+0D8h+var_98], rsi
0x180002422  mov     [rsp+0D8h+var_58], rax
0x18000242a  lea     rax, [rsp+0D8h+var_78]
0x18000242f  mov     [rsp+0D8h+var_B8], rax
0x180002434  mov     [rsp+0D8h+var_60], rbx
0x180002439  mov     [rsp+0D8h+var_50], r12
0x180002441  call    McGenEventWrite_EventWriteTransfer
0x180002446  xor     ecx, ecx; bool
0x180002448  call    ?CacheACGStatusForTroubleshooting@@YAX_N@Z; CacheACGStatusForTroubleshooting(bool)
0x18000244d  xor     eax, eax
0x18000244f  mov     rcx, [rsp+0D8h+var_38]
0x180002457  xor     rcx, rsp; StackCookie
0x18000245a  call    __security_check_cookie
0x18000245f  mov     rbx, [rsp+0D8h+arg_18]
0x180002467  add     rsp, 0B0h
0x18000246e  pop     r15
0x180002470  pop     r14
0x180002472  pop     r12
0x180002474  pop     rdi
0x180002475  pop     rsi
0x180002476  retn
0x180002477  test    r12b, cl
0x18000247a  jnz     short loc_1800024D1
0x18000247c  test    r12b, al
0x18000247f  jz      short loc_1800024CA
0x180002481  lea     rax, [rsp+0D8h+var_98]
0x180002486  mov     [rsp+0D8h+var_A8], edi
0x18000248a  mov     [rsp+0D8h+var_68], rax
0x18000248f  lea     rdx, ProcessDoesNotAllowRemoteDowngrade
0x180002496  lea     rax, [rsp+0D8h+var_A8]
0x18000249b  mov     [rsp+0D8h+var_98], rsi
0x1800024a0  mov     [rsp+0D8h+var_58], rax
0x1800024a8  mov     r9d, 3
0x1800024ae  lea     rax, [rsp+0D8h+var_78]
0x1800024b3  mov     [rsp+0D8h+var_60], rbx
0x1800024b8  mov     [rsp+0D8h+var_B8], rax
0x1800024bd  mov     [rsp+0D8h+var_50], r12
0x1800024c5  call    McGenEventWrite_EventWriteTransfer
0x1800024ca  mov     cl, 1
0x1800024cc  jmp     loc_180002448
0x1800024d1  lea     r8, [rsp+0D8h+var_A0]; bool *
0x1800024d6  mov     [rsp+0D8h+var_A0], r15b
0x1800024db  mov     edx, edi; unsigned int
0x1800024dd  mov     rcx, rsi; unsigned __int64
0x1800024e0  call    ?QueryACGPolicyForDriverId@@YAJ_KKPEA_N@Z; QueryACGPolicyForDriverId(unsigned __int64,ulong,bool *)
0x1800024e5  test    eax, eax
0x1800024e7  js      loc_18000244F
0x1800024ed  cmp     [rsp+0D8h+var_A0], r15b
0x1800024f2  jnz     loc_18000244F
0x1800024f8  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, r12b
0x1800024ff  jz      short loc_18000254A
0x180002501  lea     rax, [rsp+0D8h+var_98]
0x180002506  mov     [rsp+0D8h+var_A8], edi
0x18000250a  mov     [rsp+0D8h+var_68], rax
0x18000250f  lea     rdx, TurnOffACGDueToUnsupportiveDriver
0x180002516  lea     rax, [rsp+0D8h+var_A8]
0x18000251b  mov     [rsp+0D8h+var_98], rsi
0x180002520  mov     [rsp+0D8h+var_58], rax
0x180002528  mov     r9d, 3
0x18000252e  lea     rax, [rsp+0D8h+var_78]
0x180002533  mov     [rsp+0D8h+var_60], rbx
0x180002538  mov     [rsp+0D8h+var_B8], rax
0x18000253d  mov     [rsp+0D8h+var_50], r12
0x180002545  call    McGenEventWrite_EventWriteTransfer
0x18000254a  mov     r9d, ebx; ProcessInformationLength
0x18000254d  mov     [rsp+0D8h+var_88], r15d
0x180002552  lea     r8, [rsp+0D8h+ProcessInformation]; ProcessInformation
0x180002557  mov     [rsp+0D8h+ProcessInformation], 2
0x180002560  mov     edx, 34h ; '4'; ProcessInformationClass
0x180002565  mov     rcx, r14; ProcessHandle
0x180002568  call    cs:__imp_NtSetInformationProcess
0x18000256e  mov     r14d, eax
0x180002571  test    eax, eax
0x180002573  jns     loc_18000244D
0x180002579  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, bl
0x18000257f  jz      short loc_1800025E0
0x180002581  mov     [rsp+0D8h+var_90], eax
0x180002585  lea     rdx, SetProcessMitigationPolicyFailed
0x18000258c  lea     rax, [rsp+0D8h+var_98]
0x180002591  mov     [rsp+0D8h+var_A8], edi
0x180002595  mov     [rsp+0D8h+var_68], rax
0x18000259a  mov     r9d, r12d
0x18000259d  lea     rax, [rsp+0D8h+var_A8]
0x1800025a2  mov     [rsp+0D8h+var_98], rsi
0x1800025a7  mov     [rsp+0D8h+var_58], rax
0x1800025af  lea     rax, [rsp+0D8h+var_90]
0x1800025b4  mov     [rsp+0D8h+var_48], rax
0x1800025bc  lea     rax, [rsp+0D8h+var_78]
0x1800025c1  mov     [rsp+0D8h+var_B8], rax
0x1800025c6  mov     [rsp+0D8h+var_60], rbx
0x1800025cb  mov     [rsp+0D8h+var_50], r12
0x1800025d3  mov     [rsp+0D8h+var_40], r12
0x1800025db  call    McGenEventWrite_EventWriteTransfer
0x1800025e0  mov     ecx, r14d; Status
0x1800025e3  call    cs:__imp_RtlNtStatusToDosError
0x1800025e9  jmp     loc_180002353
```
