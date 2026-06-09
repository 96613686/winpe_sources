# BfeRpcFilterDeleteById

- ea: `0x180009cb0`
- end: `0x18000a061`
- name: `BfeRpcFilterDeleteById`
- size: `945`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800051f4`
- `0x180008f60`
- `0x180009cb0`
- `0x18000a070`
- `0x18000b3d4`
- `0x18000c188`
- `0x18000fb34`
- `0x180011510`
- `0x180012d8c`
- `0x180024ab0`
- `0x18002681c`
- `0x18004b62c`
- `0x1800592f4`
- `0x18005aa60`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x180009df2`
- `ntdll!RtlLookupEntryHashTable` at `0x180009df2`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009f26`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009f26`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009dcd`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009dcd`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009e56`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009e56`
- `RPCRT4!RpcRaiseException` at `0x180009f56`
- `RPCRT4!RpcRaiseException` at `0x18000a027`
- `RPCRT4!RpcRaiseException` at `0x180009f56`
- `RPCRT4!RpcRaiseException` at `0x18000a027`

## string_xrefs

- `0x180009dac`: `BfeObjectDeleteById`
- `0x180009e73`: `BfeObjectDeleteById`
- `0x180009f63`: `BfeObjectDeleteById`
- `0x180009fc4`: `BfeCallCommitEx`

## pseudocode

