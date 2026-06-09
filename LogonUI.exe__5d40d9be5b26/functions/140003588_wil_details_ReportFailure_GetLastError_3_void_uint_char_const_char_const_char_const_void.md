# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140003588`
- end: `0x1400035f9`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140006f68`

## callees

- `0x140002194`
- `0x140002358`
- `0x14000355c`
- `0x140003588`

## string_xrefs

- `0x14000359f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400035d0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]
  _DWORD v14[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v14[0] = LastErrorFail;
  v14[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  v14[2] = 0;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v10,
    v12,
    (__int64)a6,
    (__int64)v14);
}

```

## disassembly

```asm
0x140003588  mov     [rsp+arg_0], rbx
0x14000358d  mov     [rsp+arg_8], rsi
0x140003592  push    rdi
0x140003593  sub     rsp, 60h
0x140003597  mov     rsi, [rsp+68h+arg_28]
0x14000359f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400035a6  mov     [rsp+68h+var_40], rsi; char *
0x1400035ab  mov     ebx, edx
0x1400035ad  mov     rdi, rcx
0x1400035b0  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1400035b5  test    eax, eax
0x1400035b7  jle     short loc_1400035C1
0x1400035b9  movzx   eax, ax
0x1400035bc  or      eax, 80070000h
0x1400035c1  mov     ecx, eax; this
0x1400035c3  mov     [rsp+68h+var_18], eax
0x1400035c7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400035cc  mov     [rsp+68h+var_14], eax
0x1400035d0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400035d7  lea     rax, [rsp+68h+var_18]
0x1400035dc  mov     [rsp+68h+var_10], 0
0x1400035e4  mov     [rsp+68h+var_38], rax
0x1400035e9  mov     edx, ebx
0x1400035eb  mov     rcx, rdi
0x1400035ee  mov     [rsp+68h+var_40], rsi
0x1400035f3  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
