# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180007c54`
- end: `0x180007cce`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e4b4`

## callees

- `0x180007c1c`
- `0x180007c54`
- `0x180009e40`
- `0x18000a3e8`

## string_xrefs

- `0x180007c6b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007c9c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180007c54  mov     [rsp+arg_0], rbx
0x180007c59  mov     [rsp+arg_8], rsi
0x180007c5e  push    rdi
0x180007c5f  sub     rsp, 60h
0x180007c63  mov     rsi, [rsp+68h+arg_28]
0x180007c6b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007c72  mov     [rsp+68h+var_40], rsi; char *
0x180007c77  mov     ebx, edx
0x180007c79  mov     rdi, rcx
0x180007c7c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180007c81  test    eax, eax
0x180007c83  jle     short loc_180007C8D
0x180007c85  movzx   eax, ax
0x180007c88  or      eax, 80070000h
0x180007c8d  mov     ecx, eax; this
0x180007c8f  mov     [rsp+68h+var_18], eax
0x180007c93  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007c98  mov     [rsp+68h+var_14], eax
0x180007c9c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007ca3  lea     rax, [rsp+68h+var_18]
0x180007ca8  mov     [rsp+68h+var_30], 0
0x180007cb1  mov     [rsp+68h+var_38], rax
0x180007cb6  mov     edx, ebx
0x180007cb8  mov     rcx, rdi
0x180007cbb  mov     [rsp+68h+var_40], rsi
0x180007cc0  mov     [rsp+68h+var_10], 0
0x180007cc8  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
