# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180007eb0`
- end: `0x180007f9c`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int64, __int64, int, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007e18`
- `0x180007fa4`

## callees

- `0x18000274c`
- `0x1800027ac`
- `0x1800049b8`
- `0x180007eb0`
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
0x180007eb0  mov     rax, rsp
0x180007eb3  push    rbx
0x180007eb4  push    rbp
0x180007eb5  push    rsi
0x180007eb6  push    rdi
0x180007eb7  push    r14
0x180007eb9  push    r15
0x180007ebb  sub     rsp, 68h
0x180007ebf  mov     rdi, [rsp+98h+arg_38]
0x180007ec7  xor     r15d, r15d
0x180007eca  mov     rbx, rcx
0x180007ecd  mov     [rax+50h], r15b
0x180007ed1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007ed5  mov     rsi, r9
0x180007ed8  mov     ebp, r8d
0x180007edb  mov     r14, rdx
0x180007ede  inc     rcx
0x180007ee1  cmp     [rdi+rcx*2], r15w
0x180007ee6  jnz     short loc_180007EDE
0x180007ee8  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180007eef  mov     [rbx], r15
0x180007ef2  mov     dword ptr [rbx+8], 1
0x180007ef9  test    rax, rax
0x180007efc  jz      short loc_180007F64
0x180007efe  lea     rdx, [rdi+rcx*2]
0x180007f02  mov     r8d, 800h
0x180007f08  sub     r8, rcx
0x180007f0b  lea     r9, [rsp+98h+arg_48]
0x180007f13  lea     rcx, [rsp+98h+var_48]
0x180007f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f1d  movsd   xmm0, qword ptr [rax]
0x180007f21  mov     ecx, [rax+8]
0x180007f24  movsd   qword ptr [rbx], xmm0
0x180007f28  mov     [rbx+8], ecx
0x180007f2b  cmp     [rbx], r15d
0x180007f2e  jge     short loc_180007F64
0x180007f30  mov     rax, [rsp+98h+arg_30]
0x180007f38  mov     r8, rsi
0x180007f3b  mov     [rsp+98h+var_60], rdi
0x180007f40  mov     edx, ebp
0x180007f42  mov     [rsp+98h+var_68], rbx
0x180007f47  mov     rcx, r14
0x180007f4a  mov     [rsp+98h+var_70], rax
0x180007f4f  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180007f54  mov     rax, rbx
0x180007f57  add     rsp, 68h
0x180007f5b  pop     r15
0x180007f5d  pop     r14
0x180007f5f  pop     rdi
0x180007f60  pop     rsi
0x180007f61  pop     rbp
0x180007f62  pop     rbx
0x180007f63  retn
0x180007f64  mov     ecx, 8007023Eh; this
0x180007f69  mov     [rbx], ecx
0x180007f6b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007f70  mov     [rbx+4], eax
0x180007f73  mov     r8, rsi
0x180007f76  mov     rax, [rsp+98h+arg_30]
0x180007f7e  mov     edx, ebp
0x180007f80  mov     [rsp+98h+var_60], rdi
0x180007f85  mov     rcx, r14
0x180007f88  mov     [rsp+98h+var_68], rbx
0x180007f8d  mov     [rsp+98h+var_70], rax
0x180007f92  mov     [rbx+8], r15d
0x180007f96  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
