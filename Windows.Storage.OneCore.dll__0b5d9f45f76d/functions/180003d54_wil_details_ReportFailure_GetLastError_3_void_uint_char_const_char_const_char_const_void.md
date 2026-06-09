# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003d54`
- end: `0x180003dce`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009520`

## callees

- `0x180003d1c`
- `0x180003d54`
- `0x180005d50`
- `0x180006318`

## string_xrefs

- `0x180003d6b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180003d9c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-48h]
  void *v12; // [rsp+30h] [rbp-38h]

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v11,
                    a6,
                    v12);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v10);
}

```

## disassembly

```asm
0x180003d54  mov     [rsp+arg_0], rbx
0x180003d59  mov     [rsp+arg_8], rsi
0x180003d5e  push    rdi
0x180003d5f  sub     rsp, 60h
0x180003d63  mov     rsi, [rsp+68h+arg_28]
0x180003d6b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003d72  mov     [rsp+68h+var_40], rsi; char *
0x180003d77  mov     ebx, edx
0x180003d79  mov     rdi, rcx
0x180003d7c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180003d81  test    eax, eax
0x180003d83  jle     short loc_180003D8D
0x180003d85  movzx   eax, ax
0x180003d88  or      eax, 80070000h
0x180003d8d  mov     ecx, eax; this
0x180003d8f  mov     [rsp+68h+var_18], eax
0x180003d93  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003d98  mov     [rsp+68h+var_14], eax
0x180003d9c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003da3  lea     rax, [rsp+68h+var_18]
0x180003da8  mov     [rsp+68h+var_30], 0
0x180003db1  mov     [rsp+68h+var_38], rax
0x180003db6  mov     edx, ebx
0x180003db8  mov     rcx, rdi
0x180003dbb  mov     [rsp+68h+var_40], rsi
0x180003dc0  mov     [rsp+68h+var_10], 0
0x180003dc8  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
