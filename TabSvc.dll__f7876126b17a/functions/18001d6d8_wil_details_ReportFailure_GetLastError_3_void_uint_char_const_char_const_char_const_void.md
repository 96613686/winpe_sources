# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18001d6d8`
- end: `0x18001d752`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180028530`

## callees

- `0x18001b4b0`
- `0x18001b674`
- `0x18001d4dc`
- `0x18001d6d8`

## string_xrefs

- `0x18001d6ef`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001d720`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  void *v12; // [rsp+30h] [rbp-38h]

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v11,
                    a6,
                    v12);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v10);
}

```

## disassembly

```asm
0x18001d6d8  mov     [rsp+arg_0], rbx
0x18001d6dd  mov     [rsp+arg_8], rsi
0x18001d6e2  push    rdi
0x18001d6e3  sub     rsp, 60h
0x18001d6e7  mov     rsi, [rsp+68h+arg_28]
0x18001d6ef  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d6f6  mov     [rsp+68h+var_40], rsi; char *
0x18001d6fb  mov     ebx, edx
0x18001d6fd  mov     rdi, rcx
0x18001d700  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18001d705  test    eax, eax
0x18001d707  jle     short loc_18001D711
0x18001d709  movzx   eax, ax
0x18001d70c  or      eax, 80070000h
0x18001d711  mov     ecx, eax; this
0x18001d713  mov     [rsp+68h+var_18], eax
0x18001d717  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001d71c  mov     [rsp+68h+var_14], eax
0x18001d720  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d727  lea     rax, [rsp+68h+var_18]
0x18001d72c  mov     [rsp+68h+var_30], 0
0x18001d735  mov     [rsp+68h+var_38], rax
0x18001d73a  mov     edx, ebx
0x18001d73c  mov     rcx, rdi
0x18001d73f  mov     [rsp+68h+var_40], rsi
0x18001d744  mov     [rsp+68h+var_10], 0
0x18001d74c  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
