# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800a8324`
- end: `0x1800a8395`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800adac8`

## callees

- `0x1800a82f8`
- `0x1800a8324`
- `0x1800aa5f0`
- `0x1800aab40`

## string_xrefs

- `0x1800a833b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800a836c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  int v7; // edi
  signed int LastErrorFail; // eax
  int v9; // edx
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-48h]
  int v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]
  _DWORD v14[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v14[0] = LastErrorFail;
  v14[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  v14[2] = 0;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v10,
    v12,
    (__int64)a6,
    (__int64)v14);
}

```

## disassembly

```asm
0x1800a8324  mov     [rsp+arg_0], rbx
0x1800a8329  mov     [rsp+arg_8], rsi
0x1800a832e  push    rdi
0x1800a832f  sub     rsp, 60h
0x1800a8333  mov     rsi, [rsp+68h+arg_28]
0x1800a833b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a8342  mov     [rsp+68h+var_40], rsi; char *
0x1800a8347  mov     ebx, edx
0x1800a8349  mov     rdi, rcx
0x1800a834c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800a8351  test    eax, eax
0x1800a8353  jle     short loc_1800A835D
0x1800a8355  movzx   eax, ax
0x1800a8358  or      eax, 80070000h
0x1800a835d  mov     ecx, eax; this
0x1800a835f  mov     [rsp+68h+var_18], eax
0x1800a8363  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800a8368  mov     [rsp+68h+var_14], eax
0x1800a836c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a8373  lea     rax, [rsp+68h+var_18]
0x1800a8378  mov     [rsp+68h+var_10], 0
0x1800a8380  mov     [rsp+68h+var_38], rax
0x1800a8385  mov     edx, ebx
0x1800a8387  mov     rcx, rdi
0x1800a838a  mov     [rsp+68h+var_40], rsi
0x1800a838f  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
