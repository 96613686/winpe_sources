# BfeRpcProviderContextAdd

- ea: `0x180008cb0`
- end: `0x180009023`
- name: `BfeRpcProviderContextAdd`
- size: `883`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800060a8`
- `0x180008930`
- `0x180008cb0`
- `0x180009aa0`
- `0x18000ad28`
- `0x18000aef4`
- `0x18000f1a8`
- `0x180010ad0`
- `0x180018b74`
- `0x180022360`
- `0x180024078`
- `0x180043750`
- `0x1800575c4`
- `0x180058b30`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008d2d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008d2d`

## string_xrefs

- `0x180008f8e`: `BfeSecurityDescriptorDecode`
- `0x180008ecd`: `BfeCallCommitEx`
- `0x18000900f`: `BfeObjectCopyPublicState`

## pseudocode

```c
__int64 __fastcall BfeRpcProviderContextAdd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v8; // r12
  __int64 v9; // rbx
  __int64 *Value; // rax
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 result; // rax
  __int64 v14; // rax
  __int64 v15; // r8
  int v16; // r8d
  const char *v17; // rdi
  _QWORD *v18; // rdi
  _QWORD *v19; // [rsp+30h] [rbp-61h] BYREF
  __int64 v20; // [rsp+38h] [rbp-59h] BYREF
  _OWORD TlsValue[2]; // [rsp+40h] [rbp-51h] BYREF
  char v22[16]; // [rsp+60h] [rbp-31h] BYREF
  const char *v23; // [rsp+70h] [rbp-21h]
  __int64 v24; // [rsp+78h] [rbp-19h]
  _QWORD **v25; // [rsp+80h] [rbp-11h]
  __int64 v26; // [rsp+88h] [rbp-9h]

  v20 = 0;
  v19 = 0;
  v8 = 0;
  memset(TlsValue, 0, sizeof(TlsValue));
  if ( a1 )
    v20 = a3;
  v9 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( v9 )
    goto LABEL_12;
  Value = (__int64 *)TlsGetValue(gBfeContextComponent);
  if ( !Value || (v11 = *Value) == 0 || !*(_DWORD *)(v11 + 88) )
  {
    v9 = BfeFwpmProviderContextValidate(a3);
    if ( v9 )
    {
LABEL_29:
      if ( v20 )
        BfeObjectTraceAddFailure(1);
      goto LABEL_12;
    }
  }
  if ( !a1 )
  {
    v9 = gBfeObjMgr;
    if ( !*(_DWORD *)(gBfeObjMgr + 408) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v9 + 440))(a3, &v20);
    LODWORD(v9) = v14;
    if ( v14 )
    {
      WfpReportError(v14, "BfeObjectCopyPublicState");
      goto LABEL_29;
    }
  }
  v15 = 0;
  if ( a4 && *(_DWORD *)a4 )
  {
    v9 = BfeRelativeSecurityDescriptorValidate(*(PSECURITY_DESCRIPTOR *)(a4 + 8));
    if ( v9 )
    {
      v17 = "BfeSecurityDescriptorDecode";
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v16, 0, (__int64)"BfeSecurityDescriptorDecode", v9);
      }
      if ( !gWfpLogUserModeErrors || (byte_1800F30F5 & 1) == 0 )
        goto LABEL_29;
      v24 = 28;
      goto LABEL_45;
    }
    v15 = *(_QWORD *)(a4 + 8);
  }
  v9 = BfeObjectAdd(1, &v20, v15, &v19);
  if ( v9 )
    goto LABEL_29;
  if ( *(_QWORD *)&TlsValue[0] && *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
  {
    LODWORD(v9) = 0;
  }
  else
  {
    v9 = BfeTxnCommit(*((_QWORD *)&TlsValue[0] + 1), 0);
    *((_QWORD *)&TlsValue[0] + 1) = 0;
    if ( v9 )
    {
      v17 = "BfeCallCommitEx";
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v16, 0, (__int64)"BfeCallCommitEx", v9);
      }
      if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
      {
        v24 = 16;
LABEL_45:
        v23 = v17;
        v25 = &v19;
        LODWORD(v19) = v9;
        v26 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
          (unsigned int)WFP_USERMODE_ERROR,
          v16,
          3,
          (__int64)v22);
        goto LABEL_29;
      }
    }
    if ( v9 )
      goto LABEL_29;
  }
  v18 = v19;
  if ( !v19 || !*v19 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !v18 || !*v18 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD *))(*v18 + 104LL))(v18 + 18);
LABEL_12:
  BfeCallDestroy(TlsValue);
  v12 = gBfeObjMgr;
  if ( !*(_DWORD *)(gBfeObjMgr + 408) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  (*(void (__fastcall **)(__int64 *))(v12 + 448))(&v20);
  if ( a1 )
  {
    BfeRpcRaiseExceptionIfError(v9);
    result = 0;
LABEL_18:
    if ( a5 )
      *a5 = v8;
    return result;
  }
  result = (unsigned __int16)v9;
  if ( (v9 & 0x1FFF0000) != 0x70000 )
    result = (unsigned int)v9;
  if ( !(_DWORD)result )
    goto LABEL_18;
  return result;
}

```

