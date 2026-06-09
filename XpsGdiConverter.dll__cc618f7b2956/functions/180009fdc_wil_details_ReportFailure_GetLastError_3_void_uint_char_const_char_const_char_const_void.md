# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180009fdc`
- end: `0x18000a04d`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cd68`

## callees

- `0x180009fb0`
- `0x180009fdc`
- `0x18000b430`
- `0x18000b948`

## string_xrefs

- `0x180009ff3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a024`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180009fdc  mov     [rsp+arg_0], rbx
0x180009fe1  mov     [rsp+arg_8], rsi
0x180009fe6  push    rdi
0x180009fe7  sub     rsp, 60h
0x180009feb  mov     rsi, [rsp+68h+arg_28]
0x180009ff3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009ffa  mov     [rsp+68h+var_40], rsi; char *
0x180009fff  mov     ebx, edx
0x18000a001  mov     rdi, rcx
0x18000a004  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000a009  test    eax, eax
0x18000a00b  jle     short loc_18000A015
0x18000a00d  movzx   eax, ax
0x18000a010  or      eax, 80070000h
0x18000a015  mov     ecx, eax; this
0x18000a017  mov     [rsp+68h+var_18], eax
0x18000a01b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a020  mov     [rsp+68h+var_14], eax
0x18000a024  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a02b  lea     rax, [rsp+68h+var_18]
0x18000a030  mov     [rsp+68h+var_10], 0
0x18000a038  mov     [rsp+68h+var_38], rax
0x18000a03d  mov     edx, ebx
0x18000a03f  mov     rcx, rdi
0x18000a042  mov     [rsp+68h+var_40], rsi
0x18000a047  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
