# BfeRpcFilterDeleteById

- ea: `0x180009700`
- end: `0x180009a8c`
- name: `BfeRpcFilterDeleteById`
- size: `908`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800052ac`
- `0x180008930`
- `0x180009700`
- `0x180009aa0`
- `0x18000ad28`
- `0x18000ba68`
- `0x18000f1a8`
- `0x180010ad0`
- `0x18001236c`
- `0x1800223a8`
- `0x180023e78`
- `0x180049750`
- `0x1800575c4`
- `0x180058b30`
- `0x18008b010`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x18000983b`
- `ntdll!RtlLookupEntryHashTable` at `0x18000983b`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009963`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009963`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000981c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000981c`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009899`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009899`
- `RPCRT4!RpcRaiseException` at `0x18000998d`
- `RPCRT4!RpcRaiseException` at `0x180009a58`
- `RPCRT4!RpcRaiseException` at `0x18000998d`
- `RPCRT4!RpcRaiseException` at `0x180009a58`

## string_xrefs

- `0x1800097fb`: `BfeObjectDeleteById`
- `0x1800098b0`: `BfeObjectDeleteById`
- `0x180009994`: `BfeObjectDeleteById`
- `0x1800099f5`: `BfeCallCommitEx`

## pseudocode

```c
__int64 __fastcall BfeRpcFilterDeleteById(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 result; // rax
  __int64 v9; // rbx
  const char *v10; // rdi
  __int64 v11; // r14
  _BYTE *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // r15
  __int64 i; // rax
  _BYTE *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r8
  RPC_STATUS v19; // ecx
  RPC_STATUS v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  int v23; // edx
  int v24; // r8d
  int v25; // [rsp+30h] [rbp-39h] BYREF
  _OWORD TlsValue[2]; // [rsp+38h] [rbp-31h] BYREF
  __int128 v27; // [rsp+58h] [rbp-11h] BYREF
  const char *v28; // [rsp+68h] [rbp-1h]
  __int64 v29; // [rsp+70h] [rbp+7h]
  int *v30; // [rsp+78h] [rbp+Fh]
  __int64 v31; // [rsp+80h] [rbp+17h]

  memset(TlsValue, 0, sizeof(TlsValue));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v21 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v22 = BfeObjectTypeIdToString(5);
    WPP_SF_SI(v21, v23, v24, v22, a3);
  }
  v7 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( !v7 )
  {
    v9 = *(_QWORD *)&MEMORY[0x1800EF094][7];
    v28 = 0;
    v27 = 0;
    if ( !*(_DWORD *)(*(_QWORD *)&MEMORY[0x1800EF094][7] + 2040LL) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v10 = "BfeObjectDeleteById";
    if ( *(_DWORD *)(v9 + 2376) )
    {
      v11 = v9 + 2368;
      v12 = 0;
      RtlAcquireSRWLockShared(v9 + 2368);
      v13 = -1;
      v14 = v9 + 2328;
      if ( a3 )
        v13 = a3;
      for ( i = RtlLookupEntryHashTable(v9 + 2328, v13, &v27); i; i = RtlGetNextEntryHashTable(v14, &v27) )
      {
        v16 = (_BYTE *)(i - 40);
        if ( i == 40 || !*(_QWORD *)v16 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (v16[8] & 8) == 0 )
        {
          if ( !*(_QWORD *)v16 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( !*(_QWORD *)v16 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          if ( (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v16 + 104LL))(v16 + 144) == a3 )
          {
            v12 = v16;
            break;
          }
        }
      }
      RtlReleaseSRWLockShared(v11);
      if ( v12 )
      {
        v17 = BfeObjectDelete(v12);
        v10 = "BfeObjectDeleteById";
        goto LABEL_28;
      }
      v10 = "BfeObjectDeleteById";
    }
    v17 = WfpReportSysErrorAsWinError(
            v6,
            "BfeObjectDeleteById",
            *(unsigned int *)(*(_QWORD *)&MEMORY[0x1800EF094][7] + 2112LL));
LABEL_28:
    v7 = v17;
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v18, 0, (__int64)"BfeObjectDeleteById", v17);
      }
      if ( !MEMORY[0x1800EF078] || (qword_1800F2668[337] & 0x10000000000LL) == 0 )
        goto LABEL_4;
      v29 = 20;
    }
    else
    {
      if ( *(_QWORD *)&TlsValue[0] )
      {
        v7 = 0;
        if ( *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
          goto LABEL_4;
      }
      v7 = BfeTxnCommit(*((_QWORD *)&TlsValue[0] + 1), 0, v18);
      *((_QWORD *)&TlsValue[0] + 1) = 0;
      if ( !v7 )
        goto LABEL_4;
      v10 = "BfeCallCommitEx";
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v18, 0, (__int64)"BfeCallCommitEx", v7);
      }
      if ( !MEMORY[0x1800EF078] || (qword_1800F2668[337] & 0x10000000000LL) == 0 )
        goto LABEL_4;
      v29 = 16;
    }
    v25 = v7;
    v30 = &v25;
    v28 = v10;
    v31 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      &MICROSOFT_WFP_PROVIDER_Context,
      (__int64)WFP_USERMODE_ERROR,
      v18,
      3,
      (__int64)&v27);
  }
