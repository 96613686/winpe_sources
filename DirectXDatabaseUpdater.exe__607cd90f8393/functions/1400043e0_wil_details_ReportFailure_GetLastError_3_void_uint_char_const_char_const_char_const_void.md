# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1400043e0`
- end: `0x14000445a`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000dc08`

## callees

- `0x140004200`
- `0x1400043e0`
- `0x1400074e0`
- `0x1400080fc`

## string_xrefs

- `0x1400043f7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140004428`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1400043e0  mov     [rsp+arg_0], rbx
0x1400043e5  mov     [rsp+arg_8], rsi
0x1400043ea  push    rdi
0x1400043eb  sub     rsp, 60h
0x1400043ef  mov     rsi, [rsp+68h+arg_28]
0x1400043f7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400043fe  mov     [rsp+68h+var_40], rsi; char *
0x140004403  mov     ebx, edx
0x140004405  mov     rdi, rcx
0x140004408  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x14000440d  test    eax, eax
0x14000440f  jle     short loc_140004419
0x140004411  movzx   eax, ax
0x140004414  or      eax, 80070000h
0x140004419  mov     ecx, eax; this
0x14000441b  mov     [rsp+68h+var_18], eax
0x14000441f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004424  mov     [rsp+68h+var_14], eax
0x140004428  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000442f  lea     rax, [rsp+68h+var_18]
0x140004434  mov     [rsp+68h+var_30], 0
0x14000443d  mov     [rsp+68h+var_38], rax
0x140004442  mov     edx, ebx
0x140004444  mov     rcx, rdi
0x140004447  mov     [rsp+68h+var_40], rsi
0x14000444c  mov     [rsp+68h+var_10], 0
0x140004454  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
