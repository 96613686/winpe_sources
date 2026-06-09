# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180051eb0`
- end: `0x180051f21`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180057e84`

## callees

- `0x180049648`
- `0x18004980c`
- `0x180051e84`
- `0x180051eb0`

## string_xrefs

- `0x180051ec7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180051ef8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v10; // [rsp+20h] [rbp-48h]
  int v11; // [rsp+20h] [rbp-48h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v10,
                    a6);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v12[0] = LastErrorFail;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail);
  v12[2] = 0;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v9,
    v11,
    (__int64)a6,
    (__int64)v12);
}

```

## disassembly

```asm
0x180051eb0  mov     [rsp+arg_0], rbx
0x180051eb5  mov     [rsp+arg_8], rsi
0x180051eba  push    rdi
0x180051ebb  sub     rsp, 60h
0x180051ebf  mov     rsi, [rsp+68h+arg_28]
0x180051ec7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180051ece  mov     [rsp+68h+var_40], rsi; char *
0x180051ed3  mov     ebx, edx
0x180051ed5  mov     rdi, rcx
0x180051ed8  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180051edd  test    eax, eax
0x180051edf  jle     short loc_180051EE9
0x180051ee1  movzx   eax, ax
0x180051ee4  or      eax, 80070000h
0x180051ee9  mov     ecx, eax; this
0x180051eeb  mov     [rsp+68h+var_18], eax
0x180051eef  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180051ef4  mov     [rsp+68h+var_14], eax
0x180051ef8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180051eff  lea     rax, [rsp+68h+var_18]
0x180051f04  mov     [rsp+68h+var_10], 0
0x180051f0c  mov     [rsp+68h+var_38], rax
0x180051f11  mov     edx, ebx
0x180051f13  mov     rcx, rdi
0x180051f16  mov     [rsp+68h+var_40], rsi
0x180051f1b  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
