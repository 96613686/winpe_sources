# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180017a38`
- end: `0x180017ab8`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019e9c`

## callees

- `0x180009084`
- `0x180009a20`
- `0x180017a38`
- `0x180018614`

## string_xrefs

- `0x180017a4f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180017a86`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180017a38  mov     [rsp+arg_0], rbx
0x180017a3d  mov     [rsp+arg_8], rsi
0x180017a42  push    rdi
0x180017a43  sub     rsp, 70h
0x180017a47  mov     rsi, [rsp+78h+arg_28]
0x180017a4f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017a56  mov     [rsp+78h+var_50], rsi; char *
0x180017a5b  mov     ebx, edx
0x180017a5d  mov     rdi, rcx
0x180017a60  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180017a65  test    eax, eax
0x180017a67  jle     short loc_180017A71
0x180017a69  movzx   eax, ax
0x180017a6c  or      eax, 80070000h
0x180017a71  mov     edx, eax
0x180017a73  lea     rcx, [rsp+78h+var_18]
0x180017a78  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180017a7d  mov     [rsp+78h+var_40], 0
0x180017a86  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017a8d  mov     edx, ebx
0x180017a8f  mov     rcx, rdi
0x180017a92  movsd   xmm0, qword ptr [rax]
0x180017a96  mov     eax, [rax+8]
0x180017a99  mov     [rsp+78h+var_20], eax
0x180017a9d  lea     rax, [rsp+78h+var_28]
0x180017aa2  mov     [rsp+78h+var_48], rax
0x180017aa7  mov     [rsp+78h+var_50], rsi
0x180017aac  movsd   [rsp+78h+var_28], xmm0
0x180017ab2  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
