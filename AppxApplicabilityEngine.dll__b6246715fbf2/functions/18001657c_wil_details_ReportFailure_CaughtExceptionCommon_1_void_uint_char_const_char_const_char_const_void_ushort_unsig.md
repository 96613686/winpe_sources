# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18001657c`
- end: `0x180016668`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800164e4`

## callees

- `0x18000c030`
- `0x1800108d4`
- `0x180013924`
- `0x18001657c`
- `0x180025010`

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
0x18001657c  mov     rax, rsp
0x18001657f  push    rbx
0x180016580  push    rbp
0x180016581  push    rsi
0x180016582  push    rdi
0x180016583  push    r14
0x180016585  push    r15
0x180016587  sub     rsp, 68h
0x18001658b  mov     rdi, [rsp+98h+arg_38]
0x180016593  xor     r15d, r15d
0x180016596  mov     rbx, rcx
0x180016599  mov     [rax+50h], r15b
0x18001659d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800165a1  mov     rsi, r9
0x1800165a4  mov     ebp, r8d
0x1800165a7  mov     r14, rdx
0x1800165aa  inc     rcx
0x1800165ad  cmp     [rdi+rcx*2], r15w
0x1800165b2  jnz     short loc_1800165AA
0x1800165b4  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1800165bb  mov     [rbx], r15
0x1800165be  mov     dword ptr [rbx+8], 1
0x1800165c5  test    rax, rax
0x1800165c8  jz      short loc_180016630
0x1800165ca  lea     rdx, [rdi+rcx*2]
0x1800165ce  mov     r8d, 800h
0x1800165d4  sub     r8, rcx
0x1800165d7  lea     r9, [rsp+98h+arg_48]
0x1800165df  lea     rcx, [rsp+98h+var_48]
0x1800165e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165e9  movsd   xmm0, qword ptr [rax]
0x1800165ed  mov     ecx, [rax+8]
0x1800165f0  movsd   qword ptr [rbx], xmm0
0x1800165f4  mov     [rbx+8], ecx
0x1800165f7  cmp     [rbx], r15d
0x1800165fa  jge     short loc_180016630
0x1800165fc  mov     rax, [rsp+98h+arg_30]
0x180016604  mov     r8, rsi
0x180016607  mov     [rsp+98h+var_60], rdi
0x18001660c  mov     edx, ebp
0x18001660e  mov     [rsp+98h+var_68], rbx
0x180016613  mov     rcx, r14
0x180016616  mov     [rsp+98h+var_70], rax
0x18001661b  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180016620  mov     rax, rbx
0x180016623  add     rsp, 68h
0x180016627  pop     r15
0x180016629  pop     r14
0x18001662b  pop     rdi
0x18001662c  pop     rsi
0x18001662d  pop     rbp
0x18001662e  pop     rbx
0x18001662f  retn
0x180016630  mov     ecx, 8007023Eh; this
0x180016635  mov     [rbx], ecx
0x180016637  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001663c  mov     [rbx+4], eax
0x18001663f  mov     r8, rsi
0x180016642  mov     rax, [rsp+98h+arg_30]
0x18001664a  mov     edx, ebp
0x18001664c  mov     [rsp+98h+var_60], rdi
0x180016651  mov     rcx, r14
0x180016654  mov     [rsp+98h+var_68], rbx
0x180016659  mov     [rsp+98h+var_70], rax
0x18001665e  mov     [rbx+8], r15d
0x180016662  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
