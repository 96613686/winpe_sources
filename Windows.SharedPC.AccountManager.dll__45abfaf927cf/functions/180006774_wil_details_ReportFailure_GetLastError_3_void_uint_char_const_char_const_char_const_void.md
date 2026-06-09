# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180006774`
- end: `0x1800067ee`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009518`

## callees

- `0x180004f5c`
- `0x18000673c`
- `0x180006774`
- `0x180007d70`

## string_xrefs

- `0x18000678b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800067bc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180006774  mov     [rsp+arg_0], rbx
0x180006779  mov     [rsp+arg_8], rsi
0x18000677e  push    rdi
0x18000677f  sub     rsp, 60h
0x180006783  mov     rsi, [rsp+68h+arg_28]
0x18000678b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006792  mov     [rsp+68h+var_40], rsi; char *
0x180006797  mov     ebx, edx
0x180006799  mov     rdi, rcx
0x18000679c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800067a1  test    eax, eax
0x1800067a3  jle     short loc_1800067AD
0x1800067a5  movzx   eax, ax
0x1800067a8  or      eax, 80070000h
0x1800067ad  mov     ecx, eax; this
0x1800067af  mov     [rsp+68h+var_18], eax
0x1800067b3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800067b8  mov     [rsp+68h+var_14], eax
0x1800067bc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800067c3  lea     rax, [rsp+68h+var_18]
0x1800067c8  mov     [rsp+68h+var_30], 0
0x1800067d1  mov     [rsp+68h+var_38], rax
0x1800067d6  mov     edx, ebx
0x1800067d8  mov     rcx, rdi
0x1800067db  mov     [rsp+68h+var_40], rsi
0x1800067e0  mov     [rsp+68h+var_10], 0
0x1800067e8  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
