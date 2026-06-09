# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800077c4`
- end: `0x18000783e`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f078`

## callees

- `0x180004650`
- `0x180005a0c`
- `0x1800077c4`
- `0x18000c43c`

## string_xrefs

- `0x1800077db`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000780c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
0x1800077c4  mov     [rsp+arg_0], rbx
0x1800077c9  mov     [rsp+arg_8], rsi
0x1800077ce  push    rdi
0x1800077cf  sub     rsp, 60h
0x1800077d3  mov     rsi, [rsp+68h+arg_28]
0x1800077db  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800077e2  mov     [rsp+68h+var_40], rsi; char *
0x1800077e7  mov     ebx, edx
0x1800077e9  mov     rdi, rcx
0x1800077ec  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800077f1  test    eax, eax
0x1800077f3  jle     short loc_1800077FD
0x1800077f5  movzx   eax, ax
0x1800077f8  or      eax, 80070000h
0x1800077fd  mov     ecx, eax; this
0x1800077ff  mov     [rsp+68h+var_18], eax
0x180007803  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007808  mov     [rsp+68h+var_14], eax
0x18000780c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007813  lea     rax, [rsp+68h+var_18]
0x180007818  mov     [rsp+68h+var_30], 0
0x180007821  mov     [rsp+68h+var_38], rax
0x180007826  mov     edx, ebx
0x180007828  mov     rcx, rdi
0x18000782b  mov     [rsp+68h+var_40], rsi
0x180007830  mov     [rsp+68h+var_10], 0
0x180007838  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
