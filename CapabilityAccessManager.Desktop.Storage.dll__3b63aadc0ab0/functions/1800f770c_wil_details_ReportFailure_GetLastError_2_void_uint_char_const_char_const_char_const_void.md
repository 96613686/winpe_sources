# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800f770c`
- end: `0x1800f77aa`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `158`
- prototype: `__int64 __fastcall(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800fcdc4`

## callees

- `0x1800e8250`
- `0x1800e8820`
- `0x1800f76c8`
- `0x1800f770c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f7792`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f7792`

## string_xrefs

- `0x1800f7723`: `onecore\base\appmodel\StateRepository\Common\Inc\DataType-Temporal.hpp`
- `0x1800f775c`: `onecore\base\appmodel\StateRepository\Common\Inc\DataType-Temporal.hpp`

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
  int LastErrorFail; // eax
  int v8; // edx
  DWORD v9; // ebx
  unsigned __int64 v10; // rcx
  const char *v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]

  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x26,
                    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\DataType-Temporal.hpp",
                    a4,
                    v12,
                    a6,
                    v13);
  v9 = LastErrorFail;
  if ( LastErrorFail > 0 )
    v10 = (unsigned __int16)LastErrorFail | 0x80070000;
  else
    v10 = (unsigned int)LastErrorFail;
  wil::details::HrToNtStatus((wil::details *)v10, v8);
  wil::details::ReportFailure_Base<2,0>(
    a1,
    38,
    "onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\DataType-Temporal.hpp");
  SetLastError(v9);
  return v9;
}

```

## disassembly

```asm
0x1800f770c  mov     [rsp+arg_0], rbx
0x1800f7711  mov     [rsp+arg_8], rsi
0x1800f7716  push    rdi
0x1800f7717  sub     rsp, 60h
0x1800f771b  mov     rsi, [rsp+68h+arg_28]
0x1800f7723  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x1800f772a  mov     edx, 26h ; '&'; void *
0x1800f772f  mov     [rsp+68h+var_40], rsi; char *
0x1800f7734  mov     rdi, rcx
0x1800f7737  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800f773c  mov     ebx, eax
0x1800f773e  test    eax, eax
0x1800f7740  jg      short loc_1800F7746
0x1800f7742  mov     ecx, eax
0x1800f7744  jmp     short loc_1800F774F
0x1800f7746  movzx   ecx, bx
0x1800f7749  or      ecx, 80070000h; this
0x1800f774f  mov     [rsp+68h+var_18], ecx
0x1800f7753  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800f7758  mov     [rsp+68h+var_14], eax
0x1800f775c  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x1800f7763  lea     rax, [rsp+68h+var_18]
0x1800f7768  mov     [rsp+68h+var_30], 0
0x1800f7771  mov     [rsp+68h+var_38], rax
0x1800f7776  mov     edx, 26h ; '&'
0x1800f777b  mov     rcx, rdi
0x1800f777e  mov     [rsp+68h+var_40], rsi
0x1800f7783  mov     [rsp+68h+var_10], 0
0x1800f778b  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800f7790  mov     ecx, ebx; dwErrCode
0x1800f7792  call    cs:__imp_SetLastError
0x1800f7798  mov     rsi, [rsp+68h+arg_8]
0x1800f779d  mov     eax, ebx
0x1800f779f  mov     rbx, [rsp+68h+arg_0]
0x1800f77a4  add     rsp, 60h
0x1800f77a8  pop     rdi
0x1800f77a9  retn
```