LABEL_4:
  BfeCallDestroy(TlsValue);
  if ( a1 )
  {
    if ( v7 )
    {
      if ( !(unsigned int)BfeRpcIsKernelModeCaller() )
      {
        v19 = (unsigned __int16)v7;
        if ( (v7 & 0x1FFF0000) != 0x70000 )
          v19 = v7;
        RpcRaiseException(v19);
      }
      v20 = WfpErrorToNtStatus(v7);
      RpcRaiseException(v20);
    }
    return 0;
  }
  else
  {
    result = (unsigned __int16)v7;
    if ( (v7 & 0x1FFF0000) != 0x70000 )
      return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x180009700  mov     [rsp-8+arg_18], rbx
0x180009705  push    rbp
0x180009706  push    rsi
0x180009707  push    rdi
0x180009708  push    r12
0x18000970a  push    r13
0x18000970c  push    r14
0x18000970e  push    r15
0x180009710  lea     rbp, [rsp-27h]
0x180009715  sub     rsp, 90h
0x18000971c  mov     rax, cs:__security_cookie
0x180009723  xor     rax, rsp
0x180009726  mov     [rbp+57h+var_38], rax
0x18000972a  xorps   xmm0, xmm0
0x18000972d  mov     rsi, r8
0x180009730  movups  [rbp+57h+TlsValue], xmm0
0x180009734  mov     rdi, rdx
0x180009737  mov     r12, rcx
0x18000973a  movups  [rbp+57h+var_78], xmm0
0x18000973e  mov     rbx, cs:WPP_GLOBAL_Control
0x180009745  lea     rax, WPP_GLOBAL_Control
0x18000974c  cmp     rbx, rax
0x18000974f  jz      short loc_18000975B
0x180009751  cmp     byte ptr [rbx+19h], 4
0x180009755  jnb     loc_180009A5F
0x18000975b  lea     rax, [rbp+57h+TlsValue]
0x18000975f  mov     rdx, rdi; int
0x180009762  mov     [rsp+0C0h+lpTlsValue], rax; lpTlsValue
0x180009767  mov     eax, 1
0x18000976c  mov     r9d, eax; int
0x18000976f  mov     r8d, eax; int
0x180009772  call    BfeCallCreate
0x180009777  xor     r13d, r13d
0x18000977a  mov     rbx, rax
0x18000977d  test    rax, rax
0x180009780  jz      short loc_1800097D9
0x180009782  lea     rcx, [rbp+57h+TlsValue]
0x180009786  call    BfeCallDestroy
0x18000978b  test    r12, r12
0x18000978e  jz      short loc_18000979E
0x180009790  test    rbx, rbx
0x180009793  jnz     loc_18000996E
0x180009799  mov     eax, r13d
0x18000979c  jmp     short loc_1800097B2
0x18000979e  mov     ecx, ebx
0x1800097a0  movzx   eax, bx
0x1800097a3  and     ecx, 1FFF0000h
0x1800097a9  cmp     ecx, 70000h
0x1800097af  cmovnz  eax, ebx
0x1800097b2  mov     rcx, [rbp+57h+var_38]
0x1800097b6  xor     rcx, rsp; StackCookie
0x1800097b9  call    __security_check_cookie
0x1800097be  mov     rbx, [rsp+0C0h+arg_18]
0x1800097c6  add     rsp, 90h
0x1800097cd  pop     r15
0x1800097cf  pop     r14
0x1800097d1  pop     r13
0x1800097d3  pop     r12
0x1800097d5  pop     rdi
0x1800097d6  pop     rsi
0x1800097d7  pop     rbp
0x1800097d8  retn
0x1800097d9  mov     rbx, cs:1800EF0B0h
0x1800097e0  xor     eax, eax
0x1800097e2  xorps   xmm0, xmm0
0x1800097e5  mov     [rbp+57h+var_58], rax
0x1800097e9  movups  [rbp+57h+var_68], xmm0
0x1800097ed  cmp     [rbx+7F8h], r13d
0x1800097f4  jnz     short loc_1800097FB
0x1800097f6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800097fb  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x180009802  cmp     [rbx+948h], r13d
0x180009809  jz      loc_18000999B
0x18000980f  lea     r14, [rbx+940h]
0x180009816  mov     rdi, r13
0x180009819  mov     rcx, r14
0x18000981c  call    cs:__imp_RtlAcquireSRWLockShared
0x180009822  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009826  lea     r15, [rbx+918h]
0x18000982d  test    rsi, rsi
0x180009830  lea     r8, [rbp+57h+var_68]
0x180009834  mov     rcx, r15
0x180009837  cmovnz  rdx, rsi
0x18000983b  call    cs:__imp_RtlLookupEntryHashTable
0x180009841  test    rax, rax
0x180009844  jz      short loc_180009896
0x180009846  lea     rbx, [rax-28h]
0x18000984a  test    rbx, rbx
0x18000984d  jz      short loc_180009854
0x18000984f  cmp     [rbx], r13
0x180009852  jnz     short loc_180009859
0x180009854  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009859  test    byte ptr [rbx+8], 8
0x18000985d  jnz     loc_18000995C
0x180009863  cmp     [rbx], r13
0x180009866  jnz     short loc_180009877
0x180009868  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000986d  cmp     [rbx], r13
0x180009870  jnz     short loc_180009877
0x180009872  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009877  mov     rax, [rbx]
0x18000987a  lea     rcx, [rbx+90h]
0x180009881  mov     rax, [rax+68h]
0x180009885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000988a  cmp     rax, rsi
0x18000988d  jnz     loc_18000995C
0x180009893  mov     rdi, rbx
0x180009896  mov     rcx, r14
0x180009899  call    cs:__imp_RtlReleaseSRWLockShared
0x18000989f  test    rdi, rdi
0x1800098a2  jz      loc_180009994
0x1800098a8  mov     rcx, rdi
0x1800098ab  call    BfeObjectDelete
0x1800098b0  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x1800098b7  mov     rbx, rax
0x1800098ba  test    rax, rax
0x1800098bd  jz      loc_1800099B6
0x1800098c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098ca  lea     rax, WPP_GLOBAL_Control
0x1800098d1  cmp     rcx, rax
0x1800098d4  jz      short loc_1800098FC
0x1800098d6  cmp     byte ptr [rcx+19h], 2
0x1800098da  jb      short loc_1800098FC
0x1800098dc  test    byte ptr [rcx+1Ch], 1
0x1800098e0  jz      short loc_1800098FC
0x1800098e2  mov     rcx, [rcx+10h]
0x1800098e6  mov     edx, 1Ah
0x1800098eb  mov     [rsp+0C0h+var_98], ebx
0x1800098ef  xor     r9d, r9d
0x1800098f2  mov     [rsp+0C0h+lpTlsValue], rdi
0x1800098f7  call    WPP_SF_Ssd
0x1800098fc  cmp     cs:1800EF078h, r13d
0x180009903  jz      loc_180009782
0x180009909  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x180009910  jz      loc_180009782
0x180009916  mov     [rbp+57h+var_50], 14h
0x18000991e  lea     rax, [rbp+57h+var_90]
0x180009922  mov     [rbp+57h+var_90], ebx
0x180009925  mov     [rbp+57h+var_48], rax
0x180009929  lea     rdx, WFP_USERMODE_ERROR
0x180009930  lea     rax, [rbp+57h+var_68]
0x180009934  mov     [rbp+57h+var_58], rdi
0x180009938  mov     r9d, 3
0x18000993e  mov     [rsp+0C0h+lpTlsValue], rax
0x180009943  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000994a  mov     [rbp+57h+var_40], 4
0x180009952  call    McGenEventWrite_EtwEventWriteTransfer
0x180009957  jmp     loc_180009782
0x18000995c  lea     rdx, [rbp+57h+var_68]
0x180009960  mov     rcx, r15
0x180009963  call    cs:__imp_RtlGetNextEntryHashTable
0x180009969  jmp     loc_180009841
0x18000996e  call    BfeRpcIsKernelModeCaller
0x180009973  test    eax, eax
0x180009975  jnz     loc_180009A4E
0x18000997b  mov     eax, ebx
0x18000997d  movzx   ecx, bx
0x180009980  and     eax, 1FFF0000h
0x180009985  cmp     eax, 70000h
0x18000998a  cmovnz  ecx, ebx; exception
0x18000998d  call    cs:__imp_RpcRaiseException
0x180009993  int     3; Trap to Debugger
0x180009994  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x18000999b  mov     r8, cs:1800EF0B0h
0x1800099a2  mov     rdx, rdi
0x1800099a5  mov     r8d, [r8+840h]
0x1800099ac  call    WfpReportSysErrorAsWinError
0x1800099b1  jmp     loc_1800098B7
0x1800099b6  mov     rax, qword ptr [rbp+57h+TlsValue]
0x1800099ba  test    rax, rax
0x1800099bd  jz      short loc_1800099CC
0x1800099bf  mov     rbx, r13
0x1800099c2  cmp     [rax+24h], r13d
0x1800099c6  jnz     loc_180009782
0x1800099cc  mov     rcx, qword ptr [rbp+57h+TlsValue+8]
0x1800099d0  xor     edx, edx
0x1800099d2  call    BfeTxnCommit
0x1800099d7  mov     rbx, rax
0x1800099da  mov     qword ptr [rbp+57h+TlsValue+8], r13
0x1800099de  test    rax, rax
0x1800099e1  jz      loc_180009782
0x1800099e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099ee  lea     rax, WPP_GLOBAL_Control
0x1800099f5  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x1800099fc  cmp     rcx, rax
0x1800099ff  jz      short loc_180009A27
0x180009a01  cmp     byte ptr [rcx+19h], 2
0x180009a05  jb      short loc_180009A27
0x180009a07  test    byte ptr [rcx+1Ch], 1
0x180009a0b  jz      short loc_180009A27
0x180009a0d  mov     rcx, [rcx+10h]
0x180009a11  mov     edx, 1Ah
0x180009a16  mov     [rsp+0C0h+var_98], ebx
0x180009a1a  xor     r9d, r9d
0x180009a1d  mov     [rsp+0C0h+lpTlsValue], rdi
0x180009a22  call    WPP_SF_Ssd
0x180009a27  cmp     cs:1800EF078h, r13d
0x180009a2e  jz      loc_180009782
0x180009a34  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x180009a3b  jz      loc_180009782
0x180009a41  mov     [rbp+57h+var_50], 10h
0x180009a49  jmp     loc_18000991E
0x180009a4e  mov     rcx, rbx
0x180009a51  call    WfpErrorToNtStatus
0x180009a56  mov     ecx, eax; exception
0x180009a58  call    cs:__imp_RpcRaiseException
0x180009a5e  int     3; Trap to Debugger
0x180009a5f  test    byte ptr [rbx+1Ch], 2
0x180009a63  jz      loc_18000975B
0x180009a69  mov     rbx, [rbx+10h]
0x180009a6d  mov     ecx, 5
0x180009a72  call    BfeObjectTypeIdToString
0x180009a77  mov     r9, rax
0x180009a7a  mov     [rsp+0C0h+lpTlsValue], rsi
0x180009a7f  mov     rcx, rbx
0x180009a82  call    WPP_SF_SI
0x180009a87  jmp     loc_18000975B
```
