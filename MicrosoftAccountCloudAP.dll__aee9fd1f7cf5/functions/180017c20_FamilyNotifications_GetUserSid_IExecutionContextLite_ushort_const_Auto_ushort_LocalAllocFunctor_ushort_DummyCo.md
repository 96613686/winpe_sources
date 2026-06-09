# FamilyNotifications::GetUserSid(IExecutionContextLite *,ushort const *,Auto<ushort *,LocalAllocFunctor<ushort *>,DummyContext> &)

- ea: `0x180017c20`
- end: `0x180017d7f`
- name: `?GetUserSid@FamilyNotifications@@CAJPEAVIExecutionContextLite@@PEBGAEAV?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VDummyContext@@@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180017d88`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000def8`
- `0x180017c20`
- `0x180026c8c`
- `0x180027724`
- `0x180032010`

## string_xrefs

- `0x180017c52`: `FamilyNotifications::GetUserSid`
- `0x180017cc1`: `hr = CWLIDCCHelper::GetSID(pExecutionContextLite->GetWinApiFunctions(), pUserName, &spSid)`
- `0x180017d1b`: `hr = pSystemStoreLiteFunctions->GetCurrentUserSidString(&spSid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FamilyNotifications::GetUserSid(__int64 a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v6; // rbx
  struct IWinApiLite *v7; // rax
  int SID; // eax
  __int64 v9; // rdx
  int v10; // r8d
  int v11; // eax
  unsigned int v12; // ebx
  char *v14; // [rsp+20h] [rbp-30h]
  _QWORD v15[4]; // [rsp+30h] [rbp-20h] BYREF
  int v16; // [rsp+80h] [rbp+30h] BYREF
  int v17; // [rsp+88h] [rbp+38h] BYREF

  v16 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
  v15[0] = "FamilyNotifications::GetUserSid";
  v15[1] = &v16;
  v15[2] = 0;
  v15[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\familynotifications\\familynotifications.cpp",
    "FamilyNotifications::GetUserSid",
    (const char *)0x69,
    0,
    (const unsigned __int16 *)v14);
  Auto<unsigned char *,LocalAllocFunctor<unsigned char *>,DummyContext>::Clear((__int64)a3);
  if ( a2 )
  {
    v7 = (struct IWinApiLite *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    SID = CWLIDCCHelper::GetSID(v7, a2, a3);
    v16 = SID;
    if ( SID < 0 )
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\familynotifications\\familynotifications.cpp",
        "FamilyNotifications::GetUserSid",
        0x70u,
        SID,
        "hr = CWLIDCCHelper::GetSID(pExecutionContextLite->GetWinApiFunctions(), pUserName, &spSid)");
  }
  else
  {
    v17 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v6 + 8LL))(v6, &v17, 0);
    if ( v16 >= 0 && v17 == 1 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v6 + 32LL))(v6, a3);
      v16 = v11;
      if ( v11 < 0 )
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\familynotifications\\familynotifications.cpp",
          "FamilyNotifications::GetUserSid",
          0x7Au,
          v11,
          "hr = pSystemStoreLiteFunctions->GetCurrentUserSidString(&spSid)");
    }
    else
    {
      v16 = -2147023728;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\familynotifications\\familynotifications.cpp",
        "FamilyNotifications::GetUserSid",
        0x7Eu,
        -2147023728,
        "hr = HRESULT_FROM_WIN32(ERROR_NOT_FOUND)");
    }
  }
  v12 = v16;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v15, v9, v10);
  return v12;
}

