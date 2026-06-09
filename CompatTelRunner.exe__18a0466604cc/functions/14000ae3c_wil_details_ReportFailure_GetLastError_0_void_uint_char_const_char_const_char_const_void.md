# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x14000ae3c`
- end: `0x14000aeb4`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `120`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000be5c`

## callees

- `0x140005678`
- `0x140006140`
- `0x14000ae10`
- `0x14000ae3c`

## string_xrefs

- `0x14000ae4e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x14000ae7f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

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
  __int64 v8; // rax
  __int64 v9; // xmm0_8
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-58h]
  int v12; // [rsp+20h] [rbp-58h]
  void *v13; // [rsp+30h] [rbp-48h]
  __int64 v14; // [rsp+50h] [rbp-28h] BYREF
  int v15; // [rsp+58h] [rbp-20h]
  _BYTE v16[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x1CC8,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v8 = wil::details::ResultStatus::FromResult(v16, (unsigned int)LastErrorFail);
  v9 = *(_QWORD *)v8;
  v15 = *(_DWORD *)(v8 + 8);
  v14 = v9;
  wil::details::ReportFailure_Base<0,0>(
    v6,
    7368,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
    v10,
    v12,
    (__int64)a6,
    (__int64)&v14);
}

```

## disassembly

```asm
0x14000ae3c  mov     [rsp+arg_0], rbx
0x14000ae41  push    rdi
0x14000ae42  sub     rsp, 70h
0x14000ae46  mov     rdi, [rsp+78h+arg_28]
0x14000ae4e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000ae55  mov     edx, 1CC8h; void *
0x14000ae5a  mov     [rsp+78h+var_50], rdi; char *
0x14000ae5f  mov     rbx, rcx
0x14000ae62  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x14000ae67  test    eax, eax
0x14000ae69  jle     short loc_14000AE73
0x14000ae6b  movzx   eax, ax
0x14000ae6e  or      eax, 80070000h
0x14000ae73  mov     edx, eax
0x14000ae75  lea     rcx, [rsp+78h+var_18]
0x14000ae7a  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000ae7f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000ae86  mov     edx, 1CC8h
0x14000ae8b  mov     rcx, rbx
0x14000ae8e  movsd   xmm0, qword ptr [rax]
0x14000ae92  mov     eax, [rax+8]
0x14000ae95  mov     [rsp+78h+var_20], eax
0x14000ae99  lea     rax, [rsp+78h+var_28]
0x14000ae9e  mov     [rsp+78h+var_48], rax
0x14000aea3  mov     [rsp+78h+var_50], rdi
0x14000aea8  movsd   [rsp+78h+var_28], xmm0
0x14000aeae  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
