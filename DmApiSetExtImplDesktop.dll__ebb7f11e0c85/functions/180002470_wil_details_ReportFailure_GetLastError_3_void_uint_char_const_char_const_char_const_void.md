# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180002470`
- end: `0x1800024ea`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005acc`

## callees

- `0x1800022bc`
- `0x180002470`
- `0x180003bc0`
- `0x180004140`

## string_xrefs

- `0x180002487`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800024b8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180002470  mov     [rsp+arg_0], rbx
0x180002475  mov     [rsp+arg_8], rsi
0x18000247a  push    rdi
0x18000247b  sub     rsp, 60h
0x18000247f  mov     rsi, [rsp+68h+arg_28]
0x180002487  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000248e  mov     [rsp+68h+var_40], rsi; char *
0x180002493  mov     ebx, edx
0x180002495  mov     rdi, rcx
0x180002498  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000249d  test    eax, eax
0x18000249f  jle     short loc_1800024A9
0x1800024a1  movzx   eax, ax
0x1800024a4  or      eax, 80070000h
0x1800024a9  mov     ecx, eax; this
0x1800024ab  mov     [rsp+68h+var_18], eax
0x1800024af  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800024b4  mov     [rsp+68h+var_14], eax
0x1800024b8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800024bf  lea     rax, [rsp+68h+var_18]
0x1800024c4  mov     [rsp+68h+var_30], 0
0x1800024cd  mov     [rsp+68h+var_38], rax
0x1800024d2  mov     edx, ebx
0x1800024d4  mov     rcx, rdi
0x1800024d7  mov     [rsp+68h+var_40], rsi
0x1800024dc  mov     [rsp+68h+var_10], 0
0x1800024e4  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
