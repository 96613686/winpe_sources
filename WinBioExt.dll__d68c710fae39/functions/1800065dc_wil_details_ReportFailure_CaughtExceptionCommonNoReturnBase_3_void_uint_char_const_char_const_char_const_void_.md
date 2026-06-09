# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x1800065dc`
- end: `0x1800066ca`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800065ac`

## callees

- `0x180002430`
- `0x1800042a0`
- `0x1800065dc`
- `0x18000b010`

## string_xrefs

- `0x180006661`: `onecore\ds\security\biometrics\credprov\common\threads.cpp`
- `0x180006695`: `onecore\ds\security\biometrics\credprov\common\threads.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rcx
  int v10; // r9d
  int v11; // r9d
  _BYTE v12[24]; // [rsp+60h] [rbp-18h] BYREF
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  LOBYTE(v13) = 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a8 + 2 * v8) );
  if ( g_pfnResultFromCaughtExceptionInternal )
  {
    if ( _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                           v12,
                                                           a8 + 2 * v8,
                                                           2048 - v8,
                                                           &v13)) < 0 )
      wil::details::ReportFailure_Base<3,0>(
        a2,
        457,
        (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\common\\threads.cpp",
        v10);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(
    a2,
    457,
    (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\common\\threads.cpp",
    v11);
}

```

## disassembly

```asm
0x1800065dc  mov     rax, rsp
0x1800065df  mov     [rax+8], rbx
0x1800065e3  mov     [rax+10h], rsi
0x1800065e7  mov     [rax+18h], r8d
0x1800065eb  push    rdi
0x1800065ec  sub     rsp, 70h
0x1800065f0  mov     rbx, [rsp+78h+arg_38]
0x1800065f8  xor     esi, esi
0x1800065fa  mov     [rax+18h], sil
0x1800065fe  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006602  mov     rdi, rdx
0x180006605  inc     rcx
0x180006608  cmp     [rbx+rcx*2], si
0x18000660c  jnz     short loc_180006605
0x18000660e  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180006615  test    rax, rax
0x180006618  jz      short loc_180006683
0x18000661a  lea     rdx, [rbx+rcx*2]
0x18000661e  mov     r8d, 800h
0x180006624  sub     r8, rcx
0x180006627  lea     r9, [rsp+78h+arg_10]
0x18000662f  lea     rcx, [rsp+78h+var_18]
0x180006634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006639  movsd   xmm0, qword ptr [rax]
0x18000663d  mov     eax, [rax+8]
0x180006640  mov     [rsp+78h+var_20], eax
0x180006644  movd    eax, xmm0
0x180006648  movsd   [rsp+78h+var_28], xmm0
0x18000664e  test    eax, eax
0x180006650  jns     short loc_180006683
0x180006652  lea     rax, [rsp+78h+var_28]
0x180006657  mov     [rsp+78h+var_40], rbx
0x18000665c  mov     [rsp+78h+var_48], rax
0x180006661  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\biometrics\\cred"...
0x180006668  mov     rax, [rsp+78h+arg_30]
0x180006670  mov     edx, 1C9h
0x180006675  mov     rcx, rdi
0x180006678  mov     [rsp+78h+var_50], rax
0x18000667d  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180006683  mov     ecx, 8007023Eh; this
0x180006688  mov     dword ptr [rsp+78h+var_28], ecx
0x18000668c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006691  mov     dword ptr [rsp+78h+var_28+4], eax
0x180006695  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\biometrics\\cred"...
0x18000669c  lea     rax, [rsp+78h+var_28]
0x1800066a1  mov     [rsp+78h+var_40], rbx
0x1800066a6  mov     [rsp+78h+var_48], rax
0x1800066ab  mov     edx, 1C9h
0x1800066b0  mov     rax, [rsp+78h+arg_30]
0x1800066b8  mov     rcx, rdi
0x1800066bb  mov     [rsp+78h+var_50], rax
0x1800066c0  mov     [rsp+78h+var_20], esi
0x1800066c4  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
