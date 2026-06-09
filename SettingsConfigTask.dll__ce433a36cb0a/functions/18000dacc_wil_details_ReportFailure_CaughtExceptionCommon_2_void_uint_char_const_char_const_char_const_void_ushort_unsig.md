# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000dacc`
- end: `0x18000dbc5`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `249`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d940`

## callees

- `0x1800038b4`
- `0x180003908`
- `0x180006f24`
- `0x18000dacc`
- `0x180024010`

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
0x18000dacc  mov     rax, rsp
0x18000dacf  push    rbx
0x18000dad0  push    rbp
0x18000dad1  push    rsi
0x18000dad2  push    rdi
0x18000dad3  push    r14
0x18000dad5  push    r15
0x18000dad7  sub     rsp, 68h
0x18000dadb  mov     rdi, [rsp+98h+arg_38]
0x18000dae3  xor     r15d, r15d
0x18000dae6  mov     rbx, rcx
0x18000dae9  mov     [rax+50h], r15b
0x18000daed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000daf1  mov     rsi, r9
0x18000daf4  mov     ebp, r8d
0x18000daf7  mov     r14, rdx
0x18000dafa  inc     rcx
0x18000dafd  cmp     [rdi+rcx*2], r15w
0x18000db02  jnz     short loc_18000DAFA
0x18000db04  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000db0b  mov     [rbx], r15
0x18000db0e  mov     dword ptr [rbx+8], 1
0x18000db15  test    rax, rax
0x18000db18  jz      short loc_18000DB8D
0x18000db1a  lea     rdx, [rdi+rcx*2]
0x18000db1e  mov     r8d, 800h
0x18000db24  sub     r8, rcx
0x18000db27  lea     r9, [rsp+98h+arg_48]
0x18000db2f  lea     rcx, [rsp+98h+var_48]
0x18000db34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db39  movsd   xmm0, qword ptr [rax]
0x18000db3d  mov     ecx, [rax+8]
0x18000db40  movsd   qword ptr [rbx], xmm0
0x18000db44  mov     [rbx+8], ecx
0x18000db47  cmp     [rbx], r15d
0x18000db4a  jge     short loc_18000DB8D
0x18000db4c  mov     rax, [rsp+98h+arg_30]
0x18000db54  xor     r9d, r9d
0x18000db57  mov     [rsp+98h+var_50], r15d
0x18000db5c  mov     r8, rsi
0x18000db5f  mov     [rsp+98h+var_60], rdi
0x18000db64  mov     edx, ebp
0x18000db66  mov     [rsp+98h+var_68], rbx
0x18000db6b  mov     rcx, r14
0x18000db6e  mov     [rsp+98h+var_70], rax
0x18000db73  mov     [rsp+98h+var_78], r15
0x18000db78  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000db7d  mov     rax, rbx
0x18000db80  add     rsp, 68h
0x18000db84  pop     r15
0x18000db86  pop     r14
0x18000db88  pop     rdi
0x18000db89  pop     rsi
0x18000db8a  pop     rbp
0x18000db8b  pop     rbx
0x18000db8c  retn
0x18000db8d  mov     ecx, 8007023Eh; this
0x18000db92  mov     [rbx], ecx
0x18000db94  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000db99  mov     [rbx+4], eax
0x18000db9c  mov     r8, rsi
0x18000db9f  mov     rax, [rsp+98h+arg_30]
0x18000dba7  mov     edx, ebp
0x18000dba9  mov     [rsp+98h+var_60], rdi
0x18000dbae  mov     rcx, r14
0x18000dbb1  mov     [rsp+98h+var_68], rbx
0x18000dbb6  mov     [rsp+98h+var_70], rax
0x18000dbbb  mov     [rbx+8], r15d
0x18000dbbf  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