```

## disassembly

```asm
0x180017c20  mov     [rsp-28h+arg_10], rbx
0x180017c25  push    rbp
0x180017c26  push    rsi
0x180017c27  push    rdi
0x180017c28  push    r12
0x180017c2a  push    r14
0x180017c2c  mov     rbp, rsp
0x180017c2f  sub     rsp, 50h
0x180017c33  mov     rsi, r8
0x180017c36  mov     r14, rdx
0x180017c39  mov     rdi, rcx
0x180017c3c  mov     [rbp+arg_0], 0
0x180017c43  mov     rax, [rcx]
0x180017c46  mov     rax, [rax+30h]
0x180017c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c4f  mov     rbx, rax
0x180017c52  lea     r12, aFamilynotifica_2; "FamilyNotifications::GetUserSid"
0x180017c59  mov     [rbp+var_20], r12
0x180017c5d  lea     rax, [rbp+arg_0]
0x180017c61  mov     [rbp+var_18], rax
0x180017c65  mov     [rbp+var_10], 0
0x180017c6d  mov     [rbp+var_8], 0
0x180017c75  xor     r9d, r9d; unsigned int
0x180017c78  lea     r8d, [r9+69h]; char *
0x180017c7c  mov     rdx, r12; char *
0x180017c7f  lea     rcx, aOnecoreuapDsEx_13; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180017c86  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180017c8b  nop
0x180017c8c  mov     rcx, rsi
0x180017c8f  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x180017c94  test    r14, r14
0x180017c97  jz      short loc_180017CD8
0x180017c99  mov     rax, [rdi]
0x180017c9c  mov     rcx, rdi
0x180017c9f  mov     rax, [rax+18h]
0x180017ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ca8  mov     r8, rsi; unsigned __int16 **
0x180017cab  mov     rdx, r14; unsigned __int16 *
0x180017cae  mov     rcx, rax; struct IWinApiLite *
0x180017cb1  call    ?GetSID@CWLIDCCHelper@@SAJPEAVIWinApiLite@@PEBGPEAPEAG@Z; CWLIDCCHelper::GetSID(IWinApiLite *,ushort const *,ushort * *)
0x180017cb6  mov     [rbp+arg_0], eax
0x180017cb9  test    eax, eax
0x180017cbb  jns     loc_180017D5D
0x180017cc1  lea     r8, aHrCwlidcchelpe; "hr = CWLIDCCHelper::GetSID(pExecutionCo"...
0x180017cc8  mov     [rsp+50h+var_30], r8
0x180017ccd  mov     r9d, eax
0x180017cd0  mov     r8d, 70h ; 'p'
0x180017cd6  jmp     short loc_180017D4E
0x180017cd8  mov     [rbp+arg_8], 0
0x180017cdf  mov     rax, [rbx]
0x180017ce2  xor     r8d, r8d
0x180017ce5  lea     rdx, [rbp+arg_8]
0x180017ce9  mov     rcx, rbx
0x180017cec  mov     rax, [rax+8]
0x180017cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cf5  mov     [rbp+arg_0], eax
0x180017cf8  test    eax, eax
0x180017cfa  js      short loc_180017D32
0x180017cfc  cmp     [rbp+arg_8], 1
0x180017d00  jnz     short loc_180017D32
0x180017d02  mov     rax, [rbx]
0x180017d05  mov     rdx, rsi
0x180017d08  mov     rcx, rbx
0x180017d0b  mov     rax, [rax+20h]
0x180017d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d14  mov     [rbp+arg_0], eax
0x180017d17  test    eax, eax
0x180017d19  jns     short loc_180017D5D
0x180017d1b  lea     rcx, aHrPsystemstore; "hr = pSystemStoreLiteFunctions->GetCurr"...
0x180017d22  mov     [rsp+50h+var_30], rcx
0x180017d27  mov     r9d, eax
0x180017d2a  mov     r8d, 7Ah ; 'z'
0x180017d30  jmp     short loc_180017D4E
0x180017d32  mov     r9d, 80070490h; int
0x180017d38  mov     [rbp+arg_0], r9d
0x180017d3c  lea     rax, aHrHresultFromW_0; "hr = HRESULT_FROM_WIN32(ERROR_NOT_FOUND"...
0x180017d43  mov     [rsp+50h+var_30], rax; char *
0x180017d48  mov     r8d, 7Eh ; '~'; unsigned int
0x180017d4e  mov     rdx, r12; char *
0x180017d51  lea     rcx, aOnecoreuapDsEx_13; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180017d58  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180017d5d  mov     ebx, [rbp+arg_0]
0x180017d60  lea     rcx, [rbp+var_20]
0x180017d64  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180017d69  mov     eax, ebx
0x180017d6b  mov     rbx, [rsp+50h+arg_10]
0x180017d73  add     rsp, 50h
0x180017d77  pop     r14
0x180017d79  pop     r12
0x180017d7b  pop     rdi
0x180017d7c  pop     rsi
0x180017d7d  pop     rbp
0x180017d7e  retn
```
