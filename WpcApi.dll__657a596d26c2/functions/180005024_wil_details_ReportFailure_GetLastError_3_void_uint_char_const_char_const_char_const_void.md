# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180005024`
- end: `0x1800050a4`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a8ec`

## callees

- `0x180004fec`
- `0x180005024`
- `0x180007218`
- `0x180007a30`

## string_xrefs

- `0x18000503b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005072`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180005024  mov     [rsp+arg_0], rbx
0x180005029  mov     [rsp+arg_8], rsi
0x18000502e  push    rdi
0x18000502f  sub     rsp, 70h
0x180005033  mov     rsi, [rsp+78h+arg_28]
0x18000503b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005042  mov     [rsp+78h+var_50], rsi; char *
0x180005047  mov     ebx, edx
0x180005049  mov     rdi, rcx
0x18000504c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180005051  test    eax, eax
0x180005053  jle     short loc_18000505D
0x180005055  movzx   eax, ax
0x180005058  or      eax, 80070000h
0x18000505d  mov     edx, eax
0x18000505f  lea     rcx, [rsp+78h+var_18]
0x180005064  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180005069  mov     [rsp+78h+var_40], 0
0x180005072  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005079  mov     edx, ebx
0x18000507b  mov     rcx, rdi
0x18000507e  movsd   xmm0, qword ptr [rax]
0x180005082  mov     eax, [rax+8]
0x180005085  mov     [rsp+78h+var_20], eax
0x180005089  lea     rax, [rsp+78h+var_28]
0x18000508e  mov     [rsp+78h+var_48], rax
0x180005093  mov     [rsp+78h+var_50], rsi
0x180005098  movsd   [rsp+78h+var_28], xmm0
0x18000509e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
