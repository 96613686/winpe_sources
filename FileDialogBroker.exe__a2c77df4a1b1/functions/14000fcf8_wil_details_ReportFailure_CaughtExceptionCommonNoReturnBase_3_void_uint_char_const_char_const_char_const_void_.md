# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x14000fcf8`
- end: `0x14000fde6`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: `void __fastcall __noreturn(__int64, int, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000fcc8`

## callees

- `0x140002af4`
- `0x1400044bc`
- `0x14000fcf8`
- `0x140014010`

## string_xrefs

- `0x14000fd7d`: `onecoreuap\ds\security\isolation\broker\lib\shellobjectbroker.cpp`
- `0x14000fdb1`: `onecoreuap\ds\security\isolation\broker\lib\shellobjectbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rbx
  __int64 v9; // rcx
  unsigned __int64 *v11; // rax
  int v12; // r9d
  __m128i v13; // xmm0
  int v14; // r9d
  int v15; // [rsp+20h] [rbp-58h]
  __int64 v16; // [rsp+50h] [rbp-28h] BYREF
  int v17; // [rsp+58h] [rbp-20h]
  _BYTE v18[24]; // [rsp+60h] [rbp-18h] BYREF
  int v19; // [rsp+90h] [rbp+18h] BYREF

  v19 = a3;
  v8 = a8;
  LOBYTE(v19) = 0;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(a8 + 2 * v9) );
  if ( g_pfnResultFromCaughtExceptionInternal )
  {
    v11 = (unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(v18, a8 + 2 * v9, 2048 - v9, &v19);
    v13 = (__m128i)*v11;
    v17 = *((_DWORD *)v11 + 2);
    v16 = v13.m128i_i64[0];
    if ( _mm_cvtsi128_si32(v13) < 0 )
      wil::details::ReportFailure_Base<3,0>(
        a2,
        34,
        (int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\shellobjectbroker.cpp",
        v12,
        v15,
        a7,
        (__int64)&v16,
        v8);
  }
  LODWORD(v16) = -2147024322;
  HIDWORD(v16) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  v17 = 0;
  wil::details::ReportFailure_Base<3,0>(
    a2,
    34,
    (int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\shellobjectbroker.cpp",
    v14,
    v15,
    a7,
    (__int64)&v16,
    v8);
}

```

## disassembly

```asm
0x14000fcf8  mov     rax, rsp
0x14000fcfb  mov     [rax+8], rbx
0x14000fcff  mov     [rax+10h], rsi
0x14000fd03  mov     [rax+18h], r8d
0x14000fd07  push    rdi
0x14000fd08  sub     rsp, 70h
0x14000fd0c  mov     rbx, [rsp+78h+arg_38]
0x14000fd14  xor     esi, esi
0x14000fd16  mov     [rax+18h], sil
0x14000fd1a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000fd1e  mov     rdi, rdx
0x14000fd21  inc     rcx
0x14000fd24  cmp     [rbx+rcx*2], si
0x14000fd28  jnz     short loc_14000FD21
0x14000fd2a  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x14000fd31  test    rax, rax
0x14000fd34  jz      short loc_14000FD9F
0x14000fd36  lea     rdx, [rbx+rcx*2]
0x14000fd3a  mov     r8d, 800h
0x14000fd40  sub     r8, rcx
0x14000fd43  lea     r9, [rsp+78h+arg_10]
0x14000fd4b  lea     rcx, [rsp+78h+var_18]
0x14000fd50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd55  movsd   xmm0, qword ptr [rax]
0x14000fd59  mov     eax, [rax+8]
0x14000fd5c  mov     [rsp+78h+var_20], eax
0x14000fd60  movd    eax, xmm0
0x14000fd64  movsd   [rsp+78h+var_28], xmm0
0x14000fd6a  test    eax, eax
0x14000fd6c  jns     short loc_14000FD9F
0x14000fd6e  lea     rax, [rsp+78h+var_28]
0x14000fd73  mov     [rsp+78h+var_40], rbx
0x14000fd78  mov     [rsp+78h+var_48], rax
0x14000fd7d  lea     r8, aOnecoreuapDsSe_4; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000fd84  mov     rax, [rsp+78h+arg_30]
0x14000fd8c  mov     edx, 22h ; '"'
0x14000fd91  mov     rcx, rdi
0x14000fd94  mov     [rsp+78h+var_50], rax
0x14000fd99  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000fd9f  mov     ecx, 8007023Eh; this
0x14000fda4  mov     dword ptr [rsp+78h+var_28], ecx
0x14000fda8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000fdad  mov     dword ptr [rsp+78h+var_28+4], eax
0x14000fdb1  lea     r8, aOnecoreuapDsSe_4; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000fdb8  lea     rax, [rsp+78h+var_28]
0x14000fdbd  mov     [rsp+78h+var_40], rbx
0x14000fdc2  mov     [rsp+78h+var_48], rax
0x14000fdc7  mov     edx, 22h ; '"'
0x14000fdcc  mov     rax, [rsp+78h+arg_30]
0x14000fdd4  mov     rcx, rdi
0x14000fdd7  mov     [rsp+78h+var_50], rax
0x14000fddc  mov     [rsp+78h+var_20], esi
0x14000fde0  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
