# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180008e04`
- end: `0x180008e6e`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `106`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b3d4`

## callees

- `0x180007c78`
- `0x180007e3c`
- `0x180008dd8`
- `0x180008e04`

## string_xrefs

- `0x180008e1b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180008e04  mov     [rsp+arg_0], rbx
0x180008e09  mov     [rsp+arg_8], rsi
0x180008e0e  push    rdi
0x180008e0f  sub     rsp, 60h
0x180008e13  mov     rsi, [rsp+68h+arg_28]
0x180008e1b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008e22  mov     [rsp+68h+var_40], rsi; char *
0x180008e27  mov     ebx, edx
0x180008e29  mov     rdi, rcx
0x180008e2c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180008e31  test    eax, eax
0x180008e33  jle     short loc_180008E3D
0x180008e35  movzx   eax, ax
0x180008e38  or      eax, 80070000h
0x180008e3d  mov     ecx, eax; this
0x180008e3f  mov     [rsp+68h+var_18], eax
0x180008e43  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008e48  mov     [rsp+68h+var_14], eax
0x180008e4c  mov     edx, ebx
0x180008e4e  lea     rax, [rsp+68h+var_18]
0x180008e53  mov     [rsp+68h+var_10], 0
0x180008e5b  mov     [rsp+68h+var_38], rax
0x180008e60  mov     rcx, rdi
0x180008e63  mov     [rsp+68h+var_40], rsi
0x180008e68  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
