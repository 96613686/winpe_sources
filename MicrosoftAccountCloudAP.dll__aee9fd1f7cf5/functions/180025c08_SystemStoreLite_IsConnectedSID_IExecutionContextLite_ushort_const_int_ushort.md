# SystemStoreLite::IsConnectedSID(IExecutionContextLite *,ushort const *,int *,ushort * *)

- ea: `0x180025c08`
- end: `0x180025d8a`
- name: `?IsConnectedSID@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEBGPEAHPEAPEAG@Z`
- size: `386`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, const unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180024cc0`
- `0x180025aa4`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x180023b5c`
- `0x180023c04`
- `0x1800251c4`
- `0x180025c08`
- `0x180026c8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180025d0e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180025d0e`

## string_xrefs

- `0x180025c48`: `SystemStoreLite::IsConnectedSID`
- `0x180025d2b`: `pContext != nullptr && pIsConnected != nullptr && pCurrentUserSidString != nullptr`

## pseudocode

```c
__int64 __fastcall SystemStoreLite::IsConnectedSID(
        struct IExecutionContextLite *a1,
        const unsigned __int16 *a2,
        int *a3,
        unsigned __int16 **a4)
{
  int StoredIdentityProperty; // eax
  __int64 v9; // rdx
  int v10; // r8d
  unsigned __int16 **v12; // [rsp+20h] [rbp-49h]
  wchar_t *Str[3]; // [rsp+30h] [rbp-39h] BYREF
  int *v14[4]; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v15[11]; // [rsp+68h] [rbp-1h] BYREF
  int v16; // [rsp+D0h] [rbp+67h] BYREF

  memset(Str, 0, sizeof(Str));
  v16 = 0;
  v15[0] = "SystemStoreLite::IsConnectedSID";
  v15[1] = &v16;
  v15[2] = 0;
  v15[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
    "SystemStoreLite::IsConnectedSID",
    (const char *)0x44,
    0,
    (const unsigned __int16 *)v12);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v14, "SystemStoreLite::IsConnectedSID", &v16, 1, &dword_1800401A4);
  if ( a1 && a3 && a2 )
  {
    *a3 = 0;
    StoredIdentityProperty = SystemStoreLite::GetStoredIdentityProperty(a1, a2, L"Keywords", Str, a4);
    v16 = StoredIdentityProperty;
    if ( StoredIdentityProperty == -2147023728 )
    {
      v16 = 0;
    }
    else if ( StoredIdentityProperty >= 0 )
    {
      if ( wcsstr(Str[0], L"Connected") )
        *a3 = 1;
    }
    else
    {
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        "SystemStoreLite::IsConnectedSID",
        95,
        StoredIdentityProperty,
        "hr");
    }
  }
  else
  {
    v16 = -2147024809;
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::IsConnectedSID",
      73,
      -2147024809,
      "pContext != nullptr && pIsConnected != nullptr && pCurrentUserSidString != nullptr");
  }
  ErrorVerifier::CheckAgainstList((PPTraceStatus *)v14[3], *v14[2], (unsigned __int64)v14[1], v14[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v15, v9, v10);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)Str);
  return 0;
}

```

## disassembly

