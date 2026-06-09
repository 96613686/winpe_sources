# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000268c`
- end: `0x1800026fc`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `112`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800078f4`

## callees

- `0x180002660`
- `0x18000268c`
- `0x180004168`
- `0x1800045f0`

## string_xrefs

- `0x1800026a3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v9; // rax
  __int64 v10; // xmm0_8
  int v11; // r8d
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
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v9 = wil::details::ResultStatus::FromResult(v18, (unsigned int)LastErrorFail);
  v10 = *(_QWORD *)v9;
  v17 = *(_DWORD *)(v9 + 8);
  v16 = v10;
  wil::details::ReportFailure_Base<3,0>(v7, v6, v11, v12, v14, (__int64)a6, (__int64)&v16);
}

```

## disassembly

```asm
0x18000268c  mov     [rsp+arg_0], rbx
0x180002691  mov     [rsp+arg_8], rsi
0x180002696  push    rdi
0x180002697  sub     rsp, 70h
0x18000269b  mov     rsi, [rsp+78h+arg_28]
0x1800026a3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800026aa  mov     [rsp+78h+var_50], rsi; char *
0x1800026af  mov     ebx, edx
0x1800026b1  mov     rdi, rcx
0x1800026b4  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800026b9  test    eax, eax
0x1800026bb  jle     short loc_1800026C5
0x1800026bd  movzx   eax, ax
0x1800026c0  or      eax, 80070000h
0x1800026c5  mov     edx, eax
0x1800026c7  lea     rcx, [rsp+78h+var_18]
0x1800026cc  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800026d1  mov     edx, ebx
0x1800026d3  mov     rcx, rdi
0x1800026d6  movsd   xmm0, qword ptr [rax]
0x1800026da  mov     eax, [rax+8]
0x1800026dd  mov     [rsp+78h+var_20], eax
0x1800026e1  lea     rax, [rsp+78h+var_28]
0x1800026e6  mov     [rsp+78h+var_48], rax
0x1800026eb  mov     [rsp+78h+var_50], rsi
0x1800026f0  movsd   [rsp+78h+var_28], xmm0
0x1800026f6  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
