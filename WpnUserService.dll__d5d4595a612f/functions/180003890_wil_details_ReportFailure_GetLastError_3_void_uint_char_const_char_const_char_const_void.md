# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003890`
- end: `0x180003910`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800071a8`

## callees

- `0x180003858`
- `0x180003890`
- `0x180004d28`
- `0x180005270`

## string_xrefs

- `0x1800038a7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800038de`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180003890  mov     [rsp+arg_0], rbx
0x180003895  mov     [rsp+arg_8], rsi
0x18000389a  push    rdi
0x18000389b  sub     rsp, 70h
0x18000389f  mov     rsi, [rsp+78h+arg_28]
0x1800038a7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800038ae  mov     [rsp+78h+var_50], rsi; char *
0x1800038b3  mov     ebx, edx
0x1800038b5  mov     rdi, rcx
0x1800038b8  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800038bd  test    eax, eax
0x1800038bf  jle     short loc_1800038C9
0x1800038c1  movzx   eax, ax
0x1800038c4  or      eax, 80070000h
0x1800038c9  mov     edx, eax
0x1800038cb  lea     rcx, [rsp+78h+var_18]
0x1800038d0  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800038d5  mov     [rsp+78h+var_40], 0
0x1800038de  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800038e5  mov     edx, ebx
0x1800038e7  mov     rcx, rdi
0x1800038ea  movsd   xmm0, qword ptr [rax]
0x1800038ee  mov     eax, [rax+8]
0x1800038f1  mov     [rsp+78h+var_20], eax
0x1800038f5  lea     rax, [rsp+78h+var_28]
0x1800038fa  mov     [rsp+78h+var_48], rax
0x1800038ff  mov     [rsp+78h+var_50], rsi
0x180003904  movsd   [rsp+78h+var_28], xmm0
0x18000390a  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
