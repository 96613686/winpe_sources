# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18002639c`
- end: `0x180026463`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `199`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180029118`
- `0x180029358`

## callees

- `0x180003f58`
- `0x1800042b8`
- `0x180007ee0`
- `0x18002639c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026452`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263aa`

## string_xrefs

- `0x1800263d7`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x18002643f`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v8; // edx
  int LastError; // ebx
  unsigned __int64 v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-58h]
  _DWORD v13[14]; // [rsp+50h] [rbp-38h] BYREF

  LastError = GetLastError();
  if ( !LastError )
  {
    LODWORD(v12) = -2147024228;
    wil::details::ReportFailure_Hr<2>(
      a1,
      a2,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
      0,
      0,
      a6,
      v12);
    LastError = 668;
  }
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  else
    v10 = (unsigned int)LastError;
  v13[0] = v10;
  v13[1] = wil::details::HrToNtStatus((wil::details *)v10, v8);
  v13[2] = 0;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    a2,
    (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
    0,
    0,
    a6,
    (__int64)v13,
    0);
  SetLastError(LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002639c  push    rbx
0x18002639e  push    rbp
0x18002639f  push    rsi
0x1800263a0  push    rdi
0x1800263a1  sub     rsp, 68h
0x1800263a5  mov     edi, edx
0x1800263a7  mov     rsi, rcx
0x1800263aa  call    cs:__imp_GetLastError
0x1800263b0  mov     ebx, eax
0x1800263b2  mov     rbp, [rsp+88h+arg_28]
0x1800263ba  test    eax, eax
0x1800263bc  jnz     short loc_1800263ED
0x1800263be  mov     dword ptr [rsp+88h+var_58], 8007029Ch; wil::details *
0x1800263c6  mov     [rsp+88h+var_60], rbp; __int64
0x1800263cb  mov     [rsp+88h+var_68], 0; __int64
0x1800263d4  xor     r9d, r9d; int
0x1800263d7  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x1800263de  mov     edx, edi; int
0x1800263e0  mov     rcx, rsi; int
0x1800263e3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800263e8  mov     ebx, 29Ch
0x1800263ed  test    ebx, ebx
0x1800263ef  jg      short loc_1800263F5
0x1800263f1  mov     ecx, ebx
0x1800263f3  jmp     short loc_1800263FE
0x1800263f5  movzx   ecx, bx
0x1800263f8  or      ecx, 80070000h; this
0x1800263fe  mov     [rsp+88h+var_38], ecx
0x180026402  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180026407  mov     [rsp+88h+var_34], eax
0x18002640b  mov     [rsp+88h+var_30], 0
0x180026413  mov     [rsp+88h+var_40], 0
0x18002641b  mov     [rsp+88h+var_50], 0
0x180026424  lea     rax, [rsp+88h+var_38]
0x180026429  mov     [rsp+88h+var_58], rax
0x18002642e  mov     [rsp+88h+var_60], rbp
0x180026433  mov     [rsp+88h+var_68], 0
0x18002643c  xor     r9d, r9d
0x18002643f  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180026446  mov     edx, edi
0x180026448  mov     rcx, rsi
0x18002644b  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180026450  mov     ecx, ebx; dwErrCode
0x180026452  call    cs:__imp_SetLastError
0x180026458  mov     eax, ebx
0x18002645a  add     rsp, 68h
0x18002645e  pop     rdi
0x18002645f  pop     rsi
0x180026460  pop     rbp
0x180026461  pop     rbx
0x180026462  retn
```
