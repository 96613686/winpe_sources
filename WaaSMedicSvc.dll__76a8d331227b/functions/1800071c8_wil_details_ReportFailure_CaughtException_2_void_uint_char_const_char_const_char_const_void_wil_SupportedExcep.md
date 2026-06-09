# wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x1800071c8`
- end: `0x18000732b`
- name: `??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `355`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a2cc`

## callees

- `0x180002200`
- `0x180002f7c`
- `0x180003018`
- `0x18000306c`
- `0x180004ebc`
- `0x1800071c8`
- `0x18000bd40`
- `0x18000d010`

## string_xrefs

- `0x180007297`: `onecore\enduser\windowsupdate\undocked\stubdlls\dllexports.cpp`
- `0x1800072fc`: `onecore\enduser\windowsupdate\undocked\stubdlls\dllexports.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v8; // edx
  __int64 v9; // rcx
  __int64 v10; // rax
  int v12; // r9d
  int v13; // [rsp+20h] [rbp-E0h]
  _BYTE v14[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v15; // [rsp+58h] [rbp-A8h] BYREF
  int v16; // [rsp+60h] [rbp-A0h]
  _BYTE v17[24]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v18[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v18, 0, sizeof(v18));
  v14[0] = 0;
  v9 = -1;
  do
    ++v9;
  while ( v18[v9] );
  v15 = 0;
  v16 = 1;
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v10 = g_pfnResultFromCaughtExceptionInternal(v17, &v18[v9], 2048 - v9, v14),
        v15 = *(_QWORD *)v10,
        v16 = *(_DWORD *)(v10 + 8),
        _mm_cvtsi128_si32((__m128i)v15) >= 0) )
  {
    LODWORD(v15) = -2147024322;
    HIDWORD(v15) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v8);
    v16 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      a2,
      (int)"onecore\\enduser\\windowsupdate\\undocked\\stubdlls\\dllexports.cpp",
      v12,
      v13,
      a6,
      (__int64)&v15,
      (__int64)v18);
  }
  wil::details::ReportFailure_Base<2,0>(
    a1,
    a2,
    (unsigned int)"onecore\\enduser\\windowsupdate\\undocked\\stubdlls\\dllexports.cpp",
    0,
    0,
    a6,
    (__int64)&v15,
    (__int64)v18);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800071c8  mov     [rsp-8+arg_10], rbx
0x1800071cd  mov     [rsp-8+arg_18], rsi
0x1800071d2  push    rbp
0x1800071d3  push    rdi
0x1800071d4  push    r14
0x1800071d6  lea     rbp, [rsp-0F90h]
0x1800071de  mov     eax, 1090h
0x1800071e3  call    _alloca_probe
0x1800071e8  sub     rsp, rax
0x1800071eb  mov     rax, cs:__security_cookie
0x1800071f2  xor     rax, rsp
0x1800071f5  mov     [rbp+0FA0h+var_20], rax
0x1800071fc  mov     rsi, [rbp+0FA0h+arg_28]
0x180007203  mov     edi, edx
0x180007205  mov     rbx, rcx
0x180007208  xor     edx, edx; Val
0x18000720a  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x18000720e  mov     r8d, 1000h; Size
0x180007214  call    memset_0
0x180007219  xor     r14d, r14d
0x18000721c  lea     rax, [rbp+0FA0h+var_1020]
0x180007220  mov     [rsp+10A0h+var_1050], r14b
0x180007225  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007229  inc     rcx
0x18000722c  cmp     [rax+rcx*2], r14w
0x180007231  jnz     short loc_180007229
0x180007233  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000723a  mov     [rsp+10A0h+var_1048], r14
0x18000723f  mov     [rsp+10A0h+var_1040], 1
0x180007247  test    rax, rax
0x18000724a  jz      loc_1800072EA
0x180007250  mov     r8d, 800h
0x180007256  lea     rdx, [rbp+0FA0h+var_1020]
0x18000725a  sub     r8, rcx
0x18000725d  lea     rdx, [rdx+rcx*2]
0x180007261  lea     rcx, [rsp+10A0h+var_1038]
0x180007266  lea     r9, [rsp+10A0h+var_1050]
0x18000726b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007270  movsd   xmm0, qword ptr [rax]
0x180007274  movsd   [rsp+10A0h+var_1048], xmm0
0x18000727a  mov     eax, [rax+8]
0x18000727d  mov     [rsp+10A0h+var_1040], eax
0x180007281  movd    eax, xmm0
0x180007285  test    eax, eax
0x180007287  jns     short loc_1800072EA
0x180007289  mov     [rsp+10A0h+var_1058], r14d
0x18000728e  lea     rax, [rbp+0FA0h+var_1020]
0x180007292  mov     [rsp+10A0h+var_1068], rax
0x180007297  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x18000729e  lea     rax, [rsp+10A0h+var_1048]
0x1800072a3  xor     r9d, r9d
0x1800072a6  mov     [rsp+10A0h+var_1070], rax
0x1800072ab  mov     edx, edi
0x1800072ad  mov     [rsp+10A0h+var_1078], rsi
0x1800072b2  mov     rcx, rbx
0x1800072b5  mov     [rsp+10A0h+var_1080], r14
0x1800072ba  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800072bf  mov     eax, dword ptr [rsp+10A0h+var_1048]
0x1800072c3  mov     rcx, [rbp+0FA0h+var_20]
0x1800072ca  xor     rcx, rsp; StackCookie
0x1800072cd  call    __security_check_cookie
0x1800072d2  lea     r11, [rsp+10A0h+var_10]
0x1800072da  mov     rbx, [r11+30h]
0x1800072de  mov     rsi, [r11+38h]
0x1800072e2  mov     rsp, r11
0x1800072e5  pop     r14
0x1800072e7  pop     rdi
0x1800072e8  pop     rbp
0x1800072e9  retn
0x1800072ea  mov     ecx, 8007023Eh; this
0x1800072ef  mov     dword ptr [rsp+10A0h+var_1048], ecx
0x1800072f3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800072f8  mov     dword ptr [rsp+10A0h+var_1048+4], eax
0x1800072fc  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x180007303  lea     rax, [rbp+0FA0h+var_1020]
0x180007307  mov     [rsp+10A0h+var_1040], r14d
0x18000730c  mov     [rsp+10A0h+var_1068], rax
0x180007311  mov     edx, edi
0x180007313  lea     rax, [rsp+10A0h+var_1048]
0x180007318  mov     rcx, rbx
0x18000731b  mov     [rsp+10A0h+var_1070], rax
0x180007320  mov     [rsp+10A0h+var_1078], rsi
0x180007325  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
