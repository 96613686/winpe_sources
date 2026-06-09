# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180029918`
- end: `0x180029a06`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800298c8`

## callees

- `0x18000ab54`
- `0x18000fffc`
- `0x180029918`
- `0x18002e010`

## string_xrefs

- `0x18002999d`: `ds\security\scard\common\devhlpr\lib\errorcontract.h`
- `0x1800299d1`: `ds\security\scard\common\devhlpr\lib\errorcontract.h`

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
        104,
        (unsigned int)"ds\\security\\scard\\common\\devhlpr\\lib\\errorcontract.h",
        v10);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(
    a2,
    104,
    (unsigned int)"ds\\security\\scard\\common\\devhlpr\\lib\\errorcontract.h",
    v11);
}

```

## disassembly

```asm
0x180029918  mov     rax, rsp
0x18002991b  mov     [rax+8], rbx
0x18002991f  mov     [rax+10h], rsi
0x180029923  mov     [rax+18h], r8d
0x180029927  push    rdi
0x180029928  sub     rsp, 70h
0x18002992c  mov     rbx, [rsp+78h+arg_38]
0x180029934  xor     esi, esi
0x180029936  mov     [rax+18h], sil
0x18002993a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002993e  mov     rdi, rdx
0x180029941  inc     rcx
0x180029944  cmp     [rbx+rcx*2], si
0x180029948  jnz     short loc_180029941
0x18002994a  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180029951  test    rax, rax
0x180029954  jz      short loc_1800299BF
0x180029956  lea     rdx, [rbx+rcx*2]
0x18002995a  mov     r8d, 800h
0x180029960  sub     r8, rcx
0x180029963  lea     r9, [rsp+78h+arg_10]
0x18002996b  lea     rcx, [rsp+78h+var_18]
0x180029970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029975  movsd   xmm0, qword ptr [rax]
0x180029979  mov     eax, [rax+8]
0x18002997c  mov     [rsp+78h+var_20], eax
0x180029980  movd    eax, xmm0
0x180029984  movsd   [rsp+78h+var_28], xmm0
0x18002998a  test    eax, eax
0x18002998c  jns     short loc_1800299BF
0x18002998e  lea     rax, [rsp+78h+var_28]
0x180029993  mov     [rsp+78h+var_40], rbx
0x180029998  mov     [rsp+78h+var_48], rax
0x18002999d  lea     r8, aDsSecurityScar; "ds\\security\\scard\\common\\devhlpr\\l"...
0x1800299a4  mov     rax, [rsp+78h+arg_30]
0x1800299ac  mov     edx, 68h ; 'h'
0x1800299b1  mov     rcx, rdi
0x1800299b4  mov     [rsp+78h+var_50], rax
0x1800299b9  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800299bf  mov     ecx, 8007023Eh; this
0x1800299c4  mov     dword ptr [rsp+78h+var_28], ecx
0x1800299c8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800299cd  mov     dword ptr [rsp+78h+var_28+4], eax
0x1800299d1  lea     r8, aDsSecurityScar; "ds\\security\\scard\\common\\devhlpr\\l"...
0x1800299d8  lea     rax, [rsp+78h+var_28]
0x1800299dd  mov     [rsp+78h+var_40], rbx
0x1800299e2  mov     [rsp+78h+var_48], rax
0x1800299e7  mov     edx, 68h ; 'h'
0x1800299ec  mov     rax, [rsp+78h+arg_30]
0x1800299f4  mov     rcx, rdi
0x1800299f7  mov     [rsp+78h+var_50], rax
0x1800299fc  mov     [rsp+78h+var_20], esi
0x180029a00  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
