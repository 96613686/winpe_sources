# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x180007adc`
- end: `0x180007c23`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000a9b0`

## callees

- `0x180002650`
- `0x1800032a4`
- `0x180003490`
- `0x1800034f0`
- `0x180005590`
- `0x180007adc`
- `0x18000bec0`
- `0x18000d010`

## string_xrefs

- `0x180007b9b`: `onecoreuap\net\wcm\service\base\appprioritizationusersessionhost\lib\appprioritizationusersession.cpp`
- `0x180007bf4`: `onecoreuap\net\wcm\service\base\appprioritizationusersessionhost\lib\appprioritizationusersession.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<1>(__int64 a1, unsigned int a2)
{
  int v4; // edx
  __int64 v5; // rcx
  int v6; // r14d
  int v8; // r9d
  _BYTE v9[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v10[16]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v11[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v11, 0, sizeof(v11));
  v10[0] = 0;
  v5 = -1;
  do
    ++v5;
  while ( v11[v5] );
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v6 = _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                               v9,
                                                               &v11[v5],
                                                               2048 - v5,
                                                               v10)),
        v6 >= 0) )
  {
    wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v4);
    wil::details::ReportFailure_Base<3,0>(
      a1,
      a2,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\appprioritizationusersessionhost\\lib\\appprioritizationusersession.cpp",
      v8);
  }
  wil::details::ReportFailure_Base<1,0>(
    a1,
    a2,
    "onecoreuap\\net\\wcm\\service\\base\\appprioritizationusersessionhost\\lib\\appprioritizationusersession.cpp");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007adc  mov     [rsp-8+arg_10], rbx
0x180007ae1  push    rbp
0x180007ae2  push    rsi
0x180007ae3  push    rdi
0x180007ae4  push    r14
0x180007ae6  push    r15
0x180007ae8  lea     rbp, [rsp-0F90h]
0x180007af0  mov     eax, 1090h
0x180007af5  call    _alloca_probe
0x180007afa  sub     rsp, rax
0x180007afd  mov     rax, cs:__security_cookie
0x180007b04  xor     rax, rsp
0x180007b07  mov     [rbp+0FB0h+var_30], rax
0x180007b0e  mov     rsi, [rbp+0FB0h+arg_28]
0x180007b15  mov     edi, edx
0x180007b17  mov     rbx, rcx
0x180007b1a  xor     edx, edx; Val
0x180007b1c  lea     rcx, [rbp+0FB0h+var_1030]; void *
0x180007b20  mov     r8d, 1000h; Size
0x180007b26  call    memset_0
0x180007b2b  xor     r15d, r15d
0x180007b2e  lea     rax, [rbp+0FB0h+var_1030]
0x180007b32  mov     [rsp+10B0h+var_1040], r15b
0x180007b37  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007b3b  inc     rcx
0x180007b3e  cmp     [rax+rcx*2], r15w
0x180007b43  jnz     short loc_180007B3B
0x180007b45  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180007b4c  test    rax, rax
0x180007b4f  jz      loc_180007BE2
0x180007b55  mov     r8d, 800h
0x180007b5b  lea     rdx, [rbp+0FB0h+var_1030]
0x180007b5f  sub     r8, rcx
0x180007b62  lea     rdx, [rdx+rcx*2]
0x180007b66  lea     rcx, [rsp+10B0h+var_1050]
0x180007b6b  lea     r9, [rsp+10B0h+var_1040]
0x180007b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b75  movsd   xmm0, qword ptr [rax]
0x180007b79  mov     eax, [rax+8]
0x180007b7c  movd    r14d, xmm0
0x180007b81  movsd   [rsp+10B0h+var_1060], xmm0
0x180007b87  mov     [rsp+10B0h+var_1058], eax
0x180007b8b  test    r14d, r14d
0x180007b8e  jns     short loc_180007BE2
0x180007b90  lea     rax, [rbp+0FB0h+var_1030]
0x180007b94  mov     edx, edi
0x180007b96  mov     [rsp+10B0h+var_1078], rax
0x180007b9b  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\service\\base\\ap"...
0x180007ba2  lea     rax, [rsp+10B0h+var_1060]
0x180007ba7  mov     rcx, rbx
0x180007baa  mov     [rsp+10B0h+var_1080], rax
0x180007baf  mov     [rsp+10B0h+var_1088], rsi
0x180007bb4  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180007bb9  mov     eax, r14d
0x180007bbc  mov     rcx, [rbp+0FB0h+var_30]
0x180007bc3  xor     rcx, rsp; StackCookie
0x180007bc6  call    __security_check_cookie
0x180007bcb  mov     rbx, [rsp+10B0h+arg_10]
0x180007bd3  add     rsp, 1090h
0x180007bda  pop     r15
0x180007bdc  pop     r14
0x180007bde  pop     rdi
0x180007bdf  pop     rsi
0x180007be0  pop     rbp
0x180007be1  retn
0x180007be2  mov     ecx, 8007023Eh; this
0x180007be7  mov     dword ptr [rsp+10B0h+var_1060], ecx
0x180007beb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007bf0  mov     dword ptr [rsp+10B0h+var_1060+4], eax
0x180007bf4  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\service\\base\\ap"...
0x180007bfb  lea     rax, [rbp+0FB0h+var_1030]
0x180007bff  mov     [rsp+10B0h+var_1058], r15d
0x180007c04  mov     [rsp+10B0h+var_1078], rax
0x180007c09  mov     edx, edi
0x180007c0b  lea     rax, [rsp+10B0h+var_1060]
0x180007c10  mov     rcx, rbx
0x180007c13  mov     [rsp+10B0h+var_1080], rax
0x180007c18  mov     [rsp+10B0h+var_1088], rsi
0x180007c1d  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
