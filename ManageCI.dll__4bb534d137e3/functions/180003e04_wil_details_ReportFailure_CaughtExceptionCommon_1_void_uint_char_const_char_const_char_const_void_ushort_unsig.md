# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180003e04`
- end: `0x180003ef1`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003d6c`

## callees

- `0x180003c90`
- `0x180003cf0`
- `0x180003e04`
- `0x180006744`
- `0x18002c010`

## string_xrefs

- `0x180003e87`: `onecore\base\ci\management\dll\dllmain.cpp`
- `0x180003ec4`: `onecore\base\ci\management\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        char a10)
{
  __int64 v11; // rcx
  __int64 (__fastcall *v14)(_BYTE *, __int64, __int64, char *); // rax
  __int64 v15; // rax
  int v16; // ecx
  int v18; // r9d
  _BYTE v19[56]; // [rsp+50h] [rbp-38h] BYREF

  a10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a8 + 2 * v11) );
  v14 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v14
    || (v15 = v14(v19, a8 + 2 * v11, 2048 - v11, &a10),
        v16 = *(_DWORD *)(v15 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v15,
        *(_DWORD *)(a1 + 8) = v16,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(a2, a3, (unsigned int)"onecore\\base\\ci\\management\\dll\\dllmain.cpp", v18);
  }
  wil::details::ReportFailure_Base<1,0>(a2, a3, "onecore\\base\\ci\\management\\dll\\dllmain.cpp");
  return a1;
}

```

## disassembly

```asm
0x180003e04  mov     rax, rsp
0x180003e07  push    rbx
0x180003e08  push    rbp
0x180003e09  push    rsi
0x180003e0a  push    rdi
0x180003e0b  push    r14
0x180003e0d  sub     rsp, 60h
0x180003e11  mov     rdi, [rsp+88h+arg_38]
0x180003e19  xor     r14d, r14d
0x180003e1c  mov     rbx, rcx
0x180003e1f  mov     [rax+50h], r14b
0x180003e23  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003e27  mov     esi, r8d
0x180003e2a  mov     rbp, rdx
0x180003e2d  inc     rcx
0x180003e30  cmp     [rdi+rcx*2], r14w
0x180003e35  jnz     short loc_180003E2D
0x180003e37  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180003e3e  mov     [rbx], r14
0x180003e41  mov     dword ptr [rbx+8], 1
0x180003e48  test    rax, rax
0x180003e4b  jz      short loc_180003EB5
0x180003e4d  lea     rdx, [rdi+rcx*2]
0x180003e51  mov     r8d, 800h
0x180003e57  sub     r8, rcx
0x180003e5a  lea     r9, [rsp+88h+arg_48]
0x180003e62  lea     rcx, [rsp+88h+var_38]
0x180003e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e6c  movsd   xmm0, qword ptr [rax]
0x180003e70  mov     ecx, [rax+8]
0x180003e73  movsd   qword ptr [rbx], xmm0
0x180003e77  mov     [rbx+8], ecx
0x180003e7a  cmp     [rbx], r14d
0x180003e7d  jge     short loc_180003EB5
0x180003e7f  mov     rax, [rsp+88h+arg_30]
0x180003e87  lea     r8, aOnecoreBaseCiM; "onecore\\base\\ci\\management\\dll\\dll"...
0x180003e8e  mov     [rsp+88h+var_50], rdi
0x180003e93  mov     edx, esi
0x180003e95  mov     [rsp+88h+var_58], rbx
0x180003e9a  mov     rcx, rbp
0x180003e9d  mov     [rsp+88h+var_60], rax
0x180003ea2  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180003ea7  mov     rax, rbx
0x180003eaa  add     rsp, 60h
0x180003eae  pop     r14
0x180003eb0  pop     rdi
0x180003eb1  pop     rsi
0x180003eb2  pop     rbp
0x180003eb3  pop     rbx
0x180003eb4  retn
0x180003eb5  mov     ecx, 8007023Eh; this
0x180003eba  mov     [rbx], ecx
0x180003ebc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003ec1  mov     [rbx+4], eax
0x180003ec4  lea     r8, aOnecoreBaseCiM; "onecore\\base\\ci\\management\\dll\\dll"...
0x180003ecb  mov     rax, [rsp+88h+arg_30]
0x180003ed3  mov     edx, esi
0x180003ed5  mov     [rsp+88h+var_50], rdi
0x180003eda  mov     rcx, rbp
0x180003edd  mov     [rsp+88h+var_58], rbx
0x180003ee2  mov     [rsp+88h+var_60], rax
0x180003ee7  mov     [rbx+8], r14d
0x180003eeb  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
