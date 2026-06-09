# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x140002c6c`
- end: `0x140002ccf`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `99`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000660c`

## callees

- `0x1400023d0`
- `0x140002c6c`
- `0x1400053c4`

## string_xrefs

- `0x140002c9c`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<1,0>(v9, v8, "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h");
  return v7;
}

```

## disassembly

```asm
0x140002c6c  push    rbx
0x140002c6e  sub     rsp, 60h
0x140002c72  mov     ebx, dword ptr [rsp+68h+arg_30]
0x140002c79  mov     r9, rcx
0x140002c7c  test    ebx, ebx
0x140002c7e  jle     short loc_140002C89
0x140002c80  movzx   ebx, bx
0x140002c83  or      ebx, 80070000h
0x140002c89  mov     ecx, ebx; this
0x140002c8b  mov     [rsp+68h+var_18], ebx
0x140002c8f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002c94  mov     rcx, [rsp+68h+arg_28]
0x140002c9c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002ca3  mov     [rsp+68h+var_14], eax
0x140002ca7  lea     rax, [rsp+68h+var_18]
0x140002cac  mov     [rsp+68h+var_38], rax
0x140002cb1  mov     [rsp+68h+var_40], rcx
0x140002cb6  mov     rcx, r9
0x140002cb9  mov     [rsp+68h+var_10], 0
0x140002cc1  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140002cc6  mov     eax, ebx
0x140002cc8  add     rsp, 60h
0x140002ccc  pop     rbx
0x140002ccd  retn
```
