# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18002345c`
- end: `0x1800234d3`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `119`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180028d00`

## callees

- `0x180023430`
- `0x18002345c`
- `0x1800254b4`
- `0x180025af8`

## string_xrefs

- `0x180023473`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800234a1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v14; // [rsp+50h] [rbp-28h] BYREF
  int v15; // [rsp+58h] [rbp-20h]
  unsigned int v16[6]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v12,
                    a6);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v9 = wil::details::ResultStatus::FromResult(v16, LastErrorFail);
  v10 = *(_QWORD *)v9;
  v15 = *(_DWORD *)(v9 + 8);
  v14 = v10;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v14);
}

```

## disassembly

```asm
0x18002345c  mov     [rsp+arg_0], rbx
0x180023461  mov     [rsp+arg_8], rsi
0x180023466  push    rdi
0x180023467  sub     rsp, 70h
0x18002346b  mov     rsi, [rsp+78h+arg_28]
0x180023473  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002347a  mov     [rsp+78h+var_50], rsi; char *
0x18002347f  mov     ebx, edx
0x180023481  mov     rdi, rcx
0x180023484  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180023489  test    eax, eax
0x18002348b  jle     short loc_180023495
0x18002348d  movzx   eax, ax
0x180023490  or      eax, 80070000h
0x180023495  mov     edx, eax
0x180023497  lea     rcx, [rsp+78h+var_18]
0x18002349c  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800234a1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800234a8  mov     edx, ebx
0x1800234aa  mov     rcx, rdi
0x1800234ad  movsd   xmm0, qword ptr [rax]
0x1800234b1  mov     eax, [rax+8]
0x1800234b4  mov     [rsp+78h+var_20], eax
0x1800234b8  lea     rax, [rsp+78h+var_28]
0x1800234bd  mov     [rsp+78h+var_48], rax
0x1800234c2  mov     [rsp+78h+var_50], rsi
0x1800234c7  movsd   [rsp+78h+var_28], xmm0
0x1800234cd  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
