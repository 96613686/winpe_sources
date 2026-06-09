# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180003e14`
- end: `0x180003f00`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003cf4`

## callees

- `0x180003c30`
- `0x180003c90`
- `0x180003e14`
- `0x180007278`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
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
  int v17; // r9d
  int v18; // ecx
  int v20; // r9d
  int v21; // [rsp+20h] [rbp-78h]
  _BYTE v22[72]; // [rsp+50h] [rbp-48h] BYREF

  a10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a8 + 2 * v11) );
  v15 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v15
    || (v16 = v15(v22, a8 + 2 * v11, 2048 - v11, &a10),
        v18 = *(_DWORD *)(v16 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v16,
        *(_DWORD *)(a1 + 8) = v18,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(a2, a3, a4, v20, v21, a7, a1, a8);
  }
  wil::details::ReportFailure_Base<1,0>(a2, a3, a4, v17, v21, a7, a1, a8);
  return a1;
}

```

## disassembly

```asm
0x180003e14  mov     rax, rsp
0x180003e17  push    rbx
0x180003e18  push    rbp
0x180003e19  push    rsi
0x180003e1a  push    rdi
0x180003e1b  push    r14
0x180003e1d  push    r15
0x180003e1f  sub     rsp, 68h
0x180003e23  mov     rdi, [rsp+98h+arg_38]
0x180003e2b  xor     r15d, r15d
0x180003e2e  mov     rbx, rcx
0x180003e31  mov     [rax+50h], r15b
0x180003e35  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003e39  mov     rsi, r9
0x180003e3c  mov     ebp, r8d
0x180003e3f  mov     r14, rdx
0x180003e42  inc     rcx
0x180003e45  cmp     [rdi+rcx*2], r15w
0x180003e4a  jnz     short loc_180003E42
0x180003e4c  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180003e53  mov     [rbx], r15
0x180003e56  mov     dword ptr [rbx+8], 1
0x180003e5d  test    rax, rax
0x180003e60  jz      short loc_180003EC8
0x180003e62  lea     rdx, [rdi+rcx*2]
0x180003e66  mov     r8d, 800h
0x180003e6c  sub     r8, rcx
0x180003e6f  lea     r9, [rsp+98h+arg_48]
0x180003e77  lea     rcx, [rsp+98h+var_48]
0x180003e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e81  movsd   xmm0, qword ptr [rax]
0x180003e85  mov     ecx, [rax+8]
0x180003e88  movsd   qword ptr [rbx], xmm0
0x180003e8c  mov     [rbx+8], ecx
0x180003e8f  cmp     [rbx], r15d
0x180003e92  jge     short loc_180003EC8
0x180003e94  mov     rax, [rsp+98h+arg_30]
0x180003e9c  mov     r8, rsi
0x180003e9f  mov     [rsp+98h+var_60], rdi
0x180003ea4  mov     edx, ebp
0x180003ea6  mov     [rsp+98h+var_68], rbx
0x180003eab  mov     rcx, r14
0x180003eae  mov     [rsp+98h+var_70], rax
0x180003eb3  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180003eb8  mov     rax, rbx
0x180003ebb  add     rsp, 68h
0x180003ebf  pop     r15
0x180003ec1  pop     r14
0x180003ec3  pop     rdi
0x180003ec4  pop     rsi
0x180003ec5  pop     rbp
0x180003ec6  pop     rbx
0x180003ec7  retn
0x180003ec8  mov     ecx, 8007023Eh; this
0x180003ecd  mov     [rbx], ecx
0x180003ecf  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003ed4  mov     [rbx+4], eax
0x180003ed7  mov     r8, rsi
0x180003eda  mov     rax, [rsp+98h+arg_30]
0x180003ee2  mov     edx, ebp
0x180003ee4  mov     [rsp+98h+var_60], rdi
0x180003ee9  mov     rcx, r14
0x180003eec  mov     [rsp+98h+var_68], rbx
0x180003ef1  mov     [rsp+98h+var_70], rax
0x180003ef6  mov     [rbx+8], r15d
0x180003efa  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
