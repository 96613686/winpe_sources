# wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x1800077ec`
- end: `0x18000793a`
- name: `??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `334`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x180009b38`

## callees

- `0x180002bc0`
- `0x18000354c`
- `0x180003804`
- `0x180003858`
- `0x180005800`
- `0x1800077ec`
- `0x180010ba0`
- `0x180012010`

## string_xrefs

- `0x1800078ad`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x180007909`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<2>(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rax
  int v11; // r9d
  _BYTE v12[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v13; // [rsp+58h] [rbp-A8h] BYREF
  int v14; // [rsp+60h] [rbp-A0h]
  _BYTE v15[24]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v16[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v16, 0, sizeof(v16));
  v12[0] = 0;
  v8 = -1;
  do
    ++v8;
  while ( v16[v8] );
  v13 = 0;
  v14 = 1;
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v9 = g_pfnResultFromCaughtExceptionInternal(v15, &v16[v8], 2048 - v8, v12),
        v13 = *(_QWORD *)v9,
        v14 = *(_DWORD *)(v9 + 8),
        _mm_cvtsi128_si32((__m128i)v13) >= 0) )
  {
    LODWORD(v13) = -2147024322;
    HIDWORD(v13) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v7);
    v14 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      299,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      v11);
  }
  wil::details::ReportFailure_Base<2,0>(
    a1,
    299,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
    0,
    0,
    a6,
    (__int64)&v13,
    (__int64)v16);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800077ec  push    rbp
0x1800077ee  push    rbx
0x1800077ef  push    rsi
0x1800077f0  push    rdi
0x1800077f1  lea     rbp, [rsp-0F98h]
0x1800077f9  mov     eax, 1098h
0x1800077fe  call    _alloca_probe
0x180007803  sub     rsp, rax
0x180007806  mov     rax, cs:__security_cookie
0x18000780d  xor     rax, rsp
0x180007810  mov     [rbp+0FB0h+var_30], rax
0x180007817  mov     rdi, [rbp+0FB0h+arg_28]
0x18000781e  mov     rbx, rcx
0x180007821  lea     rcx, [rbp+0FB0h+var_1030]; void *
0x180007825  xor     edx, edx; Val
0x180007827  mov     r8d, 1000h; Size
0x18000782d  call    memset_0
0x180007832  xor     esi, esi
0x180007834  lea     rax, [rbp+0FB0h+var_1030]
0x180007838  mov     [rsp+10B0h+var_1060], sil
0x18000783d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007841  inc     rcx
0x180007844  cmp     [rax+rcx*2], si
0x180007848  jnz     short loc_180007841
0x18000784a  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180007851  mov     [rsp+10B0h+var_1058], rsi
0x180007856  mov     [rsp+10B0h+var_1050], 1
0x18000785e  test    rax, rax
0x180007861  jz      loc_1800078F7
0x180007867  mov     r8d, 800h
0x18000786d  lea     rdx, [rbp+0FB0h+var_1030]
0x180007871  sub     r8, rcx
0x180007874  lea     rdx, [rdx+rcx*2]
0x180007878  lea     rcx, [rsp+10B0h+var_1048]
0x18000787d  lea     r9, [rsp+10B0h+var_1060]
0x180007882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007887  movsd   xmm0, qword ptr [rax]
0x18000788b  movsd   [rsp+10B0h+var_1058], xmm0
0x180007891  mov     eax, [rax+8]
0x180007894  mov     [rsp+10B0h+var_1050], eax
0x180007898  movd    eax, xmm0
0x18000789c  test    eax, eax
0x18000789e  jns     short loc_1800078F7
0x1800078a0  mov     [rsp+10B0h+var_1068], esi
0x1800078a4  lea     rax, [rbp+0FB0h+var_1030]
0x1800078a8  mov     [rsp+10B0h+var_1078], rax
0x1800078ad  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800078b4  lea     rax, [rsp+10B0h+var_1058]
0x1800078b9  xor     r9d, r9d
0x1800078bc  mov     [rsp+10B0h+var_1080], rax
0x1800078c1  mov     edx, 12Bh
0x1800078c6  mov     [rsp+10B0h+var_1088], rdi
0x1800078cb  mov     rcx, rbx
0x1800078ce  mov     [rsp+10B0h+var_1090], rsi
0x1800078d3  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800078d8  mov     eax, dword ptr [rsp+10B0h+var_1058]
0x1800078dc  mov     rcx, [rbp+0FB0h+var_30]
0x1800078e3  xor     rcx, rsp; StackCookie
0x1800078e6  call    __security_check_cookie
0x1800078eb  add     rsp, 1098h
0x1800078f2  pop     rdi
0x1800078f3  pop     rsi
0x1800078f4  pop     rbx
0x1800078f5  pop     rbp
0x1800078f6  retn
0x1800078f7  mov     ecx, 8007023Eh; this
0x1800078fc  mov     dword ptr [rsp+10B0h+var_1058], ecx
0x180007900  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007905  mov     dword ptr [rsp+10B0h+var_1058+4], eax
0x180007909  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007910  lea     rax, [rbp+0FB0h+var_1030]
0x180007914  mov     [rsp+10B0h+var_1050], esi
0x180007918  mov     [rsp+10B0h+var_1078], rax
0x18000791d  mov     edx, 12Bh
0x180007922  lea     rax, [rsp+10B0h+var_1058]
0x180007927  mov     rcx, rbx
0x18000792a  mov     [rsp+10B0h+var_1080], rax
0x18000792f  mov     [rsp+10B0h+var_1088], rdi
0x180007934  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
