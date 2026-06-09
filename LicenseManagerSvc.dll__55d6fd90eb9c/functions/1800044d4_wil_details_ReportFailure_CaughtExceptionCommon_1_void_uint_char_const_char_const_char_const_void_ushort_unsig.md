# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x1800044d4`
- end: `0x1800045c0`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000443c`

## callees

- `0x180001c34`
- `0x180004378`
- `0x1800043d8`
- `0x1800044d4`
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
0x1800044d4  mov     rax, rsp
0x1800044d7  push    rbx
0x1800044d8  push    rbp
0x1800044d9  push    rsi
0x1800044da  push    rdi
0x1800044db  push    r14
0x1800044dd  push    r15
0x1800044df  sub     rsp, 68h
0x1800044e3  mov     rdi, [rsp+98h+arg_38]
0x1800044eb  xor     r15d, r15d
0x1800044ee  mov     rbx, rcx
0x1800044f1  mov     [rax+50h], r15b
0x1800044f5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800044f9  mov     rsi, r9
0x1800044fc  mov     ebp, r8d
0x1800044ff  mov     r14, rdx
0x180004502  inc     rcx
0x180004505  cmp     [rdi+rcx*2], r15w
0x18000450a  jnz     short loc_180004502
0x18000450c  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180004513  mov     [rbx], r15
0x180004516  mov     dword ptr [rbx+8], 1
0x18000451d  test    rax, rax
0x180004520  jz      short loc_180004588
0x180004522  lea     rdx, [rdi+rcx*2]
0x180004526  mov     r8d, 800h
0x18000452c  sub     r8, rcx
0x18000452f  lea     r9, [rsp+98h+arg_48]
0x180004537  lea     rcx, [rsp+98h+var_48]
0x18000453c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004541  movsd   xmm0, qword ptr [rax]
0x180004545  mov     ecx, [rax+8]
0x180004548  movsd   qword ptr [rbx], xmm0
0x18000454c  mov     [rbx+8], ecx
0x18000454f  cmp     [rbx], r15d
0x180004552  jge     short loc_180004588
0x180004554  mov     rax, [rsp+98h+arg_30]
0x18000455c  mov     r8, rsi
0x18000455f  mov     [rsp+98h+var_60], rdi
0x180004564  mov     edx, ebp
0x180004566  mov     [rsp+98h+var_68], rbx
0x18000456b  mov     rcx, r14
0x18000456e  mov     [rsp+98h+var_70], rax
0x180004573  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180004578  mov     rax, rbx
0x18000457b  add     rsp, 68h
0x18000457f  pop     r15
0x180004581  pop     r14
0x180004583  pop     rdi
0x180004584  pop     rsi
0x180004585  pop     rbp
0x180004586  pop     rbx
0x180004587  retn
0x180004588  mov     ecx, 8007023Eh; this
0x18000458d  mov     [rbx], ecx
0x18000458f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004594  mov     [rbx+4], eax
0x180004597  mov     r8, rsi
0x18000459a  mov     rax, [rsp+98h+arg_30]
0x1800045a2  mov     edx, ebp
0x1800045a4  mov     [rsp+98h+var_60], rdi
0x1800045a9  mov     rcx, r14
0x1800045ac  mov     [rsp+98h+var_68], rbx
0x1800045b1  mov     [rsp+98h+var_70], rax
0x1800045b6  mov     [rbx+8], r15d
0x1800045ba  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
