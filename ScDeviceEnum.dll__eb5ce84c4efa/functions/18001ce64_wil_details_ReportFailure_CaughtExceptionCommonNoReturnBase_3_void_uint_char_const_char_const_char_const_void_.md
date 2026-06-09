# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18001ce64`
- end: `0x18001cf52`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: `void __fastcall __noreturn(__int64, int, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ce34`

## callees

- `0x180002544`
- `0x180003e88`
- `0x18001ce64`
- `0x180020010`

## string_xrefs

- `0x18001cee9`: `ds\security\scard\common\certhlpr\errorcontract.h`
- `0x18001cf1d`: `ds\security\scard\common\certhlpr\errorcontract.h`

## pseudocode

```c
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
        27,
        (unsigned int)"ds\\security\\scard\\common\\certhlpr\\errorcontract.h",
        v10);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(
    a2,
    27,
    (unsigned int)"ds\\security\\scard\\common\\certhlpr\\errorcontract.h",
    v11);
}

```

## disassembly

```asm
0x18001ce64  mov     rax, rsp
0x18001ce67  mov     [rax+8], rbx
0x18001ce6b  mov     [rax+10h], rsi
0x18001ce6f  mov     [rax+18h], r8d
0x18001ce73  push    rdi
0x18001ce74  sub     rsp, 70h
0x18001ce78  mov     rbx, [rsp+78h+arg_38]
0x18001ce80  xor     esi, esi
0x18001ce82  mov     [rax+18h], sil
0x18001ce86  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001ce8a  mov     rdi, rdx
0x18001ce8d  inc     rcx
0x18001ce90  cmp     [rbx+rcx*2], si
0x18001ce94  jnz     short loc_18001CE8D
0x18001ce96  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18001ce9d  test    rax, rax
0x18001cea0  jz      short loc_18001CF0B
0x18001cea2  lea     rdx, [rbx+rcx*2]
0x18001cea6  mov     r8d, 800h
0x18001ceac  sub     r8, rcx
0x18001ceaf  lea     r9, [rsp+78h+arg_10]
0x18001ceb7  lea     rcx, [rsp+78h+var_18]
0x18001cebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cec1  movsd   xmm0, qword ptr [rax]
0x18001cec5  mov     eax, [rax+8]
0x18001cec8  mov     [rsp+78h+var_20], eax
0x18001cecc  movd    eax, xmm0
0x18001ced0  movsd   [rsp+78h+var_28], xmm0
0x18001ced6  test    eax, eax
0x18001ced8  jns     short loc_18001CF0B
0x18001ceda  lea     rax, [rsp+78h+var_28]
0x18001cedf  mov     [rsp+78h+var_40], rbx
0x18001cee4  mov     [rsp+78h+var_48], rax
0x18001cee9  lea     r8, aDsSecurityScar; "ds\\security\\scard\\common\\certhlpr\\"...
0x18001cef0  mov     rax, [rsp+78h+arg_30]
0x18001cef8  mov     edx, 1Bh
0x18001cefd  mov     rcx, rdi
0x18001cf00  mov     [rsp+78h+var_50], rax
0x18001cf05  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001cf0b  mov     ecx, 8007023Eh; this
0x18001cf10  mov     dword ptr [rsp+78h+var_28], ecx
0x18001cf14  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001cf19  mov     dword ptr [rsp+78h+var_28+4], eax
0x18001cf1d  lea     r8, aDsSecurityScar; "ds\\security\\scard\\common\\certhlpr\\"...
0x18001cf24  lea     rax, [rsp+78h+var_28]
0x18001cf29  mov     [rsp+78h+var_40], rbx
0x18001cf2e  mov     [rsp+78h+var_48], rax
0x18001cf33  mov     edx, 1Bh
0x18001cf38  mov     rax, [rsp+78h+arg_30]
0x18001cf40  mov     rcx, rdi
0x18001cf43  mov     [rsp+78h+var_50], rax
0x18001cf48  mov     [rsp+78h+var_20], esi
0x18001cf4c  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
