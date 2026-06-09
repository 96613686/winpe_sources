# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000ec34`
- end: `0x18000ed2d`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `249`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int64, __int64, int, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ed34`
- `0x180013604`

## callees

- `0x18000370c`
- `0x180004674`
- `0x1800046c8`
- `0x18000ec34`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<2>(
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
0x18000ec34  mov     rax, rsp
0x18000ec37  push    rbx
0x18000ec38  push    rbp
0x18000ec39  push    rsi
0x18000ec3a  push    rdi
0x18000ec3b  push    r14
0x18000ec3d  push    r15
0x18000ec3f  sub     rsp, 68h
0x18000ec43  mov     rdi, [rsp+98h+arg_38]
0x18000ec4b  xor     r15d, r15d
0x18000ec4e  mov     rbx, rcx
0x18000ec51  mov     [rax+50h], r15b
0x18000ec55  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ec59  mov     rsi, r9
0x18000ec5c  mov     ebp, r8d
0x18000ec5f  mov     r14, rdx
0x18000ec62  inc     rcx
0x18000ec65  cmp     [rdi+rcx*2], r15w
0x18000ec6a  jnz     short loc_18000EC62
0x18000ec6c  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000ec73  mov     [rbx], r15
0x18000ec76  mov     dword ptr [rbx+8], 1
0x18000ec7d  test    rax, rax
0x18000ec80  jz      short loc_18000ECF5
0x18000ec82  lea     rdx, [rdi+rcx*2]
0x18000ec86  mov     r8d, 800h
0x18000ec8c  sub     r8, rcx
0x18000ec8f  lea     r9, [rsp+98h+arg_48]
0x18000ec97  lea     rcx, [rsp+98h+var_48]
0x18000ec9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eca1  movsd   xmm0, qword ptr [rax]
0x18000eca5  mov     ecx, [rax+8]
0x18000eca8  movsd   qword ptr [rbx], xmm0
0x18000ecac  mov     [rbx+8], ecx
0x18000ecaf  cmp     [rbx], r15d
0x18000ecb2  jge     short loc_18000ECF5
0x18000ecb4  mov     rax, [rsp+98h+arg_30]
0x18000ecbc  xor     r9d, r9d
0x18000ecbf  mov     [rsp+98h+var_50], r15d
0x18000ecc4  mov     r8, rsi
0x18000ecc7  mov     [rsp+98h+var_60], rdi
0x18000eccc  mov     edx, ebp
0x18000ecce  mov     [rsp+98h+var_68], rbx
0x18000ecd3  mov     rcx, r14
0x18000ecd6  mov     [rsp+98h+var_70], rax
0x18000ecdb  mov     [rsp+98h+var_78], r15
0x18000ece0  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000ece5  mov     rax, rbx
0x18000ece8  add     rsp, 68h
0x18000ecec  pop     r15
0x18000ecee  pop     r14
0x18000ecf0  pop     rdi
0x18000ecf1  pop     rsi
0x18000ecf2  pop     rbp
0x18000ecf3  pop     rbx
0x18000ecf4  retn
0x18000ecf5  mov     ecx, 8007023Eh; this
0x18000ecfa  mov     [rbx], ecx
0x18000ecfc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ed01  mov     [rbx+4], eax
0x18000ed04  mov     r8, rsi
0x18000ed07  mov     rax, [rsp+98h+arg_30]
0x18000ed0f  mov     edx, ebp
0x18000ed11  mov     [rsp+98h+var_60], rdi
0x18000ed16  mov     rcx, r14
0x18000ed19  mov     [rsp+98h+var_68], rbx
0x18000ed1e  mov     [rsp+98h+var_70], rax
0x18000ed23  mov     [rbx+8], r15d
0x18000ed27  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
