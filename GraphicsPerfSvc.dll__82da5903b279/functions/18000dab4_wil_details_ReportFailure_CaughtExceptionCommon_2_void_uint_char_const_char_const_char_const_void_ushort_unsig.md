# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000dab4`
- end: `0x18000dbad`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `249`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64, __int64, __int64, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000dbb4`
- `0x18002629c`

## callees

- `0x180004e04`
- `0x180004e58`
- `0x1800074c8`
- `0x18000dab4`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<2>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
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
  wil::details::ReportFailure_Base<2,0>(a2, a3, a4, 0, 0, a7, a1, a8);
  return a1;
}

```

## disassembly

```asm
0x18000dab4  mov     rax, rsp
0x18000dab7  push    rbx
0x18000dab8  push    rbp
0x18000dab9  push    rsi
0x18000daba  push    rdi
0x18000dabb  push    r14
0x18000dabd  push    r15
0x18000dabf  sub     rsp, 68h
0x18000dac3  mov     rdi, [rsp+98h+arg_38]
0x18000dacb  xor     r15d, r15d
0x18000dace  mov     rbx, rcx
0x18000dad1  mov     [rax+50h], r15b
0x18000dad5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000dad9  mov     rsi, r9
0x18000dadc  mov     ebp, r8d
0x18000dadf  mov     r14, rdx
0x18000dae2  inc     rcx
0x18000dae5  cmp     [rdi+rcx*2], r15w
0x18000daea  jnz     short loc_18000DAE2
0x18000daec  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000daf3  mov     [rbx], r15
0x18000daf6  mov     dword ptr [rbx+8], 1
0x18000dafd  test    rax, rax
0x18000db00  jz      short loc_18000DB75
0x18000db02  lea     rdx, [rdi+rcx*2]
0x18000db06  mov     r8d, 800h
0x18000db0c  sub     r8, rcx
0x18000db0f  lea     r9, [rsp+98h+arg_48]
0x18000db17  lea     rcx, [rsp+98h+var_48]
0x18000db1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db21  movsd   xmm0, qword ptr [rax]
0x18000db25  mov     ecx, [rax+8]
0x18000db28  movsd   qword ptr [rbx], xmm0
0x18000db2c  mov     [rbx+8], ecx
0x18000db2f  cmp     [rbx], r15d
0x18000db32  jge     short loc_18000DB75
0x18000db34  mov     rax, [rsp+98h+arg_30]
0x18000db3c  xor     r9d, r9d
0x18000db3f  mov     [rsp+98h+var_50], r15d
0x18000db44  mov     r8, rsi
0x18000db47  mov     [rsp+98h+var_60], rdi
0x18000db4c  mov     edx, ebp
0x18000db4e  mov     [rsp+98h+var_68], rbx
0x18000db53  mov     rcx, r14
0x18000db56  mov     [rsp+98h+var_70], rax
0x18000db5b  mov     [rsp+98h+var_78], r15
0x18000db60  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000db65  mov     rax, rbx
0x18000db68  add     rsp, 68h
0x18000db6c  pop     r15
0x18000db6e  pop     r14
0x18000db70  pop     rdi
0x18000db71  pop     rsi
0x18000db72  pop     rbp
0x18000db73  pop     rbx
0x18000db74  retn
0x18000db75  mov     ecx, 8007023Eh; this
0x18000db7a  mov     [rbx], ecx
0x18000db7c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000db81  mov     [rbx+4], eax
0x18000db84  mov     r8, rsi
0x18000db87  mov     rax, [rsp+98h+arg_30]
0x18000db8f  mov     edx, ebp
0x18000db91  mov     [rsp+98h+var_60], rdi
0x18000db96  mov     rcx, r14
0x18000db99  mov     [rsp+98h+var_68], rbx
0x18000db9e  mov     [rsp+98h+var_70], rax
0x18000dba3  mov     [rbx+8], r15d
0x18000dba7  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
