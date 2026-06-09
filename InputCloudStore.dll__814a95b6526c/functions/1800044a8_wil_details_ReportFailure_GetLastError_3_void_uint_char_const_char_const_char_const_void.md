# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800044a8`
- end: `0x180004522`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800076a4`

## callees

- `0x180004470`
- `0x1800044a8`
- `0x180005990`
- `0x180005f94`

## string_xrefs

- `0x1800044bf`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800044f0`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
    v10);
}

```

## disassembly

```asm
0x1800044a8  mov     [rsp+arg_0], rbx
0x1800044ad  mov     [rsp+arg_8], rsi
0x1800044b2  push    rdi
0x1800044b3  sub     rsp, 60h
0x1800044b7  mov     rsi, [rsp+68h+arg_28]
0x1800044bf  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800044c6  mov     [rsp+68h+var_40], rsi; char *
0x1800044cb  mov     ebx, edx
0x1800044cd  mov     rdi, rcx
0x1800044d0  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800044d5  test    eax, eax
0x1800044d7  jle     short loc_1800044E1
0x1800044d9  movzx   eax, ax
0x1800044dc  or      eax, 80070000h
0x1800044e1  mov     ecx, eax; this
0x1800044e3  mov     [rsp+68h+var_18], eax
0x1800044e7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800044ec  mov     [rsp+68h+var_14], eax
0x1800044f0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800044f7  lea     rax, [rsp+68h+var_18]
0x1800044fc  mov     [rsp+68h+var_30], 0
0x180004505  mov     [rsp+68h+var_38], rax
0x18000450a  mov     edx, ebx
0x18000450c  mov     rcx, rdi
0x18000450f  mov     [rsp+68h+var_40], rsi
0x180004514  mov     [rsp+68h+var_10], 0
0x18000451c  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
