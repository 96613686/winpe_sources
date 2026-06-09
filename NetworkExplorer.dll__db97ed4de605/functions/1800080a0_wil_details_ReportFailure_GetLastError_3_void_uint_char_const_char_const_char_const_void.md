# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800080a0`
- end: `0x18000810a`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `106`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c674`

## callees

- `0x180006f5c`
- `0x180007120`
- `0x180008074`
- `0x1800080a0`

## string_xrefs

- `0x1800080b7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v10; // r8d
  int v11; // r9d
  const char *v12; // [rsp+20h] [rbp-48h]
  int v13; // [rsp+20h] [rbp-48h]
  void *v14; // [rsp+30h] [rbp-38h]
  _DWORD v15[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v12,
                    a6,
                    v14);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v15[0] = LastErrorFail;
  v15[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  v15[2] = 0;
  wil::details::ReportFailure_Base<3,0>(v7, v6, v10, v11, v13, (__int64)a6, (__int64)v15);
}

```

## disassembly

```asm
0x1800080a0  mov     [rsp+arg_0], rbx
0x1800080a5  mov     [rsp+arg_8], rsi
0x1800080aa  push    rdi
0x1800080ab  sub     rsp, 60h
0x1800080af  mov     rsi, [rsp+68h+arg_28]
0x1800080b7  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800080be  mov     [rsp+68h+var_40], rsi; char *
0x1800080c3  mov     ebx, edx
0x1800080c5  mov     rdi, rcx
0x1800080c8  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800080cd  test    eax, eax
0x1800080cf  jle     short loc_1800080D9
0x1800080d1  movzx   eax, ax
0x1800080d4  or      eax, 80070000h
0x1800080d9  mov     ecx, eax; this
0x1800080db  mov     [rsp+68h+var_18], eax
0x1800080df  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800080e4  mov     [rsp+68h+var_14], eax
0x1800080e8  mov     edx, ebx
0x1800080ea  lea     rax, [rsp+68h+var_18]
0x1800080ef  mov     [rsp+68h+var_10], 0
0x1800080f7  mov     [rsp+68h+var_38], rax
0x1800080fc  mov     rcx, rdi
0x1800080ff  mov     [rsp+68h+var_40], rsi
0x180008104  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
