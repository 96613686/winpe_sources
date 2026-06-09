# SystemStoreLite::GetSystemSidString(IExecutionContextLite *,ushort * *)

- ea: `0x180025874`
- end: `0x180025a9c`
- name: `?GetSystemSidString@SystemStoreLite@@CAJPEAVIExecutionContextLite@@PEAPEAG@Z`
- size: `552`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800251c4`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x180023b5c`
- `0x180023c04`
- `0x180025874`
- `0x1800267c0`
- `0x180026c8c`
- `0x180032010`

## string_xrefs

- `0x180025a2b`: `pContext != nullptr && ppSidString != nullptr`
- `0x180025997`: `CreateWellKnownSid failed. (win32 = 0x%0x)`
- `0x1800258de`: `SystemStoreLite::GetSystemSidString`
- `0x1800259f9`: `ConvertSidToStringSidW failed. (win32 = 0x%0x)`

## pseudocode

```c
__int64 __fastcall SystemStoreLite::GetSystemSidString(struct IExecutionContextLite *a1, unsigned __int16 **a2)
{
  __int64 v3; // rbx
  int v4; // eax
  __int64 v5; // r9
  int v6; // eax
  unsigned int v7; // ecx
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  unsigned __int16 *v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v13; // r8d
  char *v15; // [rsp+20h] [rbp-89h]
  char *v16; // [rsp+20h] [rbp-89h]
  int v17; // [rsp+30h] [rbp-79h] BYREF
  int v18; // [rsp+34h] [rbp-75h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-71h] BYREF
  __int64 v20; // [rsp+40h] [rbp-69h]
  __int64 v21; // [rsp+48h] [rbp-61h]
  int *v22[4]; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v23[4]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v24[80]; // [rsp+90h] [rbp-19h] BYREF

  v3 = (*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)a1 + 24LL))(a1);
  memset_0(v24, 0, 0x44u);
  v18 = 68;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v17 = 0;
  v23[0] = "SystemStoreLite::GetSystemSidString";
  v23[1] = &v17;
  v23[2] = 0;
  v23[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
    "SystemStoreLite::GetSystemSidString",
    (const char *)0x1DB,
    0,
    (const unsigned __int16 *)v15);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v22, "SystemStoreLite::GetSystemSidString", &v17, 10, &qword_180040120);
  if ( !a2 )
  {
    v17 = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetSystemSidString",
      0x1E0u,
      -2147024809,
      "pContext != nullptr && ppSidString != nullptr");
    goto LABEL_15;
  }
  *a2 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _BYTE *, int *))(*(_QWORD *)v3 + 200LL))(
         v3,
         22,
         0,
         v24,
         &v18);
  v5 = *(_QWORD *)v3;
  if ( v4 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *, unsigned __int16 **))(v5 + 192))(v3, v24, &v19) )
    {
      v10 = v19;
      v19 = 0;
      v20 = 0;
      *a2 = v10;
      goto LABEL_15;
    }
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    else
      v7 = v6;
    v8 = L"ConvertSidToStringSidW failed. (win32 = 0x%0x)";
    v9 = 509;
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(v5 + 120))(v3);
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    else
      v7 = v6;
    v8 = L"CreateWellKnownSid failed. (win32 = 0x%0x)";
    v9 = 496;
  }
  LODWORD(v16) = v6;
  v17 = v7;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp", v9, v8, v16);
LABEL_15:
  v11 = v17;
  ErrorVerifier::CheckAgainstList((PPTraceStatus *)v22[3], *v22[2], (unsigned __int64)v22[1], v22[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v23, v12, v13);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&v19);
  return v11;
}

```

## disassembly

