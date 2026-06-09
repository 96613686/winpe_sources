# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x140003adc`
- end: `0x140003bc9`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140003a44`

## callees

- `0x1400039b0`
- `0x140003a0c`
- `0x140003adc`
- `0x140005ed4`
- `0x14001a010`

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
0x140003adc  mov     rax, rsp
0x140003adf  push    rbx
0x140003ae0  push    rbp
0x140003ae1  push    rsi
0x140003ae2  push    rdi
0x140003ae3  push    r14
0x140003ae5  push    r15
0x140003ae7  sub     rsp, 68h
0x140003aeb  mov     rdi, [rsp+98h+arg_38]
0x140003af3  xor     r15d, r15d
0x140003af6  mov     rbx, rcx
0x140003af9  mov     [rax+50h], r15b
0x140003afd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140003b01  mov     rsi, r9
0x140003b04  mov     ebp, r8d
0x140003b07  mov     r14, rdx
0x140003b0a  inc     rcx
0x140003b0d  cmp     [rdi+rcx*2], r15w
0x140003b12  jnz     short loc_140003B0A
0x140003b14  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x140003b1b  mov     [rbx], r15
0x140003b1e  mov     dword ptr [rbx+8], 1
0x140003b25  test    rax, rax
0x140003b28  jz      short loc_140003B91
0x140003b2a  lea     rdx, [rdi+rcx*2]
0x140003b2e  mov     r8d, 800h
0x140003b34  sub     r8, rcx
0x140003b37  lea     r9, [rsp+98h+arg_48]
0x140003b3f  lea     rcx, [rsp+98h+var_48]
0x140003b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b49  movsd   xmm0, qword ptr [rax]
0x140003b4d  mov     ecx, [rax+8]
0x140003b50  movsd   qword ptr [rbx], xmm0
0x140003b54  mov     [rbx+8], ecx
0x140003b57  cmp     [rbx], r15d
0x140003b5a  jge     short loc_140003B91
0x140003b5c  mov     rax, [rsp+98h+arg_30]
0x140003b64  mov     r8, rsi
0x140003b67  mov     [rsp+98h+var_60], rdi
0x140003b6c  mov     edx, ebp
0x140003b6e  mov     [rsp+98h+var_68], rbx
0x140003b73  mov     rcx, r14
0x140003b76  mov     [rsp+98h+var_70], rax
0x140003b7b  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140003b80  mov     rax, rbx
0x140003b83  add     rsp, 68h
0x140003b87  pop     r15
0x140003b89  pop     r14
0x140003b8b  pop     rdi
0x140003b8c  pop     rsi
0x140003b8d  pop     rbp
0x140003b8e  pop     rbx
0x140003b8f  retn
0x140003b91  mov     ecx, 8007023Eh; this
0x140003b96  mov     [rbx], ecx
0x140003b98  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003b9d  mov     [rbx+4], eax
0x140003ba0  mov     r8, rsi
0x140003ba3  mov     rax, [rsp+98h+arg_30]
0x140003bab  mov     edx, ebp
0x140003bad  mov     [rsp+98h+var_60], rdi
0x140003bb2  mov     rcx, r14
0x140003bb5  mov     [rsp+98h+var_68], rbx
0x140003bba  mov     [rsp+98h+var_70], rax
0x140003bbf  mov     [rbx+8], r15d
0x140003bc3  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
