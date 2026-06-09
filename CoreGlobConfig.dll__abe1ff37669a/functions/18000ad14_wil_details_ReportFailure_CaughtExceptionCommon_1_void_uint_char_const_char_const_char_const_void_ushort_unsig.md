# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000ad14`
- end: `0x18000ae01`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000abdc`

## callees

- `0x180005c30`
- `0x180005c90`
- `0x180007754`
- `0x18000ad14`
- `0x180025010`

## string_xrefs

- `0x18000ad97`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18000add4`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

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
  __int64 (__fastcall *v14)(_BYTE *, __int64, __int64, char *); // rax
  __int64 v15; // rax
  int v16; // ecx
  int v18; // r9d
  _BYTE v19[56]; // [rsp+50h] [rbp-38h] BYREF

  a10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a8 + 2 * v11) );
  v14 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, char *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v14
    || (v15 = v14(v19, a8 + 2 * v11, 2048 - v11, &a10),
        v16 = *(_DWORD *)(v15 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v15,
        *(_DWORD *)(a1 + 8) = v16,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(
      a2,
      a3,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      v18);
  }
  wil::details::ReportFailure_Base<1,0>(
    a2,
    a3,
    "onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp");
  return a1;
}

```

## disassembly

```asm
0x18000ad14  mov     rax, rsp
0x18000ad17  push    rbx
0x18000ad18  push    rbp
0x18000ad19  push    rsi
0x18000ad1a  push    rdi
0x18000ad1b  push    r14
0x18000ad1d  sub     rsp, 60h
0x18000ad21  mov     rdi, [rsp+88h+arg_38]
0x18000ad29  xor     r14d, r14d
0x18000ad2c  mov     rbx, rcx
0x18000ad2f  mov     [rax+50h], r14b
0x18000ad33  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ad37  mov     esi, r8d
0x18000ad3a  mov     rbp, rdx
0x18000ad3d  inc     rcx
0x18000ad40  cmp     [rdi+rcx*2], r14w
0x18000ad45  jnz     short loc_18000AD3D
0x18000ad47  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000ad4e  mov     [rbx], r14
0x18000ad51  mov     dword ptr [rbx+8], 1
0x18000ad58  test    rax, rax
0x18000ad5b  jz      short loc_18000ADC5
0x18000ad5d  lea     rdx, [rdi+rcx*2]
0x18000ad61  mov     r8d, 800h
0x18000ad67  sub     r8, rcx
0x18000ad6a  lea     r9, [rsp+88h+arg_48]
0x18000ad72  lea     rcx, [rsp+88h+var_38]
0x18000ad77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad7c  movsd   xmm0, qword ptr [rax]
0x18000ad80  mov     ecx, [rax+8]
0x18000ad83  movsd   qword ptr [rbx], xmm0
0x18000ad87  mov     [rbx+8], ecx
0x18000ad8a  cmp     [rbx], r14d
0x18000ad8d  jge     short loc_18000ADC5
0x18000ad8f  mov     rax, [rsp+88h+arg_30]
0x18000ad97  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18000ad9e  mov     [rsp+88h+var_50], rdi
0x18000ada3  mov     edx, esi
0x18000ada5  mov     [rsp+88h+var_58], rbx
0x18000adaa  mov     rcx, rbp
0x18000adad  mov     [rsp+88h+var_60], rax
0x18000adb2  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000adb7  mov     rax, rbx
0x18000adba  add     rsp, 60h
0x18000adbe  pop     r14
0x18000adc0  pop     rdi
0x18000adc1  pop     rsi
0x18000adc2  pop     rbp
0x18000adc3  pop     rbx
0x18000adc4  retn
0x18000adc5  mov     ecx, 8007023Eh; this
0x18000adca  mov     [rbx], ecx
0x18000adcc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000add1  mov     [rbx+4], eax
0x18000add4  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18000addb  mov     rax, [rsp+88h+arg_30]
0x18000ade3  mov     edx, esi
0x18000ade5  mov     [rsp+88h+var_50], rdi
0x18000adea  mov     rcx, rbp
0x18000aded  mov     [rsp+88h+var_58], rbx
0x18000adf2  mov     [rsp+88h+var_60], rax
0x18000adf7  mov     [rbx+8], r14d
0x18000adfb  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
