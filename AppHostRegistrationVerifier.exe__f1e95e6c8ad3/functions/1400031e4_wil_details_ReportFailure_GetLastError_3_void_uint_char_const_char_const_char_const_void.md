# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1400031e4`
- end: `0x14000325e`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000769c`

## callees

- `0x1400031ac`
- `0x1400031e4`
- `0x1400056d0`
- `0x140005c30`

## string_xrefs

- `0x1400031fb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000322c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1400031e4  mov     [rsp+arg_0], rbx
0x1400031e9  mov     [rsp+arg_8], rsi
0x1400031ee  push    rdi
0x1400031ef  sub     rsp, 60h
0x1400031f3  mov     rsi, [rsp+68h+arg_28]
0x1400031fb  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003202  mov     [rsp+68h+var_40], rsi; char *
0x140003207  mov     ebx, edx
0x140003209  mov     rdi, rcx
0x14000320c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140003211  test    eax, eax
0x140003213  jle     short loc_14000321D
0x140003215  movzx   eax, ax
0x140003218  or      eax, 80070000h
0x14000321d  mov     ecx, eax; this
0x14000321f  mov     [rsp+68h+var_18], eax
0x140003223  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003228  mov     [rsp+68h+var_14], eax
0x14000322c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003233  lea     rax, [rsp+68h+var_18]
0x140003238  mov     [rsp+68h+var_30], 0
0x140003241  mov     [rsp+68h+var_38], rax
0x140003246  mov     edx, ebx
0x140003248  mov     rcx, rdi
0x14000324b  mov     [rsp+68h+var_40], rsi
0x140003250  mov     [rsp+68h+var_10], 0
0x140003258  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
