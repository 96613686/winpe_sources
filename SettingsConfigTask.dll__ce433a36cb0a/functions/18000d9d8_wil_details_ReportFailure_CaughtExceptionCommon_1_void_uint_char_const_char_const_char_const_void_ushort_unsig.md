# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000d9d8`
- end: `0x18000dac4`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d8a8`

## callees

- `0x1800038a8`
- `0x180003908`
- `0x180006f24`
- `0x18000d9d8`
- `0x180024010`

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
0x18000d9d8  mov     rax, rsp
0x18000d9db  push    rbx
0x18000d9dc  push    rbp
0x18000d9dd  push    rsi
0x18000d9de  push    rdi
0x18000d9df  push    r14
0x18000d9e1  push    r15
0x18000d9e3  sub     rsp, 68h
0x18000d9e7  mov     rdi, [rsp+98h+arg_38]
0x18000d9ef  xor     r15d, r15d
0x18000d9f2  mov     rbx, rcx
0x18000d9f5  mov     [rax+50h], r15b
0x18000d9f9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d9fd  mov     rsi, r9
0x18000da00  mov     ebp, r8d
0x18000da03  mov     r14, rdx
0x18000da06  inc     rcx
0x18000da09  cmp     [rdi+rcx*2], r15w
0x18000da0e  jnz     short loc_18000DA06
0x18000da10  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000da17  mov     [rbx], r15
0x18000da1a  mov     dword ptr [rbx+8], 1
0x18000da21  test    rax, rax
0x18000da24  jz      short loc_18000DA8C
0x18000da26  lea     rdx, [rdi+rcx*2]
0x18000da2a  mov     r8d, 800h
0x18000da30  sub     r8, rcx
0x18000da33  lea     r9, [rsp+98h+arg_48]
0x18000da3b  lea     rcx, [rsp+98h+var_48]
0x18000da40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da45  movsd   xmm0, qword ptr [rax]
0x18000da49  mov     ecx, [rax+8]
0x18000da4c  movsd   qword ptr [rbx], xmm0
0x18000da50  mov     [rbx+8], ecx
0x18000da53  cmp     [rbx], r15d
0x18000da56  jge     short loc_18000DA8C
0x18000da58  mov     rax, [rsp+98h+arg_30]
0x18000da60  mov     r8, rsi
0x18000da63  mov     [rsp+98h+var_60], rdi
0x18000da68  mov     edx, ebp
0x18000da6a  mov     [rsp+98h+var_68], rbx
0x18000da6f  mov     rcx, r14
0x18000da72  mov     [rsp+98h+var_70], rax
0x18000da77  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000da7c  mov     rax, rbx
0x18000da7f  add     rsp, 68h
0x18000da83  pop     r15
0x18000da85  pop     r14
0x18000da87  pop     rdi
0x18000da88  pop     rsi
0x18000da89  pop     rbp
0x18000da8a  pop     rbx
0x18000da8b  retn
0x18000da8c  mov     ecx, 8007023Eh; this
0x18000da91  mov     [rbx], ecx
0x18000da93  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000da98  mov     [rbx+4], eax
0x18000da9b  mov     r8, rsi
0x18000da9e  mov     rax, [rsp+98h+arg_30]
0x18000daa6  mov     edx, ebp
0x18000daa8  mov     [rsp+98h+var_60], rdi
0x18000daad  mov     rcx, r14
0x18000dab0  mov     [rsp+98h+var_68], rbx
0x18000dab5  mov     [rsp+98h+var_70], rax
0x18000daba  mov     [rbx+8], r15d
0x18000dabe  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
