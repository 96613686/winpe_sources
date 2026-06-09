# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000bc58`
- end: `0x18000bcc4`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `108`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c410`

## callees

- `0x18000505c`
- `0x180005450`
- `0x18000bc2c`
- `0x18000bc58`

## string_xrefs

- `0x18000bc6a`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  signed int LastErrorFail; // eax
  __int64 v8; // rax
  __int64 v9; // xmm0_8
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  const char *v13; // [rsp+20h] [rbp-58h]
  int v14; // [rsp+20h] [rbp-58h]
  void *v15; // [rsp+30h] [rbp-48h]
  __int64 v16; // [rsp+50h] [rbp-28h] BYREF
  int v17; // [rsp+58h] [rbp-20h]
  _BYTE v18[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x1CC8,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                    a4,
                    v13,
                    a6,
                    v15);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v8 = wil::details::ResultStatus::FromResult(v18, (unsigned int)LastErrorFail);
  v9 = *(_QWORD *)v8;
  v17 = *(_DWORD *)(v8 + 8);
  v16 = v9;
  wil::details::ReportFailure_Base<0,0>(v6, v10, v11, v12, v14, (__int64)a6, (__int64)&v16);
}

```

## disassembly

```asm
0x18000bc58  mov     [rsp+arg_0], rbx
0x18000bc5d  push    rdi
0x18000bc5e  sub     rsp, 70h
0x18000bc62  mov     rdi, [rsp+78h+arg_28]
0x18000bc6a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bc71  mov     edx, 1CC8h; void *
0x18000bc76  mov     [rsp+78h+var_50], rdi; char *
0x18000bc7b  mov     rbx, rcx
0x18000bc7e  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000bc83  test    eax, eax
0x18000bc85  jle     short loc_18000BC8F
0x18000bc87  movzx   eax, ax
0x18000bc8a  or      eax, 80070000h
0x18000bc8f  mov     edx, eax
0x18000bc91  lea     rcx, [rsp+78h+var_18]
0x18000bc96  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18000bc9b  mov     rcx, rbx
0x18000bc9e  movsd   xmm0, qword ptr [rax]
0x18000bca2  mov     eax, [rax+8]
0x18000bca5  mov     [rsp+78h+var_20], eax
0x18000bca9  lea     rax, [rsp+78h+var_28]
0x18000bcae  mov     [rsp+78h+var_48], rax
0x18000bcb3  mov     [rsp+78h+var_50], rdi
0x18000bcb8  movsd   [rsp+78h+var_28], xmm0
0x18000bcbe  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
