# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,wchar_t *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000fbe8`
- end: `0x18000fcd4`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEA_W_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000fab0`

## callees

- `0x180004410`
- `0x180004470`
- `0x180005f94`
- `0x18000fbe8`
- `0x180031010`

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
0x18000fbe8  mov     rax, rsp
0x18000fbeb  push    rbx
0x18000fbec  push    rbp
0x18000fbed  push    rsi
0x18000fbee  push    rdi
0x18000fbef  push    r14
0x18000fbf1  push    r15
0x18000fbf3  sub     rsp, 68h
0x18000fbf7  mov     rdi, [rsp+98h+arg_38]
0x18000fbff  xor     r15d, r15d
0x18000fc02  mov     rbx, rcx
0x18000fc05  mov     [rax+50h], r15b
0x18000fc09  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000fc0d  mov     rsi, r9
0x18000fc10  mov     ebp, r8d
0x18000fc13  mov     r14, rdx
0x18000fc16  inc     rcx
0x18000fc19  cmp     [rdi+rcx*2], r15w
0x18000fc1e  jnz     short loc_18000FC16
0x18000fc20  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000fc27  mov     [rbx], r15
0x18000fc2a  mov     dword ptr [rbx+8], 1
0x18000fc31  test    rax, rax
0x18000fc34  jz      short loc_18000FC9C
0x18000fc36  lea     rdx, [rdi+rcx*2]
0x18000fc3a  mov     r8d, 800h
0x18000fc40  sub     r8, rcx
0x18000fc43  lea     r9, [rsp+98h+arg_48]
0x18000fc4b  lea     rcx, [rsp+98h+var_48]
0x18000fc50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc55  movsd   xmm0, qword ptr [rax]
0x18000fc59  mov     ecx, [rax+8]
0x18000fc5c  movsd   qword ptr [rbx], xmm0
0x18000fc60  mov     [rbx+8], ecx
0x18000fc63  cmp     [rbx], r15d
0x18000fc66  jge     short loc_18000FC9C
0x18000fc68  mov     rax, [rsp+98h+arg_30]
0x18000fc70  mov     r8, rsi
0x18000fc73  mov     [rsp+98h+var_60], rdi
0x18000fc78  mov     edx, ebp
0x18000fc7a  mov     [rsp+98h+var_68], rbx
0x18000fc7f  mov     rcx, r14
0x18000fc82  mov     [rsp+98h+var_70], rax
0x18000fc87  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fc8c  mov     rax, rbx
0x18000fc8f  add     rsp, 68h
0x18000fc93  pop     r15
0x18000fc95  pop     r14
0x18000fc97  pop     rdi
0x18000fc98  pop     rsi
0x18000fc99  pop     rbp
0x18000fc9a  pop     rbx
0x18000fc9b  retn
0x18000fc9c  mov     ecx, 8007023Eh; this
0x18000fca1  mov     [rbx], ecx
0x18000fca3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fca8  mov     [rbx+4], eax
0x18000fcab  mov     r8, rsi
0x18000fcae  mov     rax, [rsp+98h+arg_30]
0x18000fcb6  mov     edx, ebp
0x18000fcb8  mov     [rsp+98h+var_60], rdi
0x18000fcbd  mov     rcx, r14
0x18000fcc0  mov     [rsp+98h+var_68], rbx
0x18000fcc5  mov     [rsp+98h+var_70], rax
0x18000fcca  mov     [rbx+8], r15d
0x18000fcce  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
