# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1400053b0`
- end: `0x140005430`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000e3a4`

## callees

- `0x1400051b4`
- `0x1400053b0`
- `0x140009538`
- `0x140009ad8`

## string_xrefs

- `0x1400053c7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400053fe`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // r9d
  const char *v10; // [rsp+20h] [rbp-58h]
  void *v11; // [rsp+30h] [rbp-48h]
  _BYTE v12[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v10,
                    a6,
                    v11);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  wil::details::ResultStatus::FromResult(v12, (unsigned int)LastErrorFail);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v9);
}

```

## disassembly

```asm
0x1400053b0  mov     [rsp+arg_0], rbx
0x1400053b5  mov     [rsp+arg_8], rsi
0x1400053ba  push    rdi
0x1400053bb  sub     rsp, 70h
0x1400053bf  mov     rsi, [rsp+78h+arg_28]
0x1400053c7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400053ce  mov     [rsp+78h+var_50], rsi; char *
0x1400053d3  mov     ebx, edx
0x1400053d5  mov     rdi, rcx
0x1400053d8  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1400053dd  test    eax, eax
0x1400053df  jle     short loc_1400053E9
0x1400053e1  movzx   eax, ax
0x1400053e4  or      eax, 80070000h
0x1400053e9  mov     edx, eax
0x1400053eb  lea     rcx, [rsp+78h+var_18]
0x1400053f0  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1400053f5  mov     [rsp+78h+var_40], 0
0x1400053fe  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005405  mov     edx, ebx
0x140005407  mov     rcx, rdi
0x14000540a  movsd   xmm0, qword ptr [rax]
0x14000540e  mov     eax, [rax+8]
0x140005411  mov     [rsp+78h+var_20], eax
0x140005415  lea     rax, [rsp+78h+var_28]
0x14000541a  mov     [rsp+78h+var_48], rax
0x14000541f  mov     [rsp+78h+var_50], rsi
0x140005424  movsd   [rsp+78h+var_28], xmm0
0x14000542a  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
