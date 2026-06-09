# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180003b78`
- end: `0x180003c64`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003ae0`

## callees

- `0x180003a4c`
- `0x180003aa8`
- `0x180003b78`
- `0x180006160`
- `0x18001c010`

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
0x180003b78  mov     rax, rsp
0x180003b7b  push    rbx
0x180003b7c  push    rbp
0x180003b7d  push    rsi
0x180003b7e  push    rdi
0x180003b7f  push    r14
0x180003b81  push    r15
0x180003b83  sub     rsp, 68h
0x180003b87  mov     rdi, [rsp+98h+arg_38]
0x180003b8f  xor     r15d, r15d
0x180003b92  mov     rbx, rcx
0x180003b95  mov     [rax+50h], r15b
0x180003b99  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003b9d  mov     rsi, r9
0x180003ba0  mov     ebp, r8d
0x180003ba3  mov     r14, rdx
0x180003ba6  inc     rcx
0x180003ba9  cmp     [rdi+rcx*2], r15w
0x180003bae  jnz     short loc_180003BA6
0x180003bb0  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180003bb7  mov     [rbx], r15
0x180003bba  mov     dword ptr [rbx+8], 1
0x180003bc1  test    rax, rax
0x180003bc4  jz      short loc_180003C2C
0x180003bc6  lea     rdx, [rdi+rcx*2]
0x180003bca  mov     r8d, 800h
0x180003bd0  sub     r8, rcx
0x180003bd3  lea     r9, [rsp+98h+arg_48]
0x180003bdb  lea     rcx, [rsp+98h+var_48]
0x180003be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003be5  movsd   xmm0, qword ptr [rax]
0x180003be9  mov     ecx, [rax+8]
0x180003bec  movsd   qword ptr [rbx], xmm0
0x180003bf0  mov     [rbx+8], ecx
0x180003bf3  cmp     [rbx], r15d
0x180003bf6  jge     short loc_180003C2C
0x180003bf8  mov     rax, [rsp+98h+arg_30]
0x180003c00  mov     r8, rsi
0x180003c03  mov     [rsp+98h+var_60], rdi
0x180003c08  mov     edx, ebp
0x180003c0a  mov     [rsp+98h+var_68], rbx
0x180003c0f  mov     rcx, r14
0x180003c12  mov     [rsp+98h+var_70], rax
0x180003c17  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180003c1c  mov     rax, rbx
0x180003c1f  add     rsp, 68h
0x180003c23  pop     r15
0x180003c25  pop     r14
0x180003c27  pop     rdi
0x180003c28  pop     rsi
0x180003c29  pop     rbp
0x180003c2a  pop     rbx
0x180003c2b  retn
0x180003c2c  mov     ecx, 8007023Eh; this
0x180003c31  mov     [rbx], ecx
0x180003c33  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003c38  mov     [rbx+4], eax
0x180003c3b  mov     r8, rsi
0x180003c3e  mov     rax, [rsp+98h+arg_30]
0x180003c46  mov     edx, ebp
0x180003c48  mov     [rsp+98h+var_60], rdi
0x180003c4d  mov     rcx, r14
0x180003c50  mov     [rsp+98h+var_68], rbx
0x180003c55  mov     [rsp+98h+var_70], rax
0x180003c5a  mov     [rbx+8], r15d
0x180003c5e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
