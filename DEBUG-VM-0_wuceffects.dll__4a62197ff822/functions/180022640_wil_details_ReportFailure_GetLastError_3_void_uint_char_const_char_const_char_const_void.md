# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180022640`
- end: `0x1800226ba`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180024f9c`

## callees

- `0x18001ce54`
- `0x18001dba4`
- `0x18002247c`
- `0x180022640`

## string_xrefs

- `0x180022657`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180022688`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-48h]
  int v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]
  _DWORD v14[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v14[0] = LastErrorFail;
  v14[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  v14[2] = 0;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v10,
    v12,
    (__int64)a6,
    (__int64)v14,
    0);
}

```

## disassembly

```asm
0x180022640  mov     [rsp+arg_0], rbx
0x180022645  mov     [rsp+arg_8], rsi
0x18002264a  push    rdi
0x18002264b  sub     rsp, 60h
0x18002264f  mov     rsi, [rsp+68h+arg_28]
0x180022657  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002265e  mov     [rsp+68h+var_40], rsi; char *
0x180022663  mov     ebx, edx
0x180022665  mov     rdi, rcx
0x180022668  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18002266d  test    eax, eax
0x18002266f  jle     short loc_180022679
0x180022671  movzx   eax, ax
0x180022674  or      eax, 80070000h
0x180022679  mov     ecx, eax; this
0x18002267b  mov     [rsp+68h+var_18], eax
0x18002267f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180022684  mov     [rsp+68h+var_14], eax
0x180022688  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002268f  lea     rax, [rsp+68h+var_18]
0x180022694  mov     [rsp+68h+var_30], 0
0x18002269d  mov     [rsp+68h+var_38], rax
0x1800226a2  mov     edx, ebx
0x1800226a4  mov     rcx, rdi
0x1800226a7  mov     [rsp+68h+var_40], rsi
0x1800226ac  mov     [rsp+68h+var_10], 0
0x1800226b4  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
