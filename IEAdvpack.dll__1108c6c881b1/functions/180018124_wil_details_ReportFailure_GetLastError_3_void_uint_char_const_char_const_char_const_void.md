# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180018124`
- end: `0x18001818e`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `106`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b064`

## callees

- `0x1800180f8`
- `0x180018124`
- `0x1800192f0`
- `0x1800196dc`

## string_xrefs

- `0x18001813b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  const char *v12; // [rsp+20h] [rbp-48h]
  int v13; // [rsp+20h] [rbp-48h]
  void *v14; // [rsp+30h] [rbp-38h]
  _DWORD v15[6]; // [rsp+50h] [rbp-18h] BYREF

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
  v15[0] = LastErrorFail;
  v15[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  v15[2] = 0;
  wil::details::ReportFailure_Base<3,0>(v7, v6, v10, v11, v13, (__int64)a6, (__int64)v15);
}

```

## disassembly

```asm
0x180018124  mov     [rsp+arg_0], rbx
0x180018129  mov     [rsp+arg_8], rsi
0x18001812e  push    rdi
0x18001812f  sub     rsp, 60h
0x180018133  mov     rsi, [rsp+68h+arg_28]
0x18001813b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018142  mov     [rsp+68h+var_40], rsi; char *
0x180018147  mov     ebx, edx
0x180018149  mov     rdi, rcx
0x18001814c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180018151  test    eax, eax
0x180018153  jle     short loc_18001815D
0x180018155  movzx   eax, ax
0x180018158  or      eax, 80070000h
0x18001815d  mov     ecx, eax; this
0x18001815f  mov     [rsp+68h+var_18], eax
0x180018163  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180018168  mov     [rsp+68h+var_14], eax
0x18001816c  mov     edx, ebx
0x18001816e  lea     rax, [rsp+68h+var_18]
0x180018173  mov     [rsp+68h+var_10], 0
0x18001817b  mov     [rsp+68h+var_38], rax
0x180018180  mov     rcx, rdi
0x180018183  mov     [rsp+68h+var_40], rsi
0x180018188  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
