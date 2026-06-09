# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x140003a2c`
- end: `0x140003b18`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140003994`

## callees

- `0x140003900`
- `0x14000395c`
- `0x140003a2c`
- `0x140005cd0`
- `0x140019010`

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
0x140003a2c  mov     rax, rsp
0x140003a2f  push    rbx
0x140003a30  push    rbp
0x140003a31  push    rsi
0x140003a32  push    rdi
0x140003a33  push    r14
0x140003a35  push    r15
0x140003a37  sub     rsp, 68h
0x140003a3b  mov     rdi, [rsp+98h+arg_38]
0x140003a43  xor     r15d, r15d
0x140003a46  mov     rbx, rcx
0x140003a49  mov     [rax+50h], r15b
0x140003a4d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140003a51  mov     rsi, r9
0x140003a54  mov     ebp, r8d
0x140003a57  mov     r14, rdx
0x140003a5a  inc     rcx
0x140003a5d  cmp     [rdi+rcx*2], r15w
0x140003a62  jnz     short loc_140003A5A
0x140003a64  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x140003a6b  mov     [rbx], r15
0x140003a6e  mov     dword ptr [rbx+8], 1
0x140003a75  test    rax, rax
0x140003a78  jz      short loc_140003AE0
0x140003a7a  lea     rdx, [rdi+rcx*2]
0x140003a7e  mov     r8d, 800h
0x140003a84  sub     r8, rcx
0x140003a87  lea     r9, [rsp+98h+arg_48]
0x140003a8f  lea     rcx, [rsp+98h+var_48]
0x140003a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a99  movsd   xmm0, qword ptr [rax]
0x140003a9d  mov     ecx, [rax+8]
0x140003aa0  movsd   qword ptr [rbx], xmm0
0x140003aa4  mov     [rbx+8], ecx
0x140003aa7  cmp     [rbx], r15d
0x140003aaa  jge     short loc_140003AE0
0x140003aac  mov     rax, [rsp+98h+arg_30]
0x140003ab4  mov     r8, rsi
0x140003ab7  mov     [rsp+98h+var_60], rdi
0x140003abc  mov     edx, ebp
0x140003abe  mov     [rsp+98h+var_68], rbx
0x140003ac3  mov     rcx, r14
0x140003ac6  mov     [rsp+98h+var_70], rax
0x140003acb  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140003ad0  mov     rax, rbx
0x140003ad3  add     rsp, 68h
0x140003ad7  pop     r15
0x140003ad9  pop     r14
0x140003adb  pop     rdi
0x140003adc  pop     rsi
0x140003add  pop     rbp
0x140003ade  pop     rbx
0x140003adf  retn
0x140003ae0  mov     ecx, 8007023Eh; this
0x140003ae5  mov     [rbx], ecx
0x140003ae7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003aec  mov     [rbx+4], eax
0x140003aef  mov     r8, rsi
0x140003af2  mov     rax, [rsp+98h+arg_30]
0x140003afa  mov     edx, ebp
0x140003afc  mov     [rsp+98h+var_60], rdi
0x140003b01  mov     rcx, r14
0x140003b04  mov     [rsp+98h+var_68], rbx
0x140003b09  mov     [rsp+98h+var_70], rax
0x140003b0e  mov     [rbx+8], r15d
0x140003b12  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
