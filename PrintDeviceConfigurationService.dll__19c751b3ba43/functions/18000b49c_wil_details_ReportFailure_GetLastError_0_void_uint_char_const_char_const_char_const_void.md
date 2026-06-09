# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000b49c`
- end: `0x18000b517`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `123`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c13c`

## callees

- `0x180006250`
- `0x1800067a0`
- `0x18000b140`
- `0x18000b49c`

## string_xrefs

- `0x18000b4ae`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18000b4e2`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

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
    (__int64)v13,
    0);
}

```

## disassembly

```asm
0x18000b49c  mov     [rsp+arg_0], rbx
0x18000b4a1  push    rdi
0x18000b4a2  sub     rsp, 60h
0x18000b4a6  mov     rdi, [rsp+68h+arg_28]
0x18000b4ae  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b4b5  mov     edx, 1CC8h; void *
0x18000b4ba  mov     [rsp+68h+var_40], rdi; char *
0x18000b4bf  mov     rbx, rcx
0x18000b4c2  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000b4c7  test    eax, eax
0x18000b4c9  jle     short loc_18000B4D3
0x18000b4cb  movzx   eax, ax
0x18000b4ce  or      eax, 80070000h
0x18000b4d3  mov     ecx, eax; this
0x18000b4d5  mov     [rsp+68h+var_18], eax
0x18000b4d9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b4de  mov     [rsp+68h+var_14], eax
0x18000b4e2  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b4e9  lea     rax, [rsp+68h+var_18]
0x18000b4ee  mov     [rsp+68h+var_30], 0
0x18000b4f7  mov     [rsp+68h+var_38], rax
0x18000b4fc  mov     edx, 1CC8h
0x18000b501  mov     rcx, rbx
0x18000b504  mov     [rsp+68h+var_40], rdi
0x18000b509  mov     [rsp+68h+var_10], 0
0x18000b511  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
