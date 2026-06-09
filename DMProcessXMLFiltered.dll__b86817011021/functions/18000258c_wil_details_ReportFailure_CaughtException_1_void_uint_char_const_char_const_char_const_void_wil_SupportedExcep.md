# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x18000258c`
- end: `0x1800026d7`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800051e4`

## callees

- `0x180001520`
- `0x180001e5a`
- `0x1800024f8`
- `0x180002554`
- `0x18000258c`
- `0x180004734`
- `0x180006b70`
- `0x180008010`

## string_xrefs

- `0x18000264c`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`
- `0x1800026a5`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<1>(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v7; // edx
  __int64 v8; // rcx
  unsigned __int64 *v9; // rax
  int v10; // r9d
  __m128i v11; // xmm0
  int v12; // esi
  int v14; // r9d
  int v15; // [rsp+20h] [rbp-E0h]
  _BYTE v16[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h]
  _BYTE v19[24]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v20[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v20, 0, sizeof(v20));
  v16[0] = 0;
  v8 = -1;
  do
    ++v8;
  while ( v20[v8] );
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v9 = (unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(v19, &v20[v8], 2048 - v8, v16),
        v11 = (__m128i)*v9,
        LODWORD(v9) = *((_DWORD *)v9 + 2),
        v12 = _mm_cvtsi128_si32(v11),
        v17 = v11.m128i_i64[0],
        v18 = (int)v9,
        v12 >= 0) )
  {
    LODWORD(v17) = -2147024322;
    HIDWORD(v17) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v7);
    v18 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      160,
      (int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
      v14,
      v15,
      a6,
      (__int64)&v17,
      (__int64)v20);
  }
  wil::details::ReportFailure_Base<1,0>(
    a1,
    160,
    (int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
    v10,
    v15,
    a6,
    (int)&v17,
    (__int64)v20);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000258c  mov     [rsp-8+arg_8], rbx
0x180002591  mov     [rsp-8+arg_10], rsi
0x180002596  push    rbp
0x180002597  push    rdi
0x180002598  push    r14
0x18000259a  lea     rbp, [rsp-0F90h]
0x1800025a2  mov     eax, 1090h
0x1800025a7  call    _alloca_probe
0x1800025ac  sub     rsp, rax
0x1800025af  mov     rax, cs:__security_cookie
0x1800025b6  xor     rax, rsp
0x1800025b9  mov     [rbp+0FA0h+var_20], rax
0x1800025c0  mov     rdi, [rbp+0FA0h+arg_28]
0x1800025c7  mov     rbx, rcx
0x1800025ca  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x1800025ce  xor     edx, edx; Val
0x1800025d0  mov     r8d, 1000h; Size
0x1800025d6  call    memset_0
0x1800025db  xor     r14d, r14d
0x1800025de  lea     rax, [rbp+0FA0h+var_1020]
0x1800025e2  mov     [rsp+10A0h+var_1050], r14b
0x1800025e7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800025eb  inc     rcx
0x1800025ee  cmp     [rax+rcx*2], r14w
0x1800025f3  jnz     short loc_1800025EB
0x1800025f5  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1800025fc  test    rax, rax
0x1800025ff  jz      loc_180002693
0x180002605  mov     r8d, 800h
0x18000260b  lea     rdx, [rbp+0FA0h+var_1020]
0x18000260f  sub     r8, rcx
0x180002612  lea     rdx, [rdx+rcx*2]
0x180002616  lea     rcx, [rsp+10A0h+var_1038]
0x18000261b  lea     r9, [rsp+10A0h+var_1050]
0x180002620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002625  movsd   xmm0, qword ptr [rax]
0x180002629  mov     eax, [rax+8]
0x18000262c  movd    esi, xmm0
0x180002630  movsd   [rsp+10A0h+var_1048], xmm0
0x180002636  mov     [rsp+10A0h+var_1040], eax
0x18000263a  test    esi, esi
0x18000263c  jns     short loc_180002693
0x18000263e  lea     rax, [rbp+0FA0h+var_1020]
0x180002642  mov     edx, 0A0h
0x180002647  mov     [rsp+10A0h+var_1068], rax
0x18000264c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x180002653  lea     rax, [rsp+10A0h+var_1048]
0x180002658  mov     rcx, rbx
0x18000265b  mov     [rsp+10A0h+var_1070], rax
0x180002660  mov     [rsp+10A0h+var_1078], rdi
0x180002665  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000266a  mov     eax, esi
0x18000266c  mov     rcx, [rbp+0FA0h+var_20]
0x180002673  xor     rcx, rsp; StackCookie
0x180002676  call    __security_check_cookie
0x18000267b  lea     r11, [rsp+10A0h+var_10]
0x180002683  mov     rbx, [r11+28h]
0x180002687  mov     rsi, [r11+30h]
0x18000268b  mov     rsp, r11
0x18000268e  pop     r14
0x180002690  pop     rdi
0x180002691  pop     rbp
0x180002692  retn
0x180002693  mov     ecx, 8007023Eh; this
0x180002698  mov     dword ptr [rsp+10A0h+var_1048], ecx
0x18000269c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800026a1  mov     dword ptr [rsp+10A0h+var_1048+4], eax
0x1800026a5  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x1800026ac  lea     rax, [rbp+0FA0h+var_1020]
0x1800026b0  mov     [rsp+10A0h+var_1040], r14d
0x1800026b5  mov     [rsp+10A0h+var_1068], rax
0x1800026ba  mov     edx, 0A0h
0x1800026bf  lea     rax, [rsp+10A0h+var_1048]
0x1800026c4  mov     rcx, rbx
0x1800026c7  mov     [rsp+10A0h+var_1070], rax
0x1800026cc  mov     [rsp+10A0h+var_1078], rdi
0x1800026d1  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
