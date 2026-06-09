# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180006100`
- end: `0x1800061a5`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009764`

## callees

- `0x180006100`
- `0x1800061ac`
- `0x18000a644`
- `0x18000a6c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000611d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000611d`

## string_xrefs

- `0x180006161`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000618c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  signed int LastError; // eax
  int v9; // edx
  int v10; // r9d
  int v11; // [rsp+20h] [rbp-58h]
  wil::details *v12; // [rsp+30h] [rbp-48h]
  _DWORD v13[8]; // [rsp+58h] [rbp-20h] BYREF

  LastError = GetLastError();
  if ( !LastError )
  {
    LODWORD(v12) = -2147024228;
    wil::details::ReportFailure_Hr<2>(
      a1,
      a2,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      0,
      0,
      a6,
      v12);
    LastError = 668;
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v13[0] = LastError;
  v13[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastError, v9);
  v13[2] = 0;
  wil::details::ReportFailure_Base<3,0>(
    a1,
    a2,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v10,
    v11,
    a6,
    (__int64)v13);
}

```

## disassembly

```asm
0x180006100  mov     rax, rsp
0x180006103  push    rdi
0x180006104  sub     rsp, 70h
0x180006108  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180006110  mov     [rax+8], rbx
0x180006114  mov     [rax+10h], rsi
0x180006118  mov     ebx, edx
0x18000611a  mov     rdi, rcx
0x18000611d  call    cs:__imp_GetLastError
0x180006123  mov     rsi, [rsp+78h+arg_28]
0x18000612b  test    eax, eax
0x18000612d  jz      short loc_180006173
0x18000612f  test    eax, eax
0x180006131  jle     short loc_18000613B
0x180006133  movzx   eax, ax
0x180006136  or      eax, 80070000h
0x18000613b  mov     [rsp+78h+var_20], eax
0x18000613f  mov     ecx, eax; this
0x180006141  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006146  mov     [rsp+78h+var_1C], eax
0x18000614a  mov     [rsp+78h+var_18], 0
0x180006152  lea     rax, [rsp+78h+var_20]
0x180006157  mov     [rsp+78h+var_48], rax
0x18000615c  mov     [rsp+78h+var_50], rsi
0x180006161  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006168  mov     edx, ebx
0x18000616a  mov     rcx, rdi
0x18000616d  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180006173  mov     dword ptr [rsp+78h+var_48], 8007029Ch; wil::details *
0x18000617b  mov     [rsp+78h+var_50], rsi; __int64
0x180006180  mov     [rsp+78h+var_58], 0; __int64
0x180006189  xor     r9d, r9d; int
0x18000618c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006193  mov     edx, ebx; int
0x180006195  mov     rcx, rdi; int
0x180006198  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000619d  mov     eax, 29Ch
0x1800061a2  jmp     short loc_18000612F
```
