# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180002d60`
- end: `0x180002dd7`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `119`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002e24`

## callees

- `0x1800017d0`
- `0x180001e18`
- `0x180002cd8`

## string_xrefs

- `0x180002d77`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180002da5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v6; // edi
  int v7; // esi
  int LastErrorFail; // eax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // xmm0_8
  int v12; // r9d
  const char *v13; // [rsp+20h] [rbp-58h]
  int v14; // [rsp+20h] [rbp-58h]
  void *v15; // [rsp+30h] [rbp-48h]
  __int64 v16; // [rsp+50h] [rbp-28h] BYREF
  int v17; // [rsp+58h] [rbp-20h]
  _BYTE v18[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v13,
                    a6,
                    v15);
  v9 = (unsigned __int16)LastErrorFail | 0x80070000;
  if ( LastErrorFail <= 0 )
    v9 = (unsigned int)LastErrorFail;
  v10 = wil::details::ResultStatus::FromResult(v18, v9);
  v11 = *(_QWORD *)v10;
  v17 = *(_DWORD *)(v10 + 8);
  v16 = v11;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v12,
    v14,
    (__int64)a6,
    (__int64)&v16);
}

```

## disassembly

```asm
0x180002d60  mov     [rsp+arg_0], rbx
0x180002d65  mov     [rsp+arg_8], rsi
0x180002d6a  push    rdi
0x180002d6b  sub     rsp, 70h
0x180002d6f  mov     rbx, [rsp+78h+arg_28]
0x180002d77  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002d7e  mov     [rsp+78h+var_50], rbx; char *
0x180002d83  mov     edi, edx
0x180002d85  mov     rsi, rcx
0x180002d88  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180002d8d  movzx   edx, ax
0x180002d90  lea     rcx, [rsp+78h+var_18]
0x180002d95  or      edx, 80070000h
0x180002d9b  test    eax, eax
0x180002d9d  cmovle  edx, eax
0x180002da0  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180002da5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002dac  mov     edx, edi
0x180002dae  mov     rcx, rsi
0x180002db1  movsd   xmm0, qword ptr [rax]
0x180002db5  mov     eax, [rax+8]
0x180002db8  mov     [rsp+78h+var_20], eax
0x180002dbc  lea     rax, [rsp+78h+var_28]
0x180002dc1  mov     [rsp+78h+var_48], rax
0x180002dc6  mov     [rsp+78h+var_50], rbx
0x180002dcb  movsd   [rsp+78h+var_28], xmm0
0x180002dd1  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
