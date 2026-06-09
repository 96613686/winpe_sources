# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180017ff0`
- end: `0x180018093`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `163`
- prototype: `__int64 __fastcall(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019f4c`

## callees

- `0x1800082f0`
- `0x1800095a0`
- `0x180009ac8`
- `0x180017ff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001807b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001807b`

## string_xrefs

- `0x180018007`: `onecore\base\appmodel\StateRepository\Common\Inc\DataType-Temporal.hpp`
- `0x180018042`: `onecore\base\appmodel\StateRepository\Common\Inc\DataType-Temporal.hpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int LastErrorFail; // eax
  DWORD v8; // ebx
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  const char *v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]
  _DWORD v14[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x26,
                    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\DataType-Temporal.hpp",
                    a4,
                    v12,
                    a6,
                    v13);
  v8 = LastErrorFail;
  if ( LastErrorFail > 0 )
    v9 = (unsigned __int16)LastErrorFail | 0x80070000;
  else
    v9 = (unsigned int)LastErrorFail;
  v14[0] = v9;
  v14[1] = wil::details::HrToNtStatus((wil::details *)v9, 0);
  v14[2] = v10;
  wil::details::ReportFailure_Base<2,0>(
    v6,
    38,
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\DataType-Temporal.hpp",
    0,
    v10,
    (__int64)a6,
    (__int64)v14,
    v10);
  SetLastError(v8);
  return v8;
}

```

## disassembly

```asm
0x180017ff0  mov     [rsp+arg_0], rbx
0x180017ff5  mov     [rsp+arg_8], rsi
0x180017ffa  push    rdi
0x180017ffb  sub     rsp, 60h
0x180017fff  mov     rsi, [rsp+68h+arg_28]
0x180018007  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\StateRepositor"...
0x18001800e  mov     edx, 26h ; '&'; void *
0x180018013  mov     [rsp+68h+var_40], rsi; char *
0x180018018  mov     rdi, rcx
0x18001801b  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180018020  xor     edx, edx; int
0x180018022  mov     ebx, eax
0x180018024  test    eax, eax
0x180018026  jg      short loc_18001802C
0x180018028  mov     ecx, eax
0x18001802a  jmp     short loc_180018035
0x18001802c  movzx   ecx, bx
0x18001802f  or      ecx, 80070000h; this
0x180018035  mov     [rsp+68h+var_18], ecx
0x180018039  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001803e  mov     [rsp+68h+var_20], edx
0x180018042  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\StateRepositor"...
0x180018049  mov     [rsp+68h+var_30], rdx
0x18001804e  xor     r9d, r9d
0x180018051  mov     [rsp+68h+var_14], eax
0x180018055  mov     rcx, rdi
0x180018058  lea     rax, [rsp+68h+var_18]
0x18001805d  mov     [rsp+68h+var_10], edx
0x180018061  mov     [rsp+68h+var_38], rax
0x180018066  mov     [rsp+68h+var_40], rsi
0x18001806b  mov     [rsp+68h+var_48], rdx
0x180018070  lea     edx, [r9+26h]
0x180018074  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180018079  mov     ecx, ebx; dwErrCode
0x18001807b  call    cs:__imp_SetLastError
0x180018081  mov     rsi, [rsp+68h+arg_8]
0x180018086  mov     eax, ebx
0x180018088  mov     rbx, [rsp+68h+arg_0]
0x18001808d  add     rsp, 60h
0x180018091  pop     rdi
0x180018092  retn
```
