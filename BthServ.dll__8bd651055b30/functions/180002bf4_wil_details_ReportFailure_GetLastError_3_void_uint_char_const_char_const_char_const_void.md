# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180002bf4`
- end: `0x180002c74`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000944c`

## callees

- `0x180002bbc`
- `0x180002bf4`
- `0x1800051d8`
- `0x180005720`

## string_xrefs

- `0x180002c0b`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180002c42`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  void *v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  int v16; // [rsp+58h] [rbp-20h]
  _BYTE v17[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
                    a4,
                    v12,
                    a6,
                    v14);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v9 = wil::details::ResultStatus::FromResult(v17, (unsigned int)LastErrorFail);
  v10 = *(_QWORD *)v9;
  v16 = *(_DWORD *)(v9 + 8);
  v15 = v10;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15,
    0);
}

```

## disassembly

```asm
0x180002bf4  mov     [rsp+arg_0], rbx
0x180002bf9  mov     [rsp+arg_8], rsi
0x180002bfe  push    rdi
0x180002bff  sub     rsp, 70h
0x180002c03  mov     rsi, [rsp+78h+arg_28]
0x180002c0b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002c12  mov     [rsp+78h+var_50], rsi; char *
0x180002c17  mov     ebx, edx
0x180002c19  mov     rdi, rcx
0x180002c1c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180002c21  test    eax, eax
0x180002c23  jle     short loc_180002C2D
0x180002c25  movzx   eax, ax
0x180002c28  or      eax, 80070000h
0x180002c2d  mov     edx, eax
0x180002c2f  lea     rcx, [rsp+78h+var_18]
0x180002c34  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180002c39  mov     [rsp+78h+var_40], 0
0x180002c42  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002c49  mov     edx, ebx
0x180002c4b  mov     rcx, rdi
0x180002c4e  movsd   xmm0, qword ptr [rax]
0x180002c52  mov     eax, [rax+8]
0x180002c55  mov     [rsp+78h+var_20], eax
0x180002c59  lea     rax, [rsp+78h+var_28]
0x180002c5e  mov     [rsp+78h+var_48], rax
0x180002c63  mov     [rsp+78h+var_50], rsi
0x180002c68  movsd   [rsp+78h+var_28], xmm0
0x180002c6e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
