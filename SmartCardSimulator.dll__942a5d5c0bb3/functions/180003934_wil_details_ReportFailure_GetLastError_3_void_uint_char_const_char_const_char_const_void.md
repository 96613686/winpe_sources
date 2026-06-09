# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003934`
- end: `0x1800039ae`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800067c0`

## callees

- `0x1800038fc`
- `0x180003934`
- `0x180004ca0`
- `0x1800051b8`

## string_xrefs

- `0x18000394b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000397c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180003934  mov     [rsp+arg_0], rbx
0x180003939  mov     [rsp+arg_8], rsi
0x18000393e  push    rdi
0x18000393f  sub     rsp, 60h
0x180003943  mov     rsi, [rsp+68h+arg_28]
0x18000394b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003952  mov     [rsp+68h+var_40], rsi; char *
0x180003957  mov     ebx, edx
0x180003959  mov     rdi, rcx
0x18000395c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180003961  test    eax, eax
0x180003963  jle     short loc_18000396D
0x180003965  movzx   eax, ax
0x180003968  or      eax, 80070000h
0x18000396d  mov     ecx, eax; this
0x18000396f  mov     [rsp+68h+var_18], eax
0x180003973  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003978  mov     [rsp+68h+var_14], eax
0x18000397c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003983  lea     rax, [rsp+68h+var_18]
0x180003988  mov     [rsp+68h+var_30], 0
0x180003991  mov     [rsp+68h+var_38], rax
0x180003996  mov     edx, ebx
0x180003998  mov     rcx, rdi
0x18000399b  mov     [rsp+68h+var_40], rsi
0x1800039a0  mov     [rsp+68h+var_10], 0
0x1800039a8  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
