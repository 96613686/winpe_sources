# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x14000220c`
- end: `0x1400022a0`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400076ec`

## callees

- `0x140002064`
- `0x14000220c`
- `0x140004418`
- `0x140004960`

## string_xrefs

- `0x14000221f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140002266`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        char *a5,
        char *a6)
{
  int v6; // ebx
  int v7; // edi
  int v8; // esi
  signed int LastErrorFail; // eax
  __int64 v10; // rax
  __int64 v11; // xmm0_8
  void *v12; // [rsp+30h] [rbp-68h]
  __int64 v13; // [rsp+50h] [rbp-48h] BYREF
  int v14; // [rsp+58h] [rbp-40h]
  _BYTE v15[56]; // [rsp+60h] [rbp-38h] BYREF

  v6 = (int)a4;
  v7 = (int)a2;
  v8 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    a5,
                    a6,
                    v12);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v10 = wil::details::ResultStatus::FromResult(v15, (unsigned int)LastErrorFail);
  v11 = *(_QWORD *)v10;
  v14 = *(_DWORD *)(v10 + 8);
  v13 = v11;
  wil::details::ReportFailure_Base<3,0>(
    v8,
    v7,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6,
    (__int64)a5,
    (__int64)a6,
    (__int64)&v13,
    0);
}

```

## disassembly

```asm
0x14000220c  push    rbx
0x14000220e  push    rbp
0x14000220f  push    rsi
0x140002210  push    rdi
0x140002211  push    r14
0x140002213  sub     rsp, 70h
0x140002217  mov     rbp, [rsp+98h+arg_28]
0x14000221f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002226  mov     r14, [rsp+98h+arg_20]
0x14000222e  mov     rbx, r9
0x140002231  mov     [rsp+98h+var_70], rbp; char *
0x140002236  mov     edi, edx
0x140002238  mov     [rsp+98h+var_78], r14; char *
0x14000223d  mov     rsi, rcx
0x140002240  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140002245  test    eax, eax
0x140002247  jle     short loc_140002251
0x140002249  movzx   eax, ax
0x14000224c  or      eax, 80070000h
0x140002251  mov     edx, eax
0x140002253  lea     rcx, [rsp+98h+var_38]
0x140002258  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000225d  mov     [rsp+98h+var_60], 0
0x140002266  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000226d  mov     r9, rbx
0x140002270  mov     edx, edi
0x140002272  mov     rcx, rsi
0x140002275  movsd   xmm0, qword ptr [rax]
0x140002279  mov     eax, [rax+8]
0x14000227c  mov     [rsp+98h+var_40], eax
0x140002280  lea     rax, [rsp+98h+var_48]
0x140002285  mov     [rsp+98h+var_68], rax
0x14000228a  mov     [rsp+98h+var_70], rbp
0x14000228f  mov     [rsp+98h+var_78], r14
0x140002294  movsd   [rsp+98h+var_48], xmm0
0x14000229a  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
