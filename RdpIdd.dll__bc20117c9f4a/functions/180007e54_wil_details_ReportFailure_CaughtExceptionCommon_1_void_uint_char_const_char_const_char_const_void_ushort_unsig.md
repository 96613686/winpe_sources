# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180007e54`
- end: `0x180007f41`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `237`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007dbc`
- `0x18000c980`
- `0x180031a58`
- `0x180031b78`

## callees

- `0x180007d24`
- `0x180007d84`
- `0x180007e54`
- `0x18000a2d8`
- `0x18003f010`

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
0x180007e54  mov     rax, rsp
0x180007e57  push    rbx
0x180007e58  push    rbp
0x180007e59  push    rsi
0x180007e5a  push    rdi
0x180007e5b  push    r14
0x180007e5d  push    r15
0x180007e5f  sub     rsp, 68h
0x180007e63  mov     rdi, [rsp+98h+arg_38]
0x180007e6b  xor     r15d, r15d
0x180007e6e  mov     rbx, rcx
0x180007e71  mov     [rax+50h], r15b
0x180007e75  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007e79  mov     rsi, r9
0x180007e7c  mov     ebp, r8d
0x180007e7f  mov     r14, rdx
0x180007e82  inc     rcx
0x180007e85  cmp     [rdi+rcx*2], r15w
0x180007e8a  jnz     short loc_180007E82
0x180007e8c  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180007e93  mov     [rbx], r15
0x180007e96  mov     dword ptr [rbx+8], 1
0x180007e9d  test    rax, rax
0x180007ea0  jz      short loc_180007F09
0x180007ea2  lea     rdx, [rdi+rcx*2]
0x180007ea6  mov     r8d, 800h
0x180007eac  sub     r8, rcx
0x180007eaf  lea     r9, [rsp+98h+arg_48]
0x180007eb7  lea     rcx, [rsp+98h+var_48]
0x180007ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ec1  movsd   xmm0, qword ptr [rax]
0x180007ec5  mov     ecx, [rax+8]
0x180007ec8  movsd   qword ptr [rbx], xmm0
0x180007ecc  mov     [rbx+8], ecx
0x180007ecf  cmp     [rbx], r15d
0x180007ed2  jge     short loc_180007F09
0x180007ed4  mov     rax, [rsp+98h+arg_30]
0x180007edc  mov     r8, rsi
0x180007edf  mov     [rsp+98h+var_60], rdi
0x180007ee4  mov     edx, ebp
0x180007ee6  mov     [rsp+98h+var_68], rbx
0x180007eeb  mov     rcx, r14
0x180007eee  mov     [rsp+98h+var_70], rax
0x180007ef3  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180007ef8  mov     rax, rbx
0x180007efb  add     rsp, 68h
0x180007eff  pop     r15
0x180007f01  pop     r14
0x180007f03  pop     rdi
0x180007f04  pop     rsi
0x180007f05  pop     rbp
0x180007f06  pop     rbx
0x180007f07  retn
0x180007f09  mov     ecx, 8007023Eh; this
0x180007f0e  mov     [rbx], ecx
0x180007f10  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007f15  mov     [rbx+4], eax
0x180007f18  mov     r8, rsi
0x180007f1b  mov     rax, [rsp+98h+arg_30]
0x180007f23  mov     edx, ebp
0x180007f25  mov     [rsp+98h+var_60], rdi
0x180007f2a  mov     rcx, r14
0x180007f2d  mov     [rsp+98h+var_68], rbx
0x180007f32  mov     [rsp+98h+var_70], rax
0x180007f37  mov     [rbx+8], r15d
0x180007f3b  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
