# BfeRpcProviderContextAdd

- ea: `0x180009220`
- end: `0x18000959a`
- name: `BfeRpcProviderContextAdd`
- size: `890`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006584`
- `0x180008f60`
- `0x180009220`
- `0x18000a070`
- `0x18000b3d4`
- `0x18000b5b4`
- `0x18000fb34`
- `0x180011510`
- `0x1800197d0`
- `0x180024a5c`
- `0x180026a1c`
- `0x180045700`
- `0x1800592f4`
- `0x18005aa60`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000929d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000929d`

## string_xrefs

- `0x180009505`: `BfeSecurityDescriptorDecode`
- `0x180009444`: `BfeCallCommitEx`
- `0x180009586`: `BfeObjectCopyPublicState`

## pseudocode

```c
__int64 __fastcall BfeRpcProviderContextAdd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v8; // r12
  __int64 v9; // rbx
  __int64 *Value; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 result; // rax
  __int64 v17; // rax
  void *v18; // r8
  void *v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r8
  const char *v22; // rdi
  _QWORD *v23; // rdi
  _QWORD *v24; // [rsp+30h] [rbp-61h] BYREF
  __int64 v25; // [rsp+38h] [rbp-59h] BYREF
  _OWORD TlsValue[2]; // [rsp+40h] [rbp-51h] BYREF
  char v27[16]; // [rsp+60h] [rbp-31h] BYREF
  const char *v28; // [rsp+70h] [rbp-21h]
  __int64 v29; // [rsp+78h] [rbp-19h]
  _QWORD **v30; // [rsp+80h] [rbp-11h]
  __int64 v31; // [rsp+88h] [rbp-9h]

  v25 = 0;
  v24 = 0;
  v8 = 0;
  memset(TlsValue, 0, sizeof(TlsValue));
  if ( a1 )
    v25 = a3;
  v9 = BfeCallCreate(a1, a2, 1, 1, TlsValue);
  if ( v9 )
    goto LABEL_12;
  Value = (__int64 *)TlsGetValue(gBfeContextComponent);
  if ( !Value || (v12 = *Value) == 0 || !*(_DWORD *)(v12 + 88) )
  {
    v9 = BfeFwpmProviderContextValidate(a3);
    if ( v9 )
    {
LABEL_29:
      if ( v25 )
        BfeObjectTraceAddFailure(1, v25);
      goto LABEL_12;
    }
  }
  if ( !a1 )
  {
    v9 = gBfeObjMgr;
    if ( !*(_DWORD *)(gBfeObjMgr + 408) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v11);
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v9 + 440))(a3, &v25);
    LODWORD(v9) = v17;
    if ( v17 )
    {
      WfpReportError(v17, "BfeObjectCopyPublicState");
      goto LABEL_29;
    }
  }
  v18 = 0;
  if ( a4 && *(_DWORD *)a4 )
  {
    v9 = BfeRelativeSecurityDescriptorValidate(*(PSECURITY_DESCRIPTOR *)(a4 + 8), *(_DWORD *)a4);
    if ( v9 )
    {
      v22 = "BfeSecurityDescriptorDecode";
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v21, 0, (__int64)"BfeSecurityDescriptorDecode", v9);
      }
      if ( !gWfpLogUserModeErrors || (byte_1800F6115 & 1) == 0 )
        goto LABEL_29;
      v29 = 28;
      goto LABEL_45;
    }
    v18 = *(void **)(a4 + 8);
  }
  v9 = BfeObjectAdd(1u, &v25, v18, &v24);
  if ( v9 )
    goto LABEL_29;
  if ( *(_QWORD *)&TlsValue[0] && *(_DWORD *)(*(_QWORD *)&TlsValue[0] + 36LL) )
  {
    LODWORD(v9) = 0;
  }
  else
  {
    v9 = BfeTxnCommit(*((_QWORD *)&TlsValue[0] + 1), 0, v20);
    *((_QWORD *)&TlsValue[0] + 1) = 0;
    if ( v9 )
    {
      v19 = WPP_GLOBAL_Control;
      v22 = "BfeCallCommitEx";
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v21, 0, (__int64)"BfeCallCommitEx", v9);
      }
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
      {
        v29 = 16;
LABEL_45:
        v28 = v22;
        v30 = &v24;
        LODWORD(v24) = v9;
        v31 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v21,
          3,
          (__int64)v27);
        goto LABEL_29;
      }
    }
    if ( v9 )
      goto LABEL_29;
  }
  v23 = v24;
  if ( !v24 || !*v24 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v19);
    if ( !v23 || !*v23 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v13);
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD *))(*v23 + 104LL))(v23 + 18);
LABEL_12:
  BfeCallDestroy(TlsValue);
  v15 = gBfeObjMgr;
  if ( !*(_DWORD *)(gBfeObjMgr + 408) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v14);
  (*(void (__fastcall **)(__int64 *))(v15 + 448))(&v25);
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
0x180009220  push    rbp
0x180009222  push    rbx
0x180009223  push    rsi
0x180009224  push    rdi
0x180009225  push    r12
0x180009227  push    r13
0x180009229  push    r14
0x18000922b  push    r15
0x18000922d  lea     rbp, [rsp-17h]
0x180009232  sub     rsp, 0A8h
0x180009239  mov     rax, cs:__security_cookie
0x180009240  xor     rax, rsp
0x180009243  mov     [rbp+4Fh+var_50], rax
0x180009247  mov     r14, [rbp+4Fh+arg_20]
0x18000924b  xor     r13d, r13d
0x18000924e  mov     [rbp+4Fh+var_A8], r13
0x180009252  xorps   xmm0, xmm0
0x180009255  mov     [rbp+4Fh+var_B0], r13
0x180009259  mov     rdi, r9
0x18000925c  mov     rsi, r8
0x18000925f  mov     r15, rcx
0x180009262  mov     r12d, r13d
0x180009265  movups  [rbp+4Fh+TlsValue], xmm0
0x180009269  movups  [rbp+4Fh+var_90], xmm0
0x18000926d  test    rcx, rcx
0x180009270  jz      short loc_180009276
0x180009272  mov     [rbp+4Fh+var_A8], r8
0x180009276  lea     rax, [rbp+4Fh+TlsValue]
0x18000927a  mov     [rsp+0E0h+lpTlsValue], rax; lpTlsValue
0x18000927f  mov     eax, 1
0x180009284  mov     r9d, eax; int
0x180009287  mov     r8d, eax; int
0x18000928a  call    BfeCallCreate
0x18000928f  mov     rbx, rax
0x180009292  test    rax, rax
0x180009295  jnz     short loc_180009306
0x180009297  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x18000929d  call    cs:__imp_TlsGetValue
0x1800092a4  nop     dword ptr [rax+rax+00h]
0x1800092a9  test    rax, rax
0x1800092ac  jz      short loc_1800092BA
0x1800092ae  mov     rax, [rax]
0x1800092b1  test    rax, rax
0x1800092b4  jnz     loc_180009387
0x1800092ba  mov     rcx, rsi
0x1800092bd  call    BfeFwpmProviderContextValidate
0x1800092c2  mov     rbx, rax
0x1800092c5  test    rax, rax
0x1800092c8  jnz     loc_1800093F0
0x1800092ce  jmp     loc_180009391
0x1800092d3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x1800092d8  test    rdi, rdi
0x1800092db  jz      short loc_1800092E2
0x1800092dd  cmp     [rdi], r13
0x1800092e0  jnz     short loc_1800092E7
0x1800092e2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectIsValid(obj)")
0x1800092e7  mov     rax, [rdi]
0x1800092ea  lea     rcx, [rdi+90h]
0x1800092f1  mov     rax, [rax+68h]
0x1800092f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092fa  mov     r12, rax
0x1800092fd  test    rbx, rbx
0x180009300  jnz     loc_1800093F0
0x180009306  lea     rcx, [rbp+4Fh+TlsValue]
0x18000930a  call    BfeCallDestroy
0x18000930f  mov     rdi, cs:gBfeObjMgr
0x180009316  cmp     [rdi+198h], r13d
0x18000931d  jnz     short loc_180009324
0x18000931f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectTypeIdIsValid(typeId)")
0x180009324  mov     rax, [rdi+1C0h]
0x18000932b  lea     rcx, [rbp+4Fh+var_A8]
0x18000932f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009334  test    r15, r15
0x180009337  jnz     short loc_18000937A
0x180009339  mov     ecx, ebx
0x18000933b  movzx   eax, bx
0x18000933e  and     ecx, 1FFF0000h
0x180009344  cmp     ecx, 70000h
0x18000934a  cmovnz  eax, ebx
0x18000934d  test    eax, eax
0x18000934f  jnz     short loc_180009359
0x180009351  test    r14, r14
0x180009354  jz      short loc_180009359
0x180009356  mov     [r14], r12
0x180009359  mov     rcx, [rbp+4Fh+var_50]
0x18000935d  xor     rcx, rsp; StackCookie
0x180009360  call    __security_check_cookie
0x180009365  add     rsp, 0A8h
0x18000936c  pop     r15
0x18000936e  pop     r14
0x180009370  pop     r13
0x180009372  pop     r12
0x180009374  pop     rdi
0x180009375  pop     rsi
0x180009376  pop     rbx
0x180009377  pop     rbp
0x180009378  retn
0x18000937a  mov     rcx, rbx; exception
0x18000937d  call    BfeRpcRaiseExceptionIfError
0x180009382  mov     eax, r13d
0x180009385  jmp     short loc_180009351
0x180009387  cmp     [rax+58h], r13d
0x18000938b  jz      loc_1800092BA
0x180009391  test    r15, r15
0x180009394  jnz     short loc_1800093CA
0x180009396  mov     rbx, cs:gBfeObjMgr
0x18000939d  cmp     [rbx+198h], r13d
0x1800093a4  jnz     short loc_1800093AB
0x1800093a6  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "BfeObjectTypeIdIsValid(typeId)")
0x1800093ab  mov     rax, [rbx+1B8h]
0x1800093b2  lea     rdx, [rbp+4Fh+var_A8]
0x1800093b6  mov     rcx, rsi
0x1800093b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093be  mov     rbx, rax
0x1800093c1  test    rax, rax
0x1800093c4  jnz     loc_180009586
0x1800093ca  mov     r8, r13
0x1800093cd  test    rdi, rdi
0x1800093d0  jnz     loc_18000955E
0x1800093d6  lea     r9, [rbp+4Fh+var_B0]
0x1800093da  mov     ecx, 1
0x1800093df  lea     rdx, [rbp+4Fh+var_A8]
0x1800093e3  call    BfeObjectAdd
0x1800093e8  mov     rbx, rax
0x1800093eb  test    rax, rax
0x1800093ee  jz      short loc_18000940C
0x1800093f0  mov     rdx, [rbp+4Fh+var_A8]
0x1800093f4  test    rdx, rdx
0x1800093f7  jz      loc_180009306
0x1800093fd  mov     ecx, 1
0x180009402  call    BfeObjectTraceAddFailure
0x180009407  jmp     loc_180009306
0x18000940c  mov     rax, qword ptr [rbp+4Fh+TlsValue]
0x180009410  test    rax, rax
0x180009413  jz      short loc_18000941F
0x180009415  cmp     [rax+24h], r13d
0x180009419  jnz     loc_1800094F2
0x18000941f  mov     rcx, qword ptr [rbp+4Fh+TlsValue+8]
0x180009423  xor     edx, edx
0x180009425  call    BfeTxnCommit
0x18000942a  mov     rbx, rax
0x18000942d  mov     qword ptr [rbp+4Fh+TlsValue+8], r13
0x180009431  test    rax, rax
0x180009434  jz      short loc_18000947F
0x180009436  mov     rcx, cs:WPP_GLOBAL_Control
0x18000943d  lea     rax, WPP_GLOBAL_Control
0x180009444  lea     rdi, aBfecallcommite; "BfeCallCommitEx"
0x18000944b  cmp     rcx, rax
0x18000944e  jz      short loc_180009476
0x180009450  cmp     byte ptr [rcx+19h], 2
0x180009454  jb      short loc_180009476
0x180009456  test    byte ptr [rcx+1Ch], 1
0x18000945a  jz      short loc_180009476
0x18000945c  mov     rcx, [rcx+10h]
0x180009460  mov     edx, 1Ah
0x180009465  mov     [rsp+0E0h+var_B8], ebx
0x180009469  xor     r9d, r9d
0x18000946c  mov     [rsp+0E0h+lpTlsValue], rdi
0x180009471  call    WPP_SF_Ssd
0x180009476  cmp     cs:gWfpLogUserModeErrors, r13d
0x18000947d  jnz     short loc_1800094A3
0x18000947f  test    rbx, rbx
0x180009482  jnz     loc_1800093F0
0x180009488  mov     rdi, [rbp+4Fh+var_B0]
0x18000948c  test    rdi, rdi
0x18000948f  jz      loc_1800092D3
0x180009495  cmp     [rdi], r13
0x180009498  jz      loc_1800092D3
0x18000949e  jmp     loc_1800092E7
0x1800094a3  test    cs:byte_1800F6115, 1
0x1800094aa  jz      short loc_18000947F
0x1800094ac  mov     [rbp+4Fh+var_68], 10h
0x1800094b4  lea     rax, [rbp+4Fh+var_B0]
0x1800094b8  mov     [rbp+4Fh+var_70], rdi
0x1800094bc  mov     [rbp+4Fh+var_60], rax
0x1800094c0  lea     rdx, WFP_USERMODE_ERROR
0x1800094c7  lea     rax, [rbp+4Fh+var_80]
0x1800094cb  mov     dword ptr [rbp+4Fh+var_B0], ebx
0x1800094ce  mov     r9d, 3
0x1800094d4  mov     [rsp+0E0h+lpTlsValue], rax
0x1800094d9  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800094e0  mov     [rbp+4Fh+var_58], 4
0x1800094e8  call    McGenEventWrite_EtwEventWriteTransfer
0x1800094ed  jmp     loc_1800093F0
0x1800094f2  mov     rbx, r13
0x1800094f5  jmp     short loc_180009488
0x1800094f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094fe  lea     rax, WPP_GLOBAL_Control
0x180009505  lea     rdi, aBfesecuritydes_0; "BfeSecurityDescriptorDecode"
0x18000950c  cmp     rcx, rax
0x18000950f  jz      short loc_180009537
0x180009511  cmp     byte ptr [rcx+19h], 2
0x180009515  jb      short loc_180009537
0x180009517  test    byte ptr [rcx+1Ch], 1
0x18000951b  jz      short loc_180009537
0x18000951d  mov     rcx, [rcx+10h]
0x180009521  mov     edx, 1Ah
0x180009526  mov     [rsp+0E0h+var_B8], ebx
0x18000952a  xor     r9d, r9d
0x18000952d  mov     [rsp+0E0h+lpTlsValue], rdi
0x180009532  call    WPP_SF_Ssd
0x180009537  cmp     cs:gWfpLogUserModeErrors, r13d
0x18000953e  jz      loc_1800093F0
0x180009544  test    cs:byte_1800F6115, 1
0x18000954b  jz      loc_1800093F0
0x180009551  mov     [rbp+4Fh+var_68], 1Ch
0x180009559  jmp     loc_1800094B4
0x18000955e  mov     edx, [rdi]
0x180009560  test    edx, edx
0x180009562  jz      loc_1800093D6
0x180009568  mov     rcx, [rdi+8]; SecurityDescriptor
0x18000956c  call    BfeRelativeSecurityDescriptorValidate
0x180009571  mov     rbx, rax
0x180009574  test    rax, rax
0x180009577  jnz     loc_1800094F7
0x18000957d  mov     r8, [rdi+8]
0x180009581  jmp     loc_1800093D6
0x180009586  lea     rdx, aBfeobjectcopyp; "BfeObjectCopyPublicState"
0x18000958d  mov     rcx, rax
0x180009590  call    WfpReportError
0x180009595  jmp     loc_1800093F0
```
