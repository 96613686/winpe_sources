# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,wchar_t *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000fcdc`
- end: `0x18000fdfe`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEA_W_KW4SupportedExceptions@1@@Z`
- size: `290`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int64, __int64, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000fb48`
- `0x18001fb88`

## callees

- `0x18000441c`
- `0x180004470`
- `0x180005f94`
- `0x18000fcdc`
- `0x180031010`

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
        int a10)
{
  __int64 v10; // rdi
  __int64 v12; // rcx
  __int64 (__fastcall *v16)(_BYTE *, __int64, __int64, char *); // rax
  char v17; // si
  __int64 v18; // rax
  int v19; // r9d
  int v20; // ecx
  _BYTE v22[16]; // [rsp+50h] [rbp-38h] BYREF
  char v23; // [rsp+90h] [rbp+8h] BYREF

  v10 = a8;
  v23 = 0;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(a8 + 2 * v12) );
  v16 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  v17 = 1;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v16
    || (v18 = v16(v22, v10 + 2 * v12, 2048 - v12, &v23),
        v20 = *(_DWORD *)(v18 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v18,
        *(_DWORD *)(a1 + 8) = v20,
        *(int *)a1 >= 0) )
  {
    v17 = 0;
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
  }
  if ( !a10 && !v17 )
    wil::details::ReportFailure_Base<3,0>(a2, a3, a4, v19);
  wil::details::ReportFailure_Base<2,0>(a2, a3, a4, 0, 0, a7, a1, v10);
  return a1;
}

```

## disassembly

```asm
0x18000fcdc  mov     rax, rsp
0x18000fcdf  mov     [rax+10h], rbx
0x18000fce3  mov     [rax+18h], rbp
0x18000fce7  push    rsi
0x18000fce8  push    rdi
0x18000fce9  push    r12
0x18000fceb  push    r14
0x18000fced  push    r15
0x18000fcef  sub     rsp, 60h
0x18000fcf3  mov     rdi, [rsp+88h+arg_38]
0x18000fcfb  xor     r12d, r12d
0x18000fcfe  mov     rbx, rcx
0x18000fd01  mov     [rax+8], r12b
0x18000fd05  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000fd09  mov     rbp, r9
0x18000fd0c  mov     r14d, r8d
0x18000fd0f  mov     r15, rdx
0x18000fd12  inc     rcx
0x18000fd15  cmp     [rdi+rcx*2], r12w
0x18000fd1a  jnz     short loc_18000FD12
0x18000fd1c  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000fd23  mov     esi, 1
0x18000fd28  mov     [rbx], r12
0x18000fd2b  mov     [rbx+8], esi
0x18000fd2e  test    rax, rax
0x18000fd31  jz      short loc_18000FD65
0x18000fd33  lea     rdx, [rdi+rcx*2]
0x18000fd37  mov     r8d, 800h
0x18000fd3d  sub     r8, rcx
0x18000fd40  lea     r9, [rsp+88h+arg_0]
0x18000fd48  lea     rcx, [rsp+88h+var_38]
0x18000fd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd52  movsd   xmm0, qword ptr [rax]
0x18000fd56  mov     ecx, [rax+8]
0x18000fd59  movsd   qword ptr [rbx], xmm0
0x18000fd5d  mov     [rbx+8], ecx
0x18000fd60  cmp     [rbx], r12d
0x18000fd63  jl      short loc_18000FD7B
0x18000fd65  mov     ecx, 8007023Eh; this
0x18000fd6a  mov     sil, r12b
0x18000fd6d  mov     [rbx], ecx
0x18000fd6f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fd74  mov     [rbx+4], eax
0x18000fd77  mov     [rbx+8], r12d
0x18000fd7b  cmp     [rsp+88h+arg_48], r12d
0x18000fd83  jnz     short loc_18000FDB0
0x18000fd85  test    sil, sil
0x18000fd88  jnz     short loc_18000FDB0
0x18000fd8a  mov     rax, [rsp+88h+arg_30]
0x18000fd92  mov     r8, rbp
0x18000fd95  mov     [rsp+88h+var_50], rdi
0x18000fd9a  mov     edx, r14d
0x18000fd9d  mov     [rsp+88h+var_58], rbx
0x18000fda2  mov     rcx, r15
0x18000fda5  mov     [rsp+88h+var_60], rax
0x18000fdaa  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fdb0  mov     rax, [rsp+88h+arg_30]
0x18000fdb8  xor     r9d, r9d
0x18000fdbb  mov     [rsp+88h+var_40], r12d
0x18000fdc0  mov     r8, rbp
0x18000fdc3  mov     [rsp+88h+var_50], rdi
0x18000fdc8  mov     edx, r14d
0x18000fdcb  mov     [rsp+88h+var_58], rbx
0x18000fdd0  mov     rcx, r15
0x18000fdd3  mov     [rsp+88h+var_60], rax
0x18000fdd8  mov     [rsp+88h+var_68], r12
0x18000fddd  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fde2  lea     r11, [rsp+88h+var_28]
0x18000fde7  mov     rax, rbx
0x18000fdea  mov     rbx, [r11+38h]
0x18000fdee  mov     rbp, [r11+40h]
0x18000fdf2  mov     rsp, r11
0x18000fdf5  pop     r15
0x18000fdf7  pop     r14
0x18000fdf9  pop     r12
0x18000fdfb  pop     rdi
0x18000fdfc  pop     rsi
0x18000fdfd  retn
```
