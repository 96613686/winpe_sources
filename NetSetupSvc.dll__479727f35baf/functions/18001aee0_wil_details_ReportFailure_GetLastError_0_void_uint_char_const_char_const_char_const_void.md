# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18001aee0`
- end: `0x18001af52`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `114`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180023614`

## callees

- `0x180004b60`
- `0x1800050e0`
- `0x18001aeb4`
- `0x18001aee0`

## string_xrefs

- `0x18001aef2`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001af26`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  signed int LastErrorFail; // eax
  int v8; // edx
  int v9; // r9d
  const char *v10; // [rsp+20h] [rbp-48h]
  int v11; // [rsp+20h] [rbp-48h]
  void *v12; // [rsp+30h] [rbp-38h]
  _DWORD v13[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x1CC8,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                    a4,
                    v10,
                    a6,
                    v12);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v13[0] = LastErrorFail;
  v13[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v8);
  v13[2] = 0;
  wil::details::ReportFailure_Base<0,0>(
    v6,
    7368,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
    v9,
    v11,
    (__int64)a6,
    (__int64)v13);
}

```

## disassembly

```asm
0x18001aee0  mov     [rsp+arg_0], rbx
0x18001aee5  push    rdi
0x18001aee6  sub     rsp, 60h
0x18001aeea  mov     rdi, [rsp+68h+arg_28]
0x18001aef2  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001aef9  mov     edx, 1CC8h; void *
0x18001aefe  mov     [rsp+68h+var_40], rdi; char *
0x18001af03  mov     rbx, rcx
0x18001af06  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18001af0b  test    eax, eax
0x18001af0d  jle     short loc_18001AF17
0x18001af0f  movzx   eax, ax
0x18001af12  or      eax, 80070000h
0x18001af17  mov     ecx, eax; this
0x18001af19  mov     [rsp+68h+var_18], eax
0x18001af1d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001af22  mov     [rsp+68h+var_14], eax
0x18001af26  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001af2d  lea     rax, [rsp+68h+var_18]
0x18001af32  mov     [rsp+68h+var_10], 0
0x18001af3a  mov     [rsp+68h+var_38], rax
0x18001af3f  mov     edx, 1CC8h
0x18001af44  mov     rcx, rbx
0x18001af47  mov     [rsp+68h+var_40], rdi
0x18001af4c  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
