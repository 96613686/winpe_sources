# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000b2a8`
- end: `0x18000b394`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b178`

## callees

- `0x180003f94`
- `0x180003ff4`
- `0x1800067a0`
- `0x18000b2a8`
- `0x180018010`

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
  __int64 (__fastcall *v15)(_BYTE *, __int64, __int64, char *); // rax
  __int64 v16; // rax
  int v17; // ecx
  int v19; // r9d
  _BYTE v20[72]; // [rsp+50h] [rbp-48h] BYREF

  a10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a8 + 2 * v11) );
  v15 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v15
    || (v16 = v15(v20, a8 + 2 * v11, 2048 - v11, &a10),
        v17 = *(_DWORD *)(v16 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v16,
        *(_DWORD *)(a1 + 8) = v17,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(a2, a3, a4, v19);
  }
  wil::details::ReportFailure_Base<1,0>(a2, a3, a4);
  return a1;
}

```

## disassembly

```asm
0x18000b2a8  mov     rax, rsp
0x18000b2ab  push    rbx
0x18000b2ac  push    rbp
0x18000b2ad  push    rsi
0x18000b2ae  push    rdi
0x18000b2af  push    r14
0x18000b2b1  push    r15
0x18000b2b3  sub     rsp, 68h
0x18000b2b7  mov     rdi, [rsp+98h+arg_38]
0x18000b2bf  xor     r15d, r15d
0x18000b2c2  mov     rbx, rcx
0x18000b2c5  mov     [rax+50h], r15b
0x18000b2c9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b2cd  mov     rsi, r9
0x18000b2d0  mov     ebp, r8d
0x18000b2d3  mov     r14, rdx
0x18000b2d6  inc     rcx
0x18000b2d9  cmp     [rdi+rcx*2], r15w
0x18000b2de  jnz     short loc_18000B2D6
0x18000b2e0  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000b2e7  mov     [rbx], r15
0x18000b2ea  mov     dword ptr [rbx+8], 1
0x18000b2f1  test    rax, rax
0x18000b2f4  jz      short loc_18000B35C
0x18000b2f6  lea     rdx, [rdi+rcx*2]
0x18000b2fa  mov     r8d, 800h
0x18000b300  sub     r8, rcx
0x18000b303  lea     r9, [rsp+98h+arg_48]
0x18000b30b  lea     rcx, [rsp+98h+var_48]
0x18000b310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b315  movsd   xmm0, qword ptr [rax]
0x18000b319  mov     ecx, [rax+8]
0x18000b31c  movsd   qword ptr [rbx], xmm0
0x18000b320  mov     [rbx+8], ecx
0x18000b323  cmp     [rbx], r15d
0x18000b326  jge     short loc_18000B35C
0x18000b328  mov     rax, [rsp+98h+arg_30]
0x18000b330  mov     r8, rsi
0x18000b333  mov     [rsp+98h+var_60], rdi
0x18000b338  mov     edx, ebp
0x18000b33a  mov     [rsp+98h+var_68], rbx
0x18000b33f  mov     rcx, r14
0x18000b342  mov     [rsp+98h+var_70], rax
0x18000b347  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000b34c  mov     rax, rbx
0x18000b34f  add     rsp, 68h
0x18000b353  pop     r15
0x18000b355  pop     r14
0x18000b357  pop     rdi
0x18000b358  pop     rsi
0x18000b359  pop     rbp
0x18000b35a  pop     rbx
0x18000b35b  retn
0x18000b35c  mov     ecx, 8007023Eh; this
0x18000b361  mov     [rbx], ecx
0x18000b363  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b368  mov     [rbx+4], eax
0x18000b36b  mov     r8, rsi
0x18000b36e  mov     rax, [rsp+98h+arg_30]
0x18000b376  mov     edx, ebp
0x18000b378  mov     [rsp+98h+var_60], rdi
0x18000b37d  mov     rcx, r14
0x18000b380  mov     [rsp+98h+var_68], rbx
0x18000b385  mov     [rsp+98h+var_70], rax
0x18000b38a  mov     [rbx+8], r15d
0x18000b38e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