## disassembly

```asm
0x180008cb0  push    rbp
0x180008cb2  push    rbx
0x180008cb3  push    rsi
0x180008cb4  push    rdi
0x180008cb5  push    r12
0x180008cb7  push    r13
0x180008cb9  push    r14
0x180008cbb  push    r15
0x180008cbd  lea     rbp, [rsp-17h]
0x180008cc2  sub     rsp, 0A8h
0x180008cc9  mov     rax, cs:__security_cookie
0x180008cd0  xor     rax, rsp
0x180008cd3  mov     [rbp+4Fh+var_50], rax
0x180008cd7  mov     r14, [rbp+4Fh+arg_20]
0x180008cdb  xor     r13d, r13d
0x180008cde  mov     [rbp+4Fh+var_A8], r13
0x180008ce2  xorps   xmm0, xmm0
0x180008ce5  mov     [rbp+4Fh+var_B0], r13
0x180008ce9  mov     rdi, r9
0x180008cec  mov     rsi, r8
0x180008cef  mov     r15, rcx
0x180008cf2  mov     r12d, r13d
0x180008cf5  movups  [rbp+4Fh+TlsValue], xmm0
0x180008cf9  movups  [rbp+4Fh+var_90], xmm0
0x180008cfd  test    rcx, rcx
0x180008d00  jz      short loc_180008D06
0x180008d02  mov     [rbp+4Fh+var_A8], r8
0x180008d06  lea     rax, [rbp+4Fh+TlsValue]
0x180008d0a  mov     [rsp+0E0h+lpTlsValue], rax; lpTlsValue
0x180008d0f  mov     eax, 1
0x180008d14  mov     r9d, eax; int
0x180008d17  mov     r8d, eax; int
0x180008d1a  call    BfeCallCreate
0x180008d1f  mov     rbx, rax
0x180008d22  test    rax, rax
0x180008d25  jnz     short loc_180008D90
0x180008d27  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180008d2d  call    cs:__imp_TlsGetValue
0x180008d33  test    rax, rax
0x180008d36  jz      short loc_180008D44
0x180008d38  mov     rax, [rax]
0x180008d3b  test    rax, rax
0x180008d3e  jnz     loc_180008E10
0x180008d44  mov     rcx, rsi
0x180008d47  call    BfeFwpmProviderContextValidate
0x180008d4c  mov     rbx, rax
0x180008d4f  test    rax, rax
0x180008d52  jnz     loc_180008E79
0x180008d58  jmp     loc_180008E1A
0x180008d5d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008d62  test    rdi, rdi
0x180008d65  jz      short loc_180008D6C
0x180008d67  cmp     [rdi], r13
0x180008d6a  jnz     short loc_180008D71
0x180008d6c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008d71  mov     rax, [rdi]
0x180008d74  lea     rcx, [rdi+90h]
0x180008d7b  mov     rax, [rax+68h]
0x180008d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d84  mov     r12, rax
0x180008d87  test    rbx, rbx
0x180008d8a  jnz     loc_180008E79
0x180008d90  lea     rcx, [rbp+4Fh+TlsValue]
0x180008d94  call    BfeCallDestroy
0x180008d99  mov     rdi, cs:gBfeObjMgr
0x180008da0  cmp     [rdi+198h], r13d
0x180008da7  jnz     short loc_180008DAE
0x180008da9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008dae  mov     rax, [rdi+1C0h]
0x180008db5  lea     rcx, [rbp+4Fh+var_A8]
0x180008db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dbe  test    r15, r15
0x180008dc1  jnz     short loc_180008E03
0x180008dc3  mov     ecx, ebx
0x180008dc5  movzx   eax, bx
0x180008dc8  and     ecx, 1FFF0000h
0x180008dce  cmp     ecx, 70000h
0x180008dd4  cmovnz  eax, ebx
0x180008dd7  test    eax, eax
0x180008dd9  jnz     short loc_180008DE3
0x180008ddb  test    r14, r14
0x180008dde  jz      short loc_180008DE3
0x180008de0  mov     [r14], r12
0x180008de3  mov     rcx, [rbp+4Fh+var_50]
0x180008de7  xor     rcx, rsp; StackCookie
0x180008dea  call    __security_check_cookie
0x180008def  add     rsp, 0A8h
0x180008df6  pop     r15
0x180008df8  pop     r14
0x180008dfa  pop     r13
0x180008dfc  pop     r12
0x180008dfe  pop     rdi
0x180008dff  pop     rsi
0x180008e00  pop     rbx
0x180008e01  pop     rbp
0x180008e02  retn
0x180008e03  mov     rcx, rbx; exception
0x180008e06  call    BfeRpcRaiseExceptionIfError
0x180008e0b  mov     eax, r13d
0x180008e0e  jmp     short loc_180008DDB
0x180008e10  cmp     [rax+58h], r13d
0x180008e14  jz      loc_180008D44
0x180008e1a  test    r15, r15
0x180008e1d  jnz     short loc_180008E53
0x180008e1f  mov     rbx, cs:gBfeObjMgr
0x180008e26  cmp     [rbx+198h], r13d
0x180008e2d  jnz     short loc_180008E34
0x180008e2f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008e34  mov     rax, [rbx+1B8h]
0x180008e3b  lea     rdx, [rbp+4Fh+var_A8]
0x180008e3f  mov     rcx, rsi
0x180008e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e47  mov     rbx, rax
0x180008e4a  test    rax, rax
0x180008e4d  jnz     loc_18000900F
0x180008e53  mov     r8, r13
0x180008e56  test    rdi, rdi
0x180008e59  jnz     loc_180008FE7
0x180008e5f  lea     r9, [rbp+4Fh+var_B0]
0x180008e63  mov     ecx, 1
0x180008e68  lea     rdx, [rbp+4Fh+var_A8]
0x180008e6c  call    BfeObjectAdd
0x180008e71  mov     rbx, rax
0x180008e74  test    rax, rax
0x180008e77  jz      short loc_180008E95
0x180008e79  mov     rdx, [rbp+4Fh+var_A8]
0x180008e7d  test    rdx, rdx
0x180008e80  jz      loc_180008D90
0x180008e86  mov     ecx, 1
0x180008e8b  call    BfeObjectTraceAddFailure
0x180008e90  jmp     loc_180008D90
0x180008e95  mov     rax, qword ptr [rbp+4Fh+TlsValue]
0x180008e99  test    rax, rax
0x180008e9c  jz      short loc_180008EA8
0x180008e9e  cmp     [rax+24h], r13d
0x180008ea2  jnz     loc_180008F7B
0x180008ea8  mov     rcx, qword ptr [rbp+4Fh+TlsValue+8]
0x180008eac  xor     edx, edx
0x180008eae  call    BfeTxnCommit
0x180008eb3  mov     rbx, rax
0x180008eb6  mov     qword ptr [rbp+4Fh+TlsValue+8], r13
0x180008eba  test    rax, rax
0x180008ebd  jz      short loc_180008F08
0x180008ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ec6  lea     rax, WPP_GLOBAL_Control
0x180008ecd  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x180008ed4  cmp     rcx, rax
0x180008ed7  jz      short loc_180008EFF
0x180008ed9  cmp     byte ptr [rcx+19h], 2
0x180008edd  jb      short loc_180008EFF
0x180008edf  test    byte ptr [rcx+1Ch], 1
0x180008ee3  jz      short loc_180008EFF
0x180008ee5  mov     rcx, [rcx+10h]
0x180008ee9  mov     edx, 1Ah
0x180008eee  mov     [rsp+0E0h+var_B8], ebx
0x180008ef2  xor     r9d, r9d
0x180008ef5  mov     [rsp+0E0h+lpTlsValue], rdi
0x180008efa  call    WPP_SF_Ssd
0x180008eff  cmp     cs:gWfpLogUserModeErrors, r13d
0x180008f06  jnz     short loc_180008F2C
0x180008f08  test    rbx, rbx
0x180008f0b  jnz     loc_180008E79
0x180008f11  mov     rdi, [rbp+4Fh+var_B0]
0x180008f15  test    rdi, rdi
0x180008f18  jz      loc_180008D5D
0x180008f1e  cmp     [rdi], r13
0x180008f21  jz      loc_180008D5D
0x180008f27  jmp     loc_180008D71
0x180008f2c  test    cs:byte_1800F30F5, 1
0x180008f33  jz      short loc_180008F08
0x180008f35  mov     [rbp+4Fh+var_68], 10h
0x180008f3d  lea     rax, [rbp+4Fh+var_B0]
0x180008f41  mov     [rbp+4Fh+var_70], rdi
0x180008f45  mov     [rbp+4Fh+var_60], rax
0x180008f49  lea     rdx, WFP_USERMODE_ERROR
0x180008f50  lea     rax, [rbp+4Fh+var_80]
0x180008f54  mov     dword ptr [rbp+4Fh+var_B0], ebx
0x180008f57  mov     r9d, 3
0x180008f5d  mov     [rsp+0E0h+lpTlsValue], rax
0x180008f62  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180008f69  mov     [rbp+4Fh+var_58], 4
0x180008f71  call    McGenEventWrite_EtwEventWriteTransfer
0x180008f76  jmp     loc_180008E79
0x180008f7b  mov     rbx, r13
0x180008f7e  jmp     short loc_180008F11
0x180008f80  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f87  lea     rax, WPP_GLOBAL_Control
0x180008f8e  lea     rdi, aBfesecuritydes_0; "BfeSecurityDescriptorDecode"
0x180008f95  cmp     rcx, rax
0x180008f98  jz      short loc_180008FC0
0x180008f9a  cmp     byte ptr [rcx+19h], 2
0x180008f9e  jb      short loc_180008FC0
0x180008fa0  test    byte ptr [rcx+1Ch], 1
0x180008fa4  jz      short loc_180008FC0
0x180008fa6  mov     rcx, [rcx+10h]
0x180008faa  mov     edx, 1Ah
0x180008faf  mov     [rsp+0E0h+var_B8], ebx
0x180008fb3  xor     r9d, r9d
0x180008fb6  mov     [rsp+0E0h+lpTlsValue], rdi
0x180008fbb  call    WPP_SF_Ssd
0x180008fc0  cmp     cs:gWfpLogUserModeErrors, r13d
0x180008fc7  jz      loc_180008E79
0x180008fcd  test    cs:byte_1800F30F5, 1
0x180008fd4  jz      loc_180008E79
0x180008fda  mov     [rbp+4Fh+var_68], 1Ch
0x180008fe2  jmp     loc_180008F3D
0x180008fe7  mov     edx, [rdi]
0x180008fe9  test    edx, edx
0x180008feb  jz      loc_180008E5F
0x180008ff1  mov     rcx, [rdi+8]; SecurityDescriptor
0x180008ff5  call    BfeRelativeSecurityDescriptorValidate
0x180008ffa  mov     rbx, rax
0x180008ffd  test    rax, rax
0x180009000  jnz     loc_180008F80
0x180009006  mov     r8, [rdi+8]
0x18000900a  jmp     loc_180008E5F
0x18000900f  lea     rdx, aBfeobjectcopyp; "BfeObjectCopyPublicState"
0x180009016  mov     rcx, rax
0x180009019  call    WfpReportError
0x18000901e  jmp     loc_180008E79
```
