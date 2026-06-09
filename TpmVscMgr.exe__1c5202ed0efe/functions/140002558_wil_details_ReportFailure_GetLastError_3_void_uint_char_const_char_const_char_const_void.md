# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140002558`
- end: `0x1400025d8`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005bbc`

## callees

- `0x140002520`
- `0x140002558`
- `0x1400038c8`
- `0x140003e10`

## string_xrefs

- `0x14000256f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400025a6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140002558  mov     [rsp+arg_0], rbx
0x14000255d  mov     [rsp+arg_8], rsi
0x140002562  push    rdi
0x140002563  sub     rsp, 70h
0x140002567  mov     rsi, [rsp+78h+arg_28]
0x14000256f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002576  mov     [rsp+78h+var_50], rsi; char *
0x14000257b  mov     ebx, edx
0x14000257d  mov     rdi, rcx
0x140002580  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140002585  test    eax, eax
0x140002587  jle     short loc_140002591
0x140002589  movzx   eax, ax
0x14000258c  or      eax, 80070000h
0x140002591  mov     edx, eax
0x140002593  lea     rcx, [rsp+78h+var_18]
0x140002598  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000259d  mov     [rsp+78h+var_40], 0
0x1400025a6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400025ad  mov     edx, ebx
0x1400025af  mov     rcx, rdi
0x1400025b2  movsd   xmm0, qword ptr [rax]
0x1400025b6  mov     eax, [rax+8]
0x1400025b9  mov     [rsp+78h+var_20], eax
0x1400025bd  lea     rax, [rsp+78h+var_28]
0x1400025c2  mov     [rsp+78h+var_48], rax
0x1400025c7  mov     [rsp+78h+var_50], rsi
0x1400025cc  movsd   [rsp+78h+var_28], xmm0
0x1400025d2  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
