# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x1800100c4`
- end: `0x1800101b2`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010094`

## callees

- `0x1800038bc`
- `0x180006aa4`
- `0x1800100c4`
- `0x18002b010`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rcx
  int v10; // r9d
  int v11; // r9d
  _BYTE v12[24]; // [rsp+60h] [rbp-18h] BYREF
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  LOBYTE(v13) = 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a8 + 2 * v8) );
  if ( g_pfnResultFromCaughtExceptionInternal )
  {
    if ( _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                           v12,
                                                           a8 + 2 * v8,
                                                           2048 - v8,
                                                           &v13)) < 0 )
      wil::details::ReportFailure_Base<3,0>(
        a2,
        1256,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
        v10);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(
    a2,
    1256,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
    v11);
}

```

## disassembly

```asm
0x1800100c4  mov     rax, rsp
0x1800100c7  mov     [rax+8], rbx
0x1800100cb  mov     [rax+10h], rsi
0x1800100cf  mov     [rax+18h], r8d
0x1800100d3  push    rdi
0x1800100d4  sub     rsp, 70h
0x1800100d8  mov     rbx, [rsp+78h+arg_38]
0x1800100e0  xor     esi, esi
0x1800100e2  mov     [rax+18h], sil
0x1800100e6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800100ea  mov     rdi, rdx
0x1800100ed  inc     rcx
0x1800100f0  cmp     [rbx+rcx*2], si
0x1800100f4  jnz     short loc_1800100ED
0x1800100f6  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1800100fd  test    rax, rax
0x180010100  jz      short loc_18001016B
0x180010102  lea     rdx, [rbx+rcx*2]
0x180010106  mov     r8d, 800h
0x18001010c  sub     r8, rcx
0x18001010f  lea     r9, [rsp+78h+arg_10]
0x180010117  lea     rcx, [rsp+78h+var_18]
0x18001011c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010121  movsd   xmm0, qword ptr [rax]
0x180010125  mov     eax, [rax+8]
0x180010128  mov     [rsp+78h+var_20], eax
0x18001012c  movd    eax, xmm0
0x180010130  movsd   [rsp+78h+var_28], xmm0
0x180010136  test    eax, eax
0x180010138  jns     short loc_18001016B
0x18001013a  lea     rax, [rsp+78h+var_28]
0x18001013f  mov     [rsp+78h+var_40], rbx
0x180010144  mov     [rsp+78h+var_48], rax
0x180010149  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180010150  mov     rax, [rsp+78h+arg_30]
0x180010158  mov     edx, 4E8h
0x18001015d  mov     rcx, rdi
0x180010160  mov     [rsp+78h+var_50], rax
0x180010165  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001016b  mov     ecx, 8007023Eh; this
0x180010170  mov     dword ptr [rsp+78h+var_28], ecx
0x180010174  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010179  mov     dword ptr [rsp+78h+var_28+4], eax
0x18001017d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180010184  lea     rax, [rsp+78h+var_28]
0x180010189  mov     [rsp+78h+var_40], rbx
0x18001018e  mov     [rsp+78h+var_48], rax
0x180010193  mov     edx, 4E8h
0x180010198  mov     rax, [rsp+78h+arg_30]
0x1800101a0  mov     rcx, rdi
0x1800101a3  mov     [rsp+78h+var_50], rax
0x1800101a8  mov     [rsp+78h+var_20], esi
0x1800101ac  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
