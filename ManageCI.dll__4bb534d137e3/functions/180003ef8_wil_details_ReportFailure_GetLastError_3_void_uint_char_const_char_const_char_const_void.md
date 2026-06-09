# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003ef8`
- end: `0x180003f72`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000823c`

## callees

- `0x180003cf0`
- `0x180003ef8`
- `0x1800061e0`
- `0x180006744`

## string_xrefs

- `0x180003f0f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180003f40`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180003ef8  mov     [rsp+arg_0], rbx
0x180003efd  mov     [rsp+arg_8], rsi
0x180003f02  push    rdi
0x180003f03  sub     rsp, 60h
0x180003f07  mov     rsi, [rsp+68h+arg_28]
0x180003f0f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003f16  mov     [rsp+68h+var_40], rsi; char *
0x180003f1b  mov     ebx, edx
0x180003f1d  mov     rdi, rcx
0x180003f20  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180003f25  test    eax, eax
0x180003f27  jle     short loc_180003F31
0x180003f29  movzx   eax, ax
0x180003f2c  or      eax, 80070000h
0x180003f31  mov     ecx, eax; this
0x180003f33  mov     [rsp+68h+var_18], eax
0x180003f37  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003f3c  mov     [rsp+68h+var_14], eax
0x180003f40  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003f47  lea     rax, [rsp+68h+var_18]
0x180003f4c  mov     [rsp+68h+var_30], 0
0x180003f55  mov     [rsp+68h+var_38], rax
0x180003f5a  mov     edx, ebx
0x180003f5c  mov     rcx, rdi
0x180003f5f  mov     [rsp+68h+var_40], rsi
0x180003f64  mov     [rsp+68h+var_10], 0
0x180003f6c  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
