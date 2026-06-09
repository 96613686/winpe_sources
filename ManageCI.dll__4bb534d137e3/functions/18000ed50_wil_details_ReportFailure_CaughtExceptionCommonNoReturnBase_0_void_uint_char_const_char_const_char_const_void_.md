# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<0>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000ed50`
- end: `0x18000ee4a`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$0A@@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `250`
- prototype: `void __fastcall __noreturn(__int64, int, int, __int64, __int64, __int64, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ed20`

## callees

- `0x180003cf0`
- `0x180003d28`
- `0x180006744`
- `0x18000ed50`
- `0x18002c010`

## string_xrefs

- `0x18000edef`: `onecore\base\ci\management\dll\manageci.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<0>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        char a10)
{
  __int64 v10; // rcx
  int v12; // ebp
  int v13; // r9d
  char v14; // dl
  _BYTE v15[56]; // [rsp+60h] [rbp-38h] BYREF

  a10 = 0;
  v10 = -1;
  v12 = a2;
  do
    ++v10;
  while ( *(_WORD *)(a8 + 2 * v10) );
  if ( g_pfnResultFromCaughtExceptionInternal
    && _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                         v15,
                                                         a8 + 2 * v10,
                                                         2048 - v10,
                                                         &a10)) < 0 )
  {
    v14 = 1;
  }
  else
  {
    LOBYTE(a2) = 0;
    wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  }
  if ( v14 )
    wil::details::ReportFailure_Base<0,0>(
      v12,
      a3,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
      v13);
  wil::details::ReportFailure_Base<3,0>(v12, a3, (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp", v13);
}

```

## disassembly

```asm
0x18000ed50  mov     rax, rsp
0x18000ed53  push    rbx
0x18000ed54  push    rbp
0x18000ed55  push    rsi
0x18000ed56  push    rdi
0x18000ed57  push    r14
0x18000ed59  sub     rsp, 70h
0x18000ed5d  mov     rdi, [rsp+98h+arg_38]
0x18000ed65  xor     r14d, r14d
0x18000ed68  mov     [rax+50h], r14b
0x18000ed6c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ed70  mov     esi, r8d
0x18000ed73  mov     rbp, rdx
0x18000ed76  inc     rcx
0x18000ed79  cmp     [rdi+rcx*2], r14w
0x18000ed7e  jnz     short loc_18000ED76
0x18000ed80  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000ed87  mov     ebx, 1
0x18000ed8c  test    rax, rax
0x18000ed8f  jz      short loc_18000EDCD
0x18000ed91  lea     rdx, [rdi+rcx*2]
0x18000ed95  mov     r8d, 800h
0x18000ed9b  sub     r8, rcx
0x18000ed9e  lea     r9, [rsp+98h+arg_48]
0x18000eda6  lea     rcx, [rsp+98h+var_38]
0x18000edab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edb0  movsd   xmm0, qword ptr [rax]
0x18000edb4  mov     eax, [rax+8]
0x18000edb7  mov     [rsp+98h+var_40], eax
0x18000edbb  movd    eax, xmm0
0x18000edbf  movsd   [rsp+98h+var_48], xmm0
0x18000edc5  test    eax, eax
0x18000edc7  jns     short loc_18000EDCD
0x18000edc9  mov     dl, bl
0x18000edcb  jmp     short loc_18000EDE7
0x18000edcd  mov     ecx, 8007023Eh; this
0x18000edd2  mov     dl, r14b; int
0x18000edd5  mov     dword ptr [rsp+98h+var_48], ecx
0x18000edd9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000edde  mov     dword ptr [rsp+98h+var_48+4], eax
0x18000ede2  mov     [rsp+98h+var_40], r14d
0x18000ede7  cmp     [rsp+98h+arg_48], r14b
0x18000edef  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x18000edf6  mov     eax, 3
0x18000edfb  mov     rcx, rbp
0x18000edfe  cmovnz  ebx, eax
0x18000ee01  test    dl, dl
0x18000ee03  mov     edx, esi
0x18000ee05  lea     rax, [rsp+98h+var_48]
0x18000ee0a  jz      short loc_18000EE2D
0x18000ee0c  mov     [rsp+98h+var_58], ebx
0x18000ee10  mov     [rsp+98h+var_60], rdi
0x18000ee15  mov     [rsp+98h+var_68], rax
0x18000ee1a  mov     rax, [rsp+98h+arg_30]
0x18000ee22  mov     [rsp+98h+var_70], rax
0x18000ee27  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000ee2d  mov     [rsp+98h+var_60], rdi
0x18000ee32  mov     [rsp+98h+var_68], rax
0x18000ee37  mov     rax, [rsp+98h+arg_30]
0x18000ee3f  mov     [rsp+98h+var_70], rax
0x18000ee44  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
