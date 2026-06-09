# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000e1a4`
- end: `0x18000e21e`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800167b0`

## callees

- `0x18000dff0`
- `0x18000e1a4`
- `0x180011e40`
- `0x180012eec`

## string_xrefs

- `0x18000e1bb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e1ec`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000e1a4  mov     [rsp+arg_0], rbx
0x18000e1a9  mov     [rsp+arg_8], rsi
0x18000e1ae  push    rdi
0x18000e1af  sub     rsp, 60h
0x18000e1b3  mov     rsi, [rsp+68h+arg_28]
0x18000e1bb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e1c2  mov     [rsp+68h+var_40], rsi; char *
0x18000e1c7  mov     ebx, edx
0x18000e1c9  mov     rdi, rcx
0x18000e1cc  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000e1d1  test    eax, eax
0x18000e1d3  jle     short loc_18000E1DD
0x18000e1d5  movzx   eax, ax
0x18000e1d8  or      eax, 80070000h
0x18000e1dd  mov     ecx, eax; this
0x18000e1df  mov     [rsp+68h+var_18], eax
0x18000e1e3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e1e8  mov     [rsp+68h+var_14], eax
0x18000e1ec  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e1f3  lea     rax, [rsp+68h+var_18]
0x18000e1f8  mov     [rsp+68h+var_30], 0
0x18000e201  mov     [rsp+68h+var_38], rax
0x18000e206  mov     edx, ebx
0x18000e208  mov     rcx, rdi
0x18000e20b  mov     [rsp+68h+var_40], rsi
0x18000e210  mov     [rsp+68h+var_10], 0
0x18000e218  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
