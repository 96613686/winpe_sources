# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x180002f6c`
- end: `0x1800030b7`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x1800067c4`

## callees

- `0x180001620`
- `0x1800020d0`
- `0x180002ed8`
- `0x180002f34`
- `0x180002f6c`
- `0x180005b68`
- `0x18000c790`
- `0x18000e010`

## string_xrefs

- `0x18000302c`: `base\embedded\sys\dialogblocking\service\dll\dialogblockingservice.cpp`
- `0x180003085`: `base\embedded\sys\dialogblocking\service\dll\dialogblockingservice.cpp`

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
      36,
      (int)"base\\embedded\\sys\\dialogblocking\\service\\dll\\dialogblockingservice.cpp",
      v14,
      v15,
      a6,
      (__int64)&v17,
      (__int64)v20);
  }
  wil::details::ReportFailure_Base<1,0>(
    a1,
    36,
    (int)"base\\embedded\\sys\\dialogblocking\\service\\dll\\dialogblockingservice.cpp",
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
0x180002f6c  mov     [rsp-8+arg_8], rbx
0x180002f71  mov     [rsp-8+arg_10], rsi
0x180002f76  push    rbp
0x180002f77  push    rdi
0x180002f78  push    r14
0x180002f7a  lea     rbp, [rsp-0F90h]
0x180002f82  mov     eax, 1090h
0x180002f87  call    _alloca_probe
0x180002f8c  sub     rsp, rax
0x180002f8f  mov     rax, cs:__security_cookie
0x180002f96  xor     rax, rsp
0x180002f99  mov     [rbp+0FA0h+var_20], rax
0x180002fa0  mov     rdi, [rbp+0FA0h+arg_28]
0x180002fa7  mov     rbx, rcx
0x180002faa  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x180002fae  xor     edx, edx; Val
0x180002fb0  mov     r8d, 1000h; Size
0x180002fb6  call    memset_0
0x180002fbb  xor     r14d, r14d
0x180002fbe  lea     rax, [rbp+0FA0h+var_1020]
0x180002fc2  mov     [rsp+10A0h+var_1050], r14b
0x180002fc7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002fcb  inc     rcx
0x180002fce  cmp     [rax+rcx*2], r14w
0x180002fd3  jnz     short loc_180002FCB
0x180002fd5  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180002fdc  test    rax, rax
0x180002fdf  jz      loc_180003073
0x180002fe5  mov     r8d, 800h
0x180002feb  lea     rdx, [rbp+0FA0h+var_1020]
0x180002fef  sub     r8, rcx
0x180002ff2  lea     rdx, [rdx+rcx*2]
0x180002ff6  lea     rcx, [rsp+10A0h+var_1038]
0x180002ffb  lea     r9, [rsp+10A0h+var_1050]
0x180003000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003005  movsd   xmm0, qword ptr [rax]
0x180003009  mov     eax, [rax+8]
0x18000300c  movd    esi, xmm0
0x180003010  movsd   [rsp+10A0h+var_1048], xmm0
0x180003016  mov     [rsp+10A0h+var_1040], eax
0x18000301a  test    esi, esi
0x18000301c  jns     short loc_180003073
0x18000301e  lea     rax, [rbp+0FA0h+var_1020]
0x180003022  mov     edx, 24h ; '$'
0x180003027  mov     [rsp+10A0h+var_1068], rax
0x18000302c  lea     r8, aBaseEmbeddedSy; "base\\embedded\\sys\\dialogblocking\\se"...
0x180003033  lea     rax, [rsp+10A0h+var_1048]
0x180003038  mov     rcx, rbx
0x18000303b  mov     [rsp+10A0h+var_1070], rax
0x180003040  mov     [rsp+10A0h+var_1078], rdi
0x180003045  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000304a  mov     eax, esi
0x18000304c  mov     rcx, [rbp+0FA0h+var_20]
0x180003053  xor     rcx, rsp; StackCookie
0x180003056  call    __security_check_cookie
0x18000305b  lea     r11, [rsp+10A0h+var_10]
0x180003063  mov     rbx, [r11+28h]
0x180003067  mov     rsi, [r11+30h]
0x18000306b  mov     rsp, r11
0x18000306e  pop     r14
0x180003070  pop     rdi
0x180003071  pop     rbp
0x180003072  retn
0x180003073  mov     ecx, 8007023Eh; this
0x180003078  mov     dword ptr [rsp+10A0h+var_1048], ecx
0x18000307c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003081  mov     dword ptr [rsp+10A0h+var_1048+4], eax
0x180003085  lea     r8, aBaseEmbeddedSy; "base\\embedded\\sys\\dialogblocking\\se"...
0x18000308c  lea     rax, [rbp+0FA0h+var_1020]
0x180003090  mov     [rsp+10A0h+var_1040], r14d
0x180003095  mov     [rsp+10A0h+var_1068], rax
0x18000309a  mov     edx, 24h ; '$'
0x18000309f  lea     rax, [rsp+10A0h+var_1048]
0x1800030a4  mov     rcx, rbx
0x1800030a7  mov     [rsp+10A0h+var_1070], rax
0x1800030ac  mov     [rsp+10A0h+var_1078], rdi
0x1800030b1  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
