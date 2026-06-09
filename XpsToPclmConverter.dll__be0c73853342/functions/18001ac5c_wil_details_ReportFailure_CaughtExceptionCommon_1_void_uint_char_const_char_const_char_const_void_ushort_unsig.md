# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18001ac5c`
- end: `0x18001ad48`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001abc4`

## callees

- `0x1800078f0`
- `0x18000794c`
- `0x180009e34`
- `0x18001ac5c`
- `0x18001f010`

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
0x18001ac5c  mov     rax, rsp
0x18001ac5f  push    rbx
0x18001ac60  push    rbp
0x18001ac61  push    rsi
0x18001ac62  push    rdi
0x18001ac63  push    r14
0x18001ac65  push    r15
0x18001ac67  sub     rsp, 68h
0x18001ac6b  mov     rdi, [rsp+98h+arg_38]
0x18001ac73  xor     r15d, r15d
0x18001ac76  mov     rbx, rcx
0x18001ac79  mov     [rax+50h], r15b
0x18001ac7d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001ac81  mov     rsi, r9
0x18001ac84  mov     ebp, r8d
0x18001ac87  mov     r14, rdx
0x18001ac8a  inc     rcx
0x18001ac8d  cmp     [rdi+rcx*2], r15w
0x18001ac92  jnz     short loc_18001AC8A
0x18001ac94  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18001ac9b  mov     [rbx], r15
0x18001ac9e  mov     dword ptr [rbx+8], 1
0x18001aca5  test    rax, rax
0x18001aca8  jz      short loc_18001AD10
0x18001acaa  lea     rdx, [rdi+rcx*2]
0x18001acae  mov     r8d, 800h
0x18001acb4  sub     r8, rcx
0x18001acb7  lea     r9, [rsp+98h+arg_48]
0x18001acbf  lea     rcx, [rsp+98h+var_48]
0x18001acc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acc9  movsd   xmm0, qword ptr [rax]
0x18001accd  mov     ecx, [rax+8]
0x18001acd0  movsd   qword ptr [rbx], xmm0
0x18001acd4  mov     [rbx+8], ecx
0x18001acd7  cmp     [rbx], r15d
0x18001acda  jge     short loc_18001AD10
0x18001acdc  mov     rax, [rsp+98h+arg_30]
0x18001ace4  mov     r8, rsi
0x18001ace7  mov     [rsp+98h+var_60], rdi
0x18001acec  mov     edx, ebp
0x18001acee  mov     [rsp+98h+var_68], rbx
0x18001acf3  mov     rcx, r14
0x18001acf6  mov     [rsp+98h+var_70], rax
0x18001acfb  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001ad00  mov     rax, rbx
0x18001ad03  add     rsp, 68h
0x18001ad07  pop     r15
0x18001ad09  pop     r14
0x18001ad0b  pop     rdi
0x18001ad0c  pop     rsi
0x18001ad0d  pop     rbp
0x18001ad0e  pop     rbx
0x18001ad0f  retn
0x18001ad10  mov     ecx, 8007023Eh; this
0x18001ad15  mov     [rbx], ecx
0x18001ad17  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001ad1c  mov     [rbx+4], eax
0x18001ad1f  mov     r8, rsi
0x18001ad22  mov     rax, [rsp+98h+arg_30]
0x18001ad2a  mov     edx, ebp
0x18001ad2c  mov     [rsp+98h+var_60], rdi
0x18001ad31  mov     rcx, r14
0x18001ad34  mov     [rsp+98h+var_68], rbx
0x18001ad39  mov     [rsp+98h+var_70], rax
0x18001ad3e  mov     [rbx+8], r15d
0x18001ad42  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
