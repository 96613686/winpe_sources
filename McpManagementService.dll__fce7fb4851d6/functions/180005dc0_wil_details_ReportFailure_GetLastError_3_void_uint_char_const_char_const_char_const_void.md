# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180005dc0`
- end: `0x180005e3a`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e0d8`

## callees

- `0x180005d50`
- `0x180005dc0`
- `0x1800095d0`
- `0x180009d64`

## string_xrefs

- `0x180005dd7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005e08`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180005dc0  mov     [rsp+arg_0], rbx
0x180005dc5  mov     [rsp+arg_8], rsi
0x180005dca  push    rdi
0x180005dcb  sub     rsp, 60h
0x180005dcf  mov     rsi, [rsp+68h+arg_28]
0x180005dd7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005dde  mov     [rsp+68h+var_40], rsi; char *
0x180005de3  mov     ebx, edx
0x180005de5  mov     rdi, rcx
0x180005de8  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180005ded  test    eax, eax
0x180005def  jle     short loc_180005DF9
0x180005df1  movzx   eax, ax
0x180005df4  or      eax, 80070000h
0x180005df9  mov     ecx, eax; this
0x180005dfb  mov     [rsp+68h+var_18], eax
0x180005dff  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005e04  mov     [rsp+68h+var_14], eax
0x180005e08  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005e0f  lea     rax, [rsp+68h+var_18]
0x180005e14  mov     [rsp+68h+var_30], 0
0x180005e1d  mov     [rsp+68h+var_38], rax
0x180005e22  mov     edx, ebx
0x180005e24  mov     rcx, rdi
0x180005e27  mov     [rsp+68h+var_40], rsi
0x180005e2c  mov     [rsp+68h+var_10], 0
0x180005e34  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
