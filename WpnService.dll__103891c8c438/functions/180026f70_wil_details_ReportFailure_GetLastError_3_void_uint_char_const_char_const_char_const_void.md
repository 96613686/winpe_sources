# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180026f70`
- end: `0x180026fea`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180027d98`

## callees

- `0x180012edc`
- `0x1800227d0`
- `0x180023a60`
- `0x180026f70`

## string_xrefs

- `0x180026f87`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180026fb8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180026f70  mov     [rsp+arg_0], rbx
0x180026f75  mov     [rsp+arg_8], rsi
0x180026f7a  push    rdi
0x180026f7b  sub     rsp, 60h
0x180026f7f  mov     rsi, [rsp+68h+arg_28]
0x180026f87  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026f8e  mov     [rsp+68h+var_40], rsi; char *
0x180026f93  mov     ebx, edx
0x180026f95  mov     rdi, rcx
0x180026f98  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180026f9d  test    eax, eax
0x180026f9f  jle     short loc_180026FA9
0x180026fa1  movzx   eax, ax
0x180026fa4  or      eax, 80070000h
0x180026fa9  mov     ecx, eax; this
0x180026fab  mov     [rsp+68h+var_18], eax
0x180026faf  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180026fb4  mov     [rsp+68h+var_14], eax
0x180026fb8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026fbf  lea     rax, [rsp+68h+var_18]
0x180026fc4  mov     [rsp+68h+var_30], 0
0x180026fcd  mov     [rsp+68h+var_38], rax
0x180026fd2  mov     edx, ebx
0x180026fd4  mov     rcx, rdi
0x180026fd7  mov     [rsp+68h+var_40], rsi
0x180026fdc  mov     [rsp+68h+var_10], 0
0x180026fe4  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