```c
__int64 __fastcall BfeRpcFilterDeleteById(__int64 a1, int a2, __int64 a3)
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
  __int64 v16; // rcx
  _BYTE *v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r8
  RPC_STATUS v21; // ecx
  RPC_STATUS v22; // eax
  __int64 v23; // rbx
  int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // [rsp+30h] [rbp-39h] BYREF
  _OWORD TlsValue[2]; // [rsp+38h] [rbp-31h] BYREF
  __int128 v29; // [rsp+58h] [rbp-11h] BYREF
  const char *v30; // [rsp+68h] [rbp-1h]
  __int64 v31; // [rsp+70h] [rbp+7h]
  int *v32; // [rsp+78h] [rbp+Fh]
  __int64 v33; // [rsp+80h] [rbp+17h]

  memset(TlsValue, 0, sizeof(TlsValue));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v23 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v24 = BfeObjectTypeIdToString(5);
    WPP_SF_SI(v23, v25, v26, v24, a3);
  }
  v7 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( !v7 )
  {
    v9 = gBfeObjMgr;
    v30 = 0;
    v29 = 0;
    if ( !*(_DWORD *)(gBfeObjMgr + 2040) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6);
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
      for ( i = RtlLookupEntryHashTable(v9 + 2328, v13, &v29); i; i = RtlGetNextEntryHashTable(v14, &v29) )
      {
        v17 = (_BYTE *)(i - 40);
        if ( i == 40 || !*(_QWORD *)v17 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v16);
        if ( (v17[8] & 8) == 0 )
        {
          if ( !*(_QWORD *)v17 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v16);
            if ( !*(_QWORD *)v17 )
              MicrosoftTelemetryAssertTriggeredNoArgs(v18);
          }
          if ( (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v17 + 104LL))(v17 + 144) == a3 )
          {
            v12 = v17;
            break;
          }
        }
      }
      RtlReleaseSRWLockShared(v11);
      if ( v12 )
      {
        v19 = BfeObjectDelete(v12);
        v10 = "BfeObjectDeleteById";
        goto LABEL_28;
      }
      v10 = "BfeObjectDeleteById";
    }
    v19 = WfpReportSysErrorAsWinError(v6, "BfeObjectDeleteById", *(unsigned int *)(gBfeObjMgr + 2112));
LABEL_28:
    v7 = v19;
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v20, 0, (__int64)"BfeObjectDeleteById", v19);
      }
      if ( !gWfpLogUserModeErrors || (byte_1800F6115 & 1) == 0 )
        goto LABEL_4;
      v31 = 20;
    }
    else
    {
      if ( *(_QWORD *)&TlsValue[0] )
      {
        v7 = 0;
        if ( *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
          goto LABEL_4;
      }
      v7 = BfeTxnCommit(*((_QWORD *)&TlsValue[0] + 1), 0, v20);
      *((_QWORD *)&TlsValue[0] + 1) = 0;
      if ( !v7 )
        goto LABEL_4;
      v10 = "BfeCallCommitEx";
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v20, 0, (__int64)"BfeCallCommitEx", v7);
      }
      if ( !gWfpLogUserModeErrors || (byte_1800F6115 & 1) == 0 )
        goto LABEL_4;
      v31 = 16;
    }
    v27 = v7;
    v32 = &v27;
    v30 = v10;
    v33 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      &MICROSOFT_WFP_PROVIDER_Context,
      (__int64)WFP_USERMODE_ERROR,
      v20,
      3,
      (__int64)&v29);
  }
LABEL_4:
  BfeCallDestroy(TlsValue);
  if ( a1 )
  {
    if ( v7 )
    {
      if ( !(unsigned int)BfeRpcIsKernelModeCaller() )
      {
        v21 = (unsigned __int16)v7;
        if ( (v7 & 0x1FFF0000) != 0x70000 )
          v21 = v7;
        RpcRaiseException(v21);
      }
      v22 = WfpErrorToNtStatus(v7);
      RpcRaiseException(v22);
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
0x180009cb0  mov     [rsp-8+arg_18], rbx
0x180009cb5  push    rbp
0x180009cb6  push    rsi
0x180009cb7  push    rdi
0x180009cb8  push    r12
0x180009cba  push    r13
0x180009cbc  push    r14
0x180009cbe  push    r15
0x180009cc0  lea     rbp, [rsp-27h]
0x180009cc5  sub     rsp, 90h
0x180009ccc  mov     rax, cs:__security_cookie
0x180009cd3  xor     rax, rsp
0x180009cd6  mov     [rbp+57h+var_38], rax
0x180009cda  xorps   xmm0, xmm0
0x180009cdd  mov     rsi, r8
0x180009ce0  movups  [rbp+57h+TlsValue], xmm0
0x180009ce4  mov     rdi, rdx
0x180009ce7  mov     r12, rcx
0x180009cea  movups  [rbp+57h+var_78], xmm0
0x180009cee  mov     rbx, cs:WPP_GLOBAL_Control
0x180009cf5  lea     rax, WPP_GLOBAL_Control
0x180009cfc  cmp     rbx, rax
0x180009cff  jz      short loc_180009D0B
0x180009d01  cmp     byte ptr [rbx+19h], 4
0x180009d05  jnb     loc_18000A034
0x180009d0b  lea     rax, [rbp+57h+TlsValue]
0x180009d0f  mov     rdx, rdi; int
0x180009d12  mov     [rsp+0C0h+lpTlsValue], rax; lpTlsValue
0x180009d17  mov     eax, 1
0x180009d1c  mov     r9d, eax; int
0x180009d1f  mov     r8d, eax; int
0x180009d22  call    BfeCallCreate
0x180009d27  xor     r13d, r13d
0x180009d2a  mov     rbx, rax
0x180009d2d  test    rax, rax
0x180009d30  jz      short loc_180009D8A
0x180009d32  lea     rcx, [rbp+57h+TlsValue]
0x180009d36  call    BfeCallDestroy
0x180009d3b  test    r12, r12
0x180009d3e  jz      short loc_180009D4E
0x180009d40  test    rbx, rbx
0x180009d43  jnz     loc_180009F37
0x180009d49  mov     eax, r13d
0x180009d4c  jmp     short loc_180009D62
0x180009d4e  mov     ecx, ebx
0x180009d50  movzx   eax, bx
0x180009d53  and     ecx, 1FFF0000h
0x180009d59  cmp     ecx, 70000h
0x180009d5f  cmovnz  eax, ebx
0x180009d62  mov     rcx, [rbp+57h+var_38]
0x180009d66  xor     rcx, rsp; StackCookie
0x180009d69  call    __security_check_cookie
0x180009d6e  mov     rbx, [rsp+0C0h+arg_18]
0x180009d76  add     rsp, 90h
0x180009d7d  pop     r15
0x180009d7f  pop     r14
0x180009d81  pop     r13
0x180009d83  pop     r12
0x180009d85  pop     rdi
0x180009d86  pop     rsi
0x180009d87  pop     rbp
0x180009d88  retn
0x180009d8a  mov     rbx, cs:gBfeObjMgr
0x180009d91  xor     eax, eax
0x180009d93  xorps   xmm0, xmm0
0x180009d96  mov     [rbp+57h+var_58], rax
0x180009d9a  movups  [rbp+57h+var_68], xmm0
0x180009d9e  cmp     [rbx+7F8h], r13d
0x180009da5  jnz     short loc_180009DAC
0x180009da7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectTypeIdIsValid(typeId)")
0x180009dac  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x180009db3  cmp     [rbx+948h], r13d
0x180009dba  jz      loc_180009F6A
0x180009dc0  lea     r14, [rbx+940h]
0x180009dc7  mov     rdi, r13
0x180009dca  mov     rcx, r14
0x180009dcd  call    cs:__imp_RtlAcquireSRWLockShared
0x180009dd4  nop     dword ptr [rax+rax+00h]
0x180009dd9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009ddd  lea     r15, [rbx+918h]
0x180009de4  test    rsi, rsi
0x180009de7  lea     r8, [rbp+57h+var_68]
0x180009deb  mov     rcx, r15
0x180009dee  cmovnz  rdx, rsi
0x180009df2  call    cs:__imp_RtlLookupEntryHashTable
0x180009df9  nop     dword ptr [rax+rax+00h]
0x180009dfe  test    rax, rax
0x180009e01  jz      short loc_180009E53
0x180009e03  lea     rbx, [rax-28h]
0x180009e07  test    rbx, rbx
0x180009e0a  jz      short loc_180009E11
0x180009e0c  cmp     [rbx], r13
0x180009e0f  jnz     short loc_180009E16
0x180009e11  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x180009e16  test    byte ptr [rbx+8], 8
0x180009e1a  jnz     loc_180009F1F
0x180009e20  cmp     [rbx], r13
0x180009e23  jnz     short loc_180009E34
0x180009e25  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x180009e2a  cmp     [rbx], r13
0x180009e2d  jnz     short loc_180009E34
0x180009e2f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x180009e34  mov     rax, [rbx]
0x180009e37  lea     rcx, [rbx+90h]
0x180009e3e  mov     rax, [rax+68h]
0x180009e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e47  cmp     rax, rsi
0x180009e4a  jnz     loc_180009F1F
0x180009e50  mov     rdi, rbx
0x180009e53  mov     rcx, r14
0x180009e56  call    cs:__imp_RtlReleaseSRWLockShared
0x180009e5d  nop     dword ptr [rax+rax+00h]
0x180009e62  test    rdi, rdi
0x180009e65  jz      loc_180009F63
0x180009e6b  mov     rcx, rdi
0x180009e6e  call    BfeObjectDelete
0x180009e73  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x180009e7a  mov     rbx, rax
0x180009e7d  test    rax, rax
0x180009e80  jz      loc_180009F85
0x180009e86  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e8d  lea     rax, WPP_GLOBAL_Control
0x180009e94  cmp     rcx, rax
0x180009e97  jz      short loc_180009EBF
0x180009e99  cmp     byte ptr [rcx+19h], 2
0x180009e9d  jb      short loc_180009EBF
0x180009e9f  test    byte ptr [rcx+1Ch], 1
0x180009ea3  jz      short loc_180009EBF
0x180009ea5  mov     rcx, [rcx+10h]
0x180009ea9  mov     edx, 1Ah
0x180009eae  mov     [rsp+0C0h+var_98], ebx
0x180009eb2  xor     r9d, r9d
0x180009eb5  mov     [rsp+0C0h+lpTlsValue], rdi
0x180009eba  call    WPP_SF_Ssd
0x180009ebf  cmp     cs:gWfpLogUserModeErrors, r13d
0x180009ec6  jz      loc_180009D32
0x180009ecc  test    cs:byte_1800F6115, 1
0x180009ed3  jz      loc_180009D32
0x180009ed9  mov     [rbp+57h+var_50], 14h
0x180009ee1  lea     rax, [rbp+57h+var_90]
0x180009ee5  mov     [rbp+57h+var_90], ebx
0x180009ee8  mov     [rbp+57h+var_48], rax
0x180009eec  lea     rdx, WFP_USERMODE_ERROR
0x180009ef3  lea     rax, [rbp+57h+var_68]
0x180009ef7  mov     [rbp+57h+var_58], rdi
0x180009efb  mov     r9d, 3
0x180009f01  mov     [rsp+0C0h+lpTlsValue], rax
0x180009f06  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180009f0d  mov     [rbp+57h+var_40], 4
0x180009f15  call    McGenEventWrite_EtwEventWriteTransfer
0x180009f1a  jmp     loc_180009D32
0x180009f1f  lea     rdx, [rbp+57h+var_68]
0x180009f23  mov     rcx, r15
0x180009f26  call    cs:__imp_RtlGetNextEntryHashTable
0x180009f2d  nop     dword ptr [rax+rax+00h]
0x180009f32  jmp     loc_180009DFE
0x180009f37  call    BfeRpcIsKernelModeCaller
0x180009f3c  test    eax, eax
0x180009f3e  jnz     loc_18000A01D
0x180009f44  mov     eax, ebx
0x180009f46  movzx   ecx, bx
0x180009f49  and     eax, 1FFF0000h
0x180009f4e  cmp     eax, 70000h
0x180009f53  cmovnz  ecx, ebx; exception
0x180009f56  call    cs:__imp_RpcRaiseException
0x180009f5d  nop     dword ptr [rax+rax+00h]
0x180009f62  int     3; Trap to Debugger
0x180009f63  lea     rdi, aBfeobjectdelet_0; "BfeObjectDeleteById"
0x180009f6a  mov     r8, cs:gBfeObjMgr
0x180009f71  mov     rdx, rdi
0x180009f74  mov     r8d, [r8+840h]
0x180009f7b  call    WfpReportSysErrorAsWinError
0x180009f80  jmp     loc_180009E7A
0x180009f85  mov     rax, qword ptr [rbp+57h+TlsValue]
0x180009f89  test    rax, rax
0x180009f8c  jz      short loc_180009F9B
0x180009f8e  mov     rbx, r13
0x180009f91  cmp     [rax+24h], r13d
0x180009f95  jnz     loc_180009D32
0x180009f9b  mov     rcx, qword ptr [rbp+57h+TlsValue+8]
0x180009f9f  xor     edx, edx
0x180009fa1  call    BfeTxnCommit
0x180009fa6  mov     rbx, rax
0x180009fa9  mov     qword ptr [rbp+57h+TlsValue+8], r13
0x180009fad  test    rax, rax
0x180009fb0  jz      loc_180009D32
0x180009fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fbd  lea     rax, WPP_GLOBAL_Control
0x180009fc4  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x180009fcb  cmp     rcx, rax
0x180009fce  jz      short loc_180009FF6
0x180009fd0  cmp     byte ptr [rcx+19h], 2
0x180009fd4  jb      short loc_180009FF6
0x180009fd6  test    byte ptr [rcx+1Ch], 1
0x180009fda  jz      short loc_180009FF6
0x180009fdc  mov     rcx, [rcx+10h]
0x180009fe0  mov     edx, 1Ah
0x180009fe5  mov     [rsp+0C0h+var_98], ebx
0x180009fe9  xor     r9d, r9d
0x180009fec  mov     [rsp+0C0h+lpTlsValue], rdi
0x180009ff1  call    WPP_SF_Ssd
0x180009ff6  cmp     cs:gWfpLogUserModeErrors, r13d
0x180009ffd  jz      loc_180009D32
0x18000a003  test    cs:byte_1800F6115, 1
0x18000a00a  jz      loc_180009D32
0x18000a010  mov     [rbp+57h+var_50], 10h
0x18000a018  jmp     loc_180009EE1
0x18000a01d  mov     rcx, rbx
0x18000a020  call    WfpErrorToNtStatus
0x18000a025  mov     ecx, eax; exception
0x18000a027  call    cs:__imp_RpcRaiseException
0x18000a02e  nop     dword ptr [rax+rax+00h]
0x18000a033  int     3; Trap to Debugger
0x18000a034  test    byte ptr [rbx+1Ch], 2
0x18000a038  jz      loc_180009D0B
0x18000a03e  mov     rbx, [rbx+10h]
0x18000a042  mov     ecx, 5
0x18000a047  call    BfeObjectTypeIdToString
0x18000a04c  mov     r9, rax
0x18000a04f  mov     [rsp+0C0h+lpTlsValue], rsi
0x18000a054  mov     rcx, rbx
0x18000a057  call    WPP_SF_SI
0x18000a05c  jmp     loc_180009D0B
```
