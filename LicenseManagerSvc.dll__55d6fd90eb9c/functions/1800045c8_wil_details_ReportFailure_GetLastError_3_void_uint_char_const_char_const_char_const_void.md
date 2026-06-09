# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800045c8`
- end: `0x180004642`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007568`

## callees

- `0x180001c34`
- `0x180002c18`
- `0x1800043d8`
- `0x1800045c8`

## string_xrefs

- `0x1800045df`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004610`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800045c8  mov     [rsp+arg_0], rbx
0x1800045cd  mov     [rsp+arg_8], rsi
0x1800045d2  push    rdi
0x1800045d3  sub     rsp, 60h
0x1800045d7  mov     rsi, [rsp+68h+arg_28]
0x1800045df  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800045e6  mov     [rsp+68h+var_40], rsi; char *
0x1800045eb  mov     ebx, edx
0x1800045ed  mov     rdi, rcx
0x1800045f0  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800045f5  test    eax, eax
0x1800045f7  jle     short loc_180004601
0x1800045f9  movzx   eax, ax
0x1800045fc  or      eax, 80070000h
0x180004601  mov     ecx, eax; this
0x180004603  mov     [rsp+68h+var_18], eax
0x180004607  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000460c  mov     [rsp+68h+var_14], eax
0x180004610  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004617  lea     rax, [rsp+68h+var_18]
0x18000461c  mov     [rsp+68h+var_30], 0
0x180004625  mov     [rsp+68h+var_38], rax
0x18000462a  mov     edx, ebx
0x18000462c  mov     rcx, rdi
0x18000462f  mov     [rsp+68h+var_40], rsi
0x180004634  mov     [rsp+68h+var_10], 0
0x18000463c  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
