# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140002b2c`
- end: `0x140002ba6`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005b74`

## callees

- `0x140002af4`
- `0x140002b2c`
- `0x140003f50`
- `0x1400044bc`

## string_xrefs

- `0x140002b43`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140002b74`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v10,
    v12,
    (__int64)a6,
    (__int64)v14,
    0);
}

```

## disassembly

```asm
0x140002b2c  mov     [rsp+arg_0], rbx
0x140002b31  mov     [rsp+arg_8], rsi
0x140002b36  push    rdi
0x140002b37  sub     rsp, 60h
0x140002b3b  mov     rsi, [rsp+68h+arg_28]
0x140002b43  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002b4a  mov     [rsp+68h+var_40], rsi; char *
0x140002b4f  mov     ebx, edx
0x140002b51  mov     rdi, rcx
0x140002b54  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140002b59  test    eax, eax
0x140002b5b  jle     short loc_140002B65
0x140002b5d  movzx   eax, ax
0x140002b60  or      eax, 80070000h
0x140002b65  mov     ecx, eax; this
0x140002b67  mov     [rsp+68h+var_18], eax
0x140002b6b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002b70  mov     [rsp+68h+var_14], eax
0x140002b74  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002b7b  lea     rax, [rsp+68h+var_18]
0x140002b80  mov     [rsp+68h+var_30], 0
0x140002b89  mov     [rsp+68h+var_38], rax
0x140002b8e  mov     edx, ebx
0x140002b90  mov     rcx, rdi
0x140002b93  mov     [rsp+68h+var_40], rsi
0x140002b98  mov     [rsp+68h+var_10], 0
0x140002ba0  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
