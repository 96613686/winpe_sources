# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180024b30`
- end: `0x180024ba2`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `114`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180027b60`

## callees

- `0x180006010`
- `0x180006620`
- `0x18000d524`
- `0x180024b30`

## string_xrefs

- `0x180024b42`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180024b76`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  signed int LastErrorFail; // eax
  int v8; // edx
  int v9; // r9d
  const char *v10; // [rsp+20h] [rbp-48h]
  int v11; // [rsp+20h] [rbp-48h]
  void *v12; // [rsp+30h] [rbp-38h]
  _DWORD v13[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x1CC8,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                    a4,
                    v10,
                    a6,
                    v12);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v13[0] = LastErrorFail;
  v13[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v8);
  v13[2] = 0;
  wil::details::ReportFailure_Base<0,0>(
    v6,
    7368,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
    v9,
    v11,
    (__int64)a6,
    (__int64)v13);
}

```

## disassembly

```asm
0x180024b30  mov     [rsp+arg_0], rbx
0x180024b35  push    rdi
0x180024b36  sub     rsp, 60h
0x180024b3a  mov     rdi, [rsp+68h+arg_28]
0x180024b42  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024b49  mov     edx, 1CC8h; void *
0x180024b4e  mov     [rsp+68h+var_40], rdi; char *
0x180024b53  mov     rbx, rcx
0x180024b56  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180024b5b  test    eax, eax
0x180024b5d  jle     short loc_180024B67
0x180024b5f  movzx   eax, ax
0x180024b62  or      eax, 80070000h
0x180024b67  mov     ecx, eax; this
0x180024b69  mov     [rsp+68h+var_18], eax
0x180024b6d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180024b72  mov     [rsp+68h+var_14], eax
0x180024b76  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024b7d  lea     rax, [rsp+68h+var_18]
0x180024b82  mov     [rsp+68h+var_10], 0
0x180024b8a  mov     [rsp+68h+var_38], rax
0x180024b8f  mov     edx, 1CC8h
0x180024b94  mov     rcx, rbx
0x180024b97  mov     [rsp+68h+var_40], rdi
0x180024b9c  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
