# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140006d08`
- end: `0x140006d79`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b884`

## callees

- `0x140004ba0`
- `0x140004d64`
- `0x140006cdc`
- `0x140006d08`

## string_xrefs

- `0x140006d1f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140006d50`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140006d08  mov     [rsp+arg_0], rbx
0x140006d0d  mov     [rsp+arg_8], rsi
0x140006d12  push    rdi
0x140006d13  sub     rsp, 60h
0x140006d17  mov     rsi, [rsp+68h+arg_28]
0x140006d1f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006d26  mov     [rsp+68h+var_40], rsi; char *
0x140006d2b  mov     ebx, edx
0x140006d2d  mov     rdi, rcx
0x140006d30  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140006d35  test    eax, eax
0x140006d37  jle     short loc_140006D41
0x140006d39  movzx   eax, ax
0x140006d3c  or      eax, 80070000h
0x140006d41  mov     ecx, eax; this
0x140006d43  mov     [rsp+68h+var_18], eax
0x140006d47  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006d4c  mov     [rsp+68h+var_14], eax
0x140006d50  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006d57  lea     rax, [rsp+68h+var_18]
0x140006d5c  mov     [rsp+68h+var_10], 0
0x140006d64  mov     [rsp+68h+var_38], rax
0x140006d69  mov     edx, ebx
0x140006d6b  mov     rcx, rdi
0x140006d6e  mov     [rsp+68h+var_40], rsi
0x140006d73  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