```asm
0x180025874  mov     [rsp-8+arg_10], rbx
0x180025879  push    rbp
0x18002587a  push    rdi
0x18002587b  push    r15
0x18002587d  lea     rbp, [rsp-47h]
0x180025882  sub     rsp, 0F0h
0x180025889  mov     rax, cs:__security_cookie
0x180025890  xor     rax, rsp
0x180025893  mov     [rbp+57h+var_20], rax
0x180025897  mov     rdi, rdx
0x18002589a  mov     rax, [rcx]
0x18002589d  mov     rax, [rax+18h]
0x1800258a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258a6  mov     rbx, rax
0x1800258a9  xor     edx, edx; Val
0x1800258ab  lea     r8d, [rdx+44h]; Size
0x1800258af  lea     rcx, [rbp+57h+var_70]; void *
0x1800258b3  call    memset_0
0x1800258b8  mov     [rbp+57h+var_CC], 44h ; 'D'
0x1800258bf  mov     [rbp+57h+var_C8], 0
0x1800258c7  mov     [rbp+57h+var_B8], 0
0x1800258cf  mov     [rbp+57h+var_C0], 0
0x1800258d7  mov     [rbp+57h+var_D0], 0
0x1800258de  lea     r15, aSystemstorelit_3; "SystemStoreLite::GetSystemSidString"
0x1800258e5  mov     [rbp+57h+var_90], r15
0x1800258e9  lea     rax, [rbp+57h+var_D0]
0x1800258ed  mov     [rbp+57h+var_88], rax
0x1800258f1  mov     [rbp+57h+var_80], 0
0x1800258f9  mov     [rbp+57h+var_78], 0
0x180025901  xor     r9d, r9d; unsigned int
0x180025904  mov     r8d, 1DBh; char *
0x18002590a  mov     rdx, r15; char *
0x18002590d  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180025914  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180025919  nop
0x18002591a  lea     rax, qword_180040120
0x180025921  mov     [rsp+100h+var_E0], rax; int *
0x180025926  mov     r9d, 0Ah; unsigned __int64
0x18002592c  lea     r8, [rbp+57h+var_D0]; int *
0x180025930  mov     rdx, r15; char *
0x180025933  lea     rcx, [rbp+57h+var_B0]; this
0x180025937  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18002593c  nop
0x18002593d  test    rdi, rdi
0x180025940  jz      loc_180025A21
0x180025946  mov     qword ptr [rdi], 0
0x18002594d  mov     rax, [rbx]
0x180025950  lea     rcx, [rbp+57h+var_CC]
0x180025954  mov     [rsp+100h+var_E0], rcx
0x180025959  lea     r9, [rbp+57h+var_70]
0x18002595d  xor     r8d, r8d
0x180025960  lea     edx, [r8+16h]
0x180025964  mov     rcx, rbx
0x180025967  mov     rax, [rax+0C8h]
0x18002596e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025973  mov     r9, [rbx]
0x180025976  mov     rcx, rbx
0x180025979  test    eax, eax
0x18002597b  jnz     short loc_1800259C1
0x18002597d  mov     rax, [r9+78h]
0x180025981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025986  test    eax, eax
0x180025988  jg      short loc_18002598E
0x18002598a  mov     ecx, eax
0x18002598c  jmp     short loc_180025997
0x18002598e  movzx   ecx, ax
0x180025991  or      ecx, 80070000h
0x180025997  lea     r9, aCreatewellknow; "CreateWellKnownSid failed. (win32 = 0x%"...
0x18002599e  mov     r8d, 1F0h; unsigned int
0x1800259a4  mov     dword ptr [rsp+100h+var_E0], eax
0x1800259a8  mov     [rbp+57h+var_D0], ecx
0x1800259ab  lea     rdx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800259b2  mov     ecx, 2; unsigned __int8
0x1800259b7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800259bc  jmp     loc_180025A4C
0x1800259c1  lea     r8, [rbp+57h+var_C8]
0x1800259c5  lea     rdx, [rbp+57h+var_70]
0x1800259c9  mov     rax, [r9+0C0h]
0x1800259d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259d5  test    eax, eax
0x1800259d7  jnz     short loc_180025A08
0x1800259d9  mov     rax, [rbx]
0x1800259dc  mov     rcx, rbx
0x1800259df  mov     rax, [rax+78h]
0x1800259e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259e8  test    eax, eax
0x1800259ea  jg      short loc_1800259F0
0x1800259ec  mov     ecx, eax
0x1800259ee  jmp     short loc_1800259F9
0x1800259f0  movzx   ecx, ax
0x1800259f3  or      ecx, 80070000h
0x1800259f9  lea     r9, aConvertsidtost_1; "ConvertSidToStringSidW failed. (win32 ="...
0x180025a00  mov     r8d, 1FDh
0x180025a06  jmp     short loc_1800259A4
0x180025a08  mov     rax, [rbp+57h+var_C8]
0x180025a0c  mov     [rbp+57h+var_C8], 0
0x180025a14  mov     [rbp+57h+var_C0], 0
0x180025a1c  mov     [rdi], rax
0x180025a1f  jmp     short loc_180025A4C
0x180025a21  mov     r9d, 80070057h; int
0x180025a27  mov     [rbp+57h+var_D0], r9d
0x180025a2b  lea     rax, aPcontextNullpt_0; "pContext != nullptr && ppSidString != n"...
0x180025a32  mov     [rsp+100h+var_E0], rax; char *
0x180025a37  mov     r8d, 1E0h; unsigned int
0x180025a3d  mov     rdx, r15; char *
0x180025a40  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180025a47  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180025a4c  mov     ebx, [rbp+57h+var_D0]
0x180025a4f  mov     r9, [rbp+57h+var_B0]; int *
0x180025a53  mov     r8, [rbp+57h+var_A8]; unsigned __int64
0x180025a57  mov     rdx, [rbp+57h+var_A0]
0x180025a5b  mov     edx, [rdx]; int
0x180025a5d  mov     rcx, [rbp+57h+var_98]; char *
0x180025a61  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180025a66  nop
0x180025a67  lea     rcx, [rbp+57h+var_90]
0x180025a6b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180025a70  nop
0x180025a71  lea     rcx, [rbp+57h+var_C8]
0x180025a75  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180025a7a  mov     eax, ebx
0x180025a7c  mov     rcx, [rbp+57h+var_20]
0x180025a80  xor     rcx, rsp; StackCookie
0x180025a83  call    __security_check_cookie
0x180025a88  mov     rbx, [rsp+100h+arg_10]
0x180025a90  add     rsp, 0F0h
0x180025a97  pop     r15
0x180025a99  pop     rdi
0x180025a9a  pop     rbp
0x180025a9b  retn
```
