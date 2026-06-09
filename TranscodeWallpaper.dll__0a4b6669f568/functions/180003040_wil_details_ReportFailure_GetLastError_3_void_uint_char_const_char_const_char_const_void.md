# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003040`
- end: `0x1800030c0`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000698c`

## callees

- `0x180002ec4`
- `0x180003040`
- `0x1800045e8`
- `0x180004b30`

## string_xrefs

- `0x180003057`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000308e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v11; // r9d
  const char *v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  void *v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  int v16; // [rsp+58h] [rbp-20h]
  _BYTE v17[24]; // [rsp+60h] [rbp-18h] BYREF

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
  v9 = wil::details::ResultStatus::FromResult(v17, (unsigned int)LastErrorFail);
  v10 = *(_QWORD *)v9;
  v16 = *(_DWORD *)(v9 + 8);
  v15 = v10;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15,
    0);
}

```

## disassembly

```asm
0x180003040  mov     [rsp+arg_0], rbx
0x180003045  mov     [rsp+arg_8], rsi
0x18000304a  push    rdi
0x18000304b  sub     rsp, 70h
0x18000304f  mov     rsi, [rsp+78h+arg_28]
0x180003057  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000305e  mov     [rsp+78h+var_50], rsi; char *
0x180003063  mov     ebx, edx
0x180003065  mov     rdi, rcx
0x180003068  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000306d  test    eax, eax
0x18000306f  jle     short loc_180003079
0x180003071  movzx   eax, ax
0x180003074  or      eax, 80070000h
0x180003079  mov     edx, eax
0x18000307b  lea     rcx, [rsp+78h+var_18]
0x180003080  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180003085  mov     [rsp+78h+var_40], 0
0x18000308e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003095  mov     edx, ebx
0x180003097  mov     rcx, rdi
0x18000309a  movsd   xmm0, qword ptr [rax]
0x18000309e  mov     eax, [rax+8]
0x1800030a1  mov     [rsp+78h+var_20], eax
0x1800030a5  lea     rax, [rsp+78h+var_28]
0x1800030aa  mov     [rsp+78h+var_48], rax
0x1800030af  mov     [rsp+78h+var_50], rsi
0x1800030b4  movsd   [rsp+78h+var_28], xmm0
0x1800030ba  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
