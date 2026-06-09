# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18002bd14`
- end: `0x18002bd8e`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002c9c8`

## callees

- `0x18001d5b0`
- `0x180026500`
- `0x180028e9c`
- `0x18002bd14`

## string_xrefs

- `0x18002bd2b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002bd5c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18002bd14  mov     [rsp+arg_0], rbx
0x18002bd19  mov     [rsp+arg_8], rsi
0x18002bd1e  push    rdi
0x18002bd1f  sub     rsp, 60h
0x18002bd23  mov     rsi, [rsp+68h+arg_28]
0x18002bd2b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002bd32  mov     [rsp+68h+var_40], rsi; char *
0x18002bd37  mov     ebx, edx
0x18002bd39  mov     rdi, rcx
0x18002bd3c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18002bd41  test    eax, eax
0x18002bd43  jle     short loc_18002BD4D
0x18002bd45  movzx   eax, ax
0x18002bd48  or      eax, 80070000h
0x18002bd4d  mov     ecx, eax; this
0x18002bd4f  mov     [rsp+68h+var_18], eax
0x18002bd53  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002bd58  mov     [rsp+68h+var_14], eax
0x18002bd5c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002bd63  lea     rax, [rsp+68h+var_18]
0x18002bd68  mov     [rsp+68h+var_30], 0
0x18002bd71  mov     [rsp+68h+var_38], rax
0x18002bd76  mov     edx, ebx
0x18002bd78  mov     rcx, rdi
0x18002bd7b  mov     [rsp+68h+var_40], rsi
0x18002bd80  mov     [rsp+68h+var_10], 0
0x18002bd88  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
