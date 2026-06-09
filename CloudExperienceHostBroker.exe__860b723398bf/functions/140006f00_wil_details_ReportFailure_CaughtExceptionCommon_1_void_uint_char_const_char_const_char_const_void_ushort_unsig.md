# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x140006f00`
- end: `0x140006fec`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140006e78`

## callees

- `0x1400027a0`
- `0x1400027fc`
- `0x14000417c`
- `0x140006f00`
- `0x14000a010`

## string_xrefs

- `0x140006f7f`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`
- `0x140006fbd`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rdi
  __int64 v10; // rcx
  __int64 (__fastcall *v12)(_BYTE *, __int64, __int64, int *); // rax
  __int64 v13; // rax
  int v14; // r9d
  int v15; // ecx
  int v17; // r9d
  int v18; // [rsp+20h] [rbp-68h]
  __int64 v19; // [rsp+28h] [rbp-60h]
  _BYTE v20[56]; // [rsp+50h] [rbp-38h] BYREF
  int v21; // [rsp+A0h] [rbp+18h] BYREF

  v21 = a3;
  v8 = a8;
  LOBYTE(v21) = 0;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a8 + 2 * v10) );
  v12 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, int *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v12
    || (v13 = v12(v20, v8 + 2 * v10, 2048 - v10, &v21),
        v15 = *(_DWORD *)(v13 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v13,
        *(_DWORD *)(a1 + 8) = v15,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    v19 = a7;
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(
      a2,
      46,
      (int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
      v17,
      v18,
      v19,
      a1,
      v8);
  }
  wil::details::ReportFailure_Base<1,0>(
    a2,
    46,
    (int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
    v14,
    v18,
    a7,
    a1,
    v8);
  return a1;
}

```

## disassembly

```asm
0x140006f00  mov     rax, rsp
0x140006f03  mov     [rax+18h], r8d
0x140006f07  push    rbx
0x140006f08  push    rbp
0x140006f09  push    rsi
0x140006f0a  push    rdi
0x140006f0b  sub     rsp, 68h
0x140006f0f  mov     rdi, [rsp+88h+arg_38]
0x140006f17  xor     ebp, ebp
0x140006f19  mov     rbx, rcx
0x140006f1c  mov     [rax+18h], bpl
0x140006f20  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140006f24  mov     rsi, rdx
0x140006f27  inc     rcx
0x140006f2a  cmp     [rdi+rcx*2], bp
0x140006f2e  jnz     short loc_140006F27
0x140006f30  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x140006f37  mov     [rbx], rbp
0x140006f3a  mov     dword ptr [rbx+8], 1
0x140006f41  test    rax, rax
0x140006f44  jz      short loc_140006FAE
0x140006f46  lea     rdx, [rdi+rcx*2]
0x140006f4a  mov     r8d, 800h
0x140006f50  sub     r8, rcx
0x140006f53  lea     r9, [rsp+88h+arg_10]
0x140006f5b  lea     rcx, [rsp+88h+var_38]
0x140006f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f65  movsd   xmm0, qword ptr [rax]
0x140006f69  mov     ecx, [rax+8]
0x140006f6c  movsd   qword ptr [rbx], xmm0
0x140006f70  mov     [rbx+8], ecx
0x140006f73  cmp     [rbx], ebp
0x140006f75  jge     short loc_140006FAE
0x140006f77  mov     rax, [rsp+88h+arg_30]
0x140006f7f  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x140006f86  mov     [rsp+88h+var_50], rdi
0x140006f8b  mov     edx, 2Eh ; '.'
0x140006f90  mov     [rsp+88h+var_58], rbx
0x140006f95  mov     rcx, rsi
0x140006f98  mov     [rsp+88h+var_60], rax
0x140006f9d  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140006fa2  mov     rax, rbx
0x140006fa5  add     rsp, 68h
0x140006fa9  pop     rdi
0x140006faa  pop     rsi
0x140006fab  pop     rbp
0x140006fac  pop     rbx
0x140006fad  retn
0x140006fae  mov     ecx, 8007023Eh; this
0x140006fb3  mov     [rbx], ecx
0x140006fb5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006fba  mov     [rbx+4], eax
0x140006fbd  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x140006fc4  mov     rax, [rsp+88h+arg_30]
0x140006fcc  mov     edx, 2Eh ; '.'
0x140006fd1  mov     [rsp+88h+var_50], rdi
0x140006fd6  mov     rcx, rsi
0x140006fd9  mov     [rsp+88h+var_58], rbx
0x140006fde  mov     [rsp+88h+var_60], rax
0x140006fe3  mov     [rbx+8], ebp
0x140006fe6  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
