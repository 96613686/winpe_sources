# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000b39c`
- end: `0x18000b495`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `249`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b210`

## callees

- `0x180003fa0`
- `0x180003ff4`
- `0x1800067a0`
- `0x18000b39c`
- `0x180018010`

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
0x18000b39c  mov     rax, rsp
0x18000b39f  push    rbx
0x18000b3a0  push    rbp
0x18000b3a1  push    rsi
0x18000b3a2  push    rdi
0x18000b3a3  push    r14
0x18000b3a5  push    r15
0x18000b3a7  sub     rsp, 68h
0x18000b3ab  mov     rdi, [rsp+98h+arg_38]
0x18000b3b3  xor     r15d, r15d
0x18000b3b6  mov     rbx, rcx
0x18000b3b9  mov     [rax+50h], r15b
0x18000b3bd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b3c1  mov     rsi, r9
0x18000b3c4  mov     ebp, r8d
0x18000b3c7  mov     r14, rdx
0x18000b3ca  inc     rcx
0x18000b3cd  cmp     [rdi+rcx*2], r15w
0x18000b3d2  jnz     short loc_18000B3CA
0x18000b3d4  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000b3db  mov     [rbx], r15
0x18000b3de  mov     dword ptr [rbx+8], 1
0x18000b3e5  test    rax, rax
0x18000b3e8  jz      short loc_18000B45D
0x18000b3ea  lea     rdx, [rdi+rcx*2]
0x18000b3ee  mov     r8d, 800h
0x18000b3f4  sub     r8, rcx
0x18000b3f7  lea     r9, [rsp+98h+arg_48]
0x18000b3ff  lea     rcx, [rsp+98h+var_48]
0x18000b404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b409  movsd   xmm0, qword ptr [rax]
0x18000b40d  mov     ecx, [rax+8]
0x18000b410  movsd   qword ptr [rbx], xmm0
0x18000b414  mov     [rbx+8], ecx
0x18000b417  cmp     [rbx], r15d
0x18000b41a  jge     short loc_18000B45D
0x18000b41c  mov     rax, [rsp+98h+arg_30]
0x18000b424  xor     r9d, r9d
0x18000b427  mov     [rsp+98h+var_50], r15d
0x18000b42c  mov     r8, rsi
0x18000b42f  mov     [rsp+98h+var_60], rdi
0x18000b434  mov     edx, ebp
0x18000b436  mov     [rsp+98h+var_68], rbx
0x18000b43b  mov     rcx, r14
0x18000b43e  mov     [rsp+98h+var_70], rax
0x18000b443  mov     [rsp+98h+var_78], r15
0x18000b448  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000b44d  mov     rax, rbx
0x18000b450  add     rsp, 68h
0x18000b454  pop     r15
0x18000b456  pop     r14
0x18000b458  pop     rdi
0x18000b459  pop     rsi
0x18000b45a  pop     rbp
0x18000b45b  pop     rbx
0x18000b45c  retn
0x18000b45d  mov     ecx, 8007023Eh; this
0x18000b462  mov     [rbx], ecx
0x18000b464  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b469  mov     [rbx+4], eax
0x18000b46c  mov     r8, rsi
0x18000b46f  mov     rax, [rsp+98h+arg_30]
0x18000b477  mov     edx, ebp
0x18000b479  mov     [rsp+98h+var_60], rdi
0x18000b47e  mov     rcx, r14
0x18000b481  mov     [rsp+98h+var_68], rbx
0x18000b486  mov     [rsp+98h+var_70], rax
0x18000b48b  mov     [rbx+8], r15d
0x18000b48f  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