```asm
0x180025c08  push    rbp
0x180025c0a  push    rbx
0x180025c0b  push    rsi
0x180025c0c  push    rdi
0x180025c0d  push    r12
0x180025c0f  push    r14
0x180025c11  lea     rbp, [rsp-2Fh]
0x180025c16  sub     rsp, 98h
0x180025c1d  mov     r14, r9
0x180025c20  mov     rbx, r8
0x180025c23  mov     rdi, rdx
0x180025c26  mov     rsi, rcx
0x180025c29  mov     [rbp+57h+Str], 0
0x180025c31  mov     [rbp+57h+var_80], 0
0x180025c39  mov     [rbp+57h+var_88], 0
0x180025c41  mov     [rbp+57h+arg_0], 0
0x180025c48  lea     r12, aSystemstorelit; "SystemStoreLite::IsConnectedSID"
0x180025c4f  mov     [rbp+57h+var_58], r12
0x180025c53  lea     rax, [rbp+57h+arg_0]
0x180025c57  mov     [rbp+57h+var_50], rax
0x180025c5b  mov     [rbp+57h+var_48], 0
0x180025c63  mov     [rbp+57h+var_40], 0
0x180025c6b  xor     r9d, r9d; unsigned int
0x180025c6e  lea     r8d, [r9+44h]; char *
0x180025c72  mov     rdx, r12; char *
0x180025c75  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180025c7c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180025c81  nop
0x180025c82  lea     rax, dword_1800401A4
0x180025c89  mov     [rsp+0C0h+var_A0], rax; int *
0x180025c8e  mov     r9d, 1; unsigned __int64
0x180025c94  lea     r8, [rbp+57h+arg_0]; int *
0x180025c98  mov     rdx, r12; char *
0x180025c9b  lea     rcx, [rbp+57h+var_78]; this
0x180025c9f  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180025ca4  nop
0x180025ca5  test    rsi, rsi
0x180025ca8  jz      short loc_180025D21
0x180025caa  test    rbx, rbx
0x180025cad  jz      short loc_180025D21
0x180025caf  test    rdi, rdi
0x180025cb2  jz      short loc_180025D21
0x180025cb4  mov     dword ptr [rbx], 0
0x180025cba  mov     [rsp+0C0h+var_A0], r14; unsigned __int16 **
0x180025cbf  lea     r9, [rbp+57h+Str]; unsigned __int16 **
0x180025cc3  lea     r8, aKeywords; "Keywords"
0x180025cca  mov     rdx, rdi; unsigned __int16 *
0x180025ccd  mov     rcx, rsi; struct IExecutionContextLite *
0x180025cd0  call    ?GetStoredIdentityProperty@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEBG1PEAPEAG2@Z; SystemStoreLite::GetStoredIdentityProperty(IExecutionContextLite *,ushort const *,ushort const *,ushort * *,ushort * *)
0x180025cd5  mov     [rbp+57h+arg_0], eax
0x180025cd8  cmp     eax, 80070490h
0x180025cdd  jnz     short loc_180025CE8
0x180025cdf  mov     [rbp+57h+arg_0], 0
0x180025ce6  jmp     short loc_180025D4D
0x180025ce8  test    eax, eax
0x180025cea  jns     short loc_180025D03
0x180025cec  lea     r8, aHr; "hr"
0x180025cf3  mov     [rsp+0C0h+var_A0], r8
0x180025cf8  mov     r9d, eax
0x180025cfb  mov     r8d, 5Fh ; '_'
0x180025d01  jmp     short loc_180025D3D
0x180025d03  lea     rdx, aConnected; "Connected"
0x180025d0a  mov     rcx, [rbp+57h+Str]; Str
0x180025d0e  call    cs:__imp_wcsstr
0x180025d14  test    rax, rax
0x180025d17  jz      short loc_180025D4D
0x180025d19  mov     dword ptr [rbx], 1
0x180025d1f  jmp     short loc_180025D4D
0x180025d21  mov     r9d, 80070057h; int
0x180025d27  mov     [rbp+57h+arg_0], r9d
0x180025d2b  lea     rax, aPcontextNullpt_2; "pContext != nullptr && pIsConnected != "...
0x180025d32  mov     [rsp+0C0h+var_A0], rax; char *
0x180025d37  mov     r8d, 49h ; 'I'; unsigned int
0x180025d3d  mov     rdx, r12; char *
0x180025d40  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180025d47  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180025d4c  nop
0x180025d4d  mov     r9, [rbp+57h+var_78]; int *
0x180025d51  mov     r8, [rbp+57h+var_70]; unsigned __int64
0x180025d55  mov     rdx, [rbp+57h+var_68]
0x180025d59  mov     edx, [rdx]; int
0x180025d5b  mov     rcx, [rbp+57h+var_60]; char *
0x180025d5f  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180025d64  nop
0x180025d65  lea     rcx, [rbp+57h+var_58]
0x180025d69  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180025d6e  nop
0x180025d6f  lea     rcx, [rbp+57h+Str]
0x180025d73  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180025d78  xor     eax, eax
0x180025d7a  add     rsp, 98h
0x180025d81  pop     r14
0x180025d83  pop     r12
0x180025d85  pop     rdi
0x180025d86  pop     rsi
0x180025d87  pop     rbx
0x180025d88  pop     rbp
0x180025d89  retn
```
