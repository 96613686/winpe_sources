# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180005b14`
- end: `0x180005c00`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005a7c`

## callees

- `0x180004650`
- `0x1800059b0`
- `0x180005a0c`
- `0x180005b14`
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
0x180005b14  mov     rax, rsp
0x180005b17  push    rbx
0x180005b18  push    rbp
0x180005b19  push    rsi
0x180005b1a  push    rdi
0x180005b1b  push    r14
0x180005b1d  push    r15
0x180005b1f  sub     rsp, 68h
0x180005b23  mov     rdi, [rsp+98h+arg_38]
0x180005b2b  xor     r15d, r15d
0x180005b2e  mov     rbx, rcx
0x180005b31  mov     [rax+50h], r15b
0x180005b35  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180005b39  mov     rsi, r9
0x180005b3c  mov     ebp, r8d
0x180005b3f  mov     r14, rdx
0x180005b42  inc     rcx
0x180005b45  cmp     [rdi+rcx*2], r15w
0x180005b4a  jnz     short loc_180005B42
0x180005b4c  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180005b53  mov     [rbx], r15
0x180005b56  mov     dword ptr [rbx+8], 1
0x180005b5d  test    rax, rax
0x180005b60  jz      short loc_180005BC8
0x180005b62  lea     rdx, [rdi+rcx*2]
0x180005b66  mov     r8d, 800h
0x180005b6c  sub     r8, rcx
0x180005b6f  lea     r9, [rsp+98h+arg_48]
0x180005b77  lea     rcx, [rsp+98h+var_48]
0x180005b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b81  movsd   xmm0, qword ptr [rax]
0x180005b85  mov     ecx, [rax+8]
0x180005b88  movsd   qword ptr [rbx], xmm0
0x180005b8c  mov     [rbx+8], ecx
0x180005b8f  cmp     [rbx], r15d
0x180005b92  jge     short loc_180005BC8
0x180005b94  mov     rax, [rsp+98h+arg_30]
0x180005b9c  mov     r8, rsi
0x180005b9f  mov     [rsp+98h+var_60], rdi
0x180005ba4  mov     edx, ebp
0x180005ba6  mov     [rsp+98h+var_68], rbx
0x180005bab  mov     rcx, r14
0x180005bae  mov     [rsp+98h+var_70], rax
0x180005bb3  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180005bb8  mov     rax, rbx
0x180005bbb  add     rsp, 68h
0x180005bbf  pop     r15
0x180005bc1  pop     r14
0x180005bc3  pop     rdi
0x180005bc4  pop     rsi
0x180005bc5  pop     rbp
0x180005bc6  pop     rbx
0x180005bc7  retn
0x180005bc8  mov     ecx, 8007023Eh; this
0x180005bcd  mov     [rbx], ecx
0x180005bcf  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005bd4  mov     [rbx+4], eax
0x180005bd7  mov     r8, rsi
0x180005bda  mov     rax, [rsp+98h+arg_30]
0x180005be2  mov     edx, ebp
0x180005be4  mov     [rsp+98h+var_60], rdi
0x180005be9  mov     rcx, r14
0x180005bec  mov     [rsp+98h+var_68], rbx
0x180005bf1  mov     [rsp+98h+var_70], rax
0x180005bf6  mov     [rbx+8], r15d
0x180005bfa  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
