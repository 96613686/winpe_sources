# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000fb30`
- end: `0x18000fb92`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010a60`

## callees

- `0x180003390`
- `0x1800051c4`
- `0x18000fb30`

## string_xrefs

- `0x18000fb60`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
0x18000fb30  push    rbx
0x18000fb32  sub     rsp, 60h
0x18000fb36  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000fb3d  mov     r9, rcx
0x18000fb40  test    ebx, ebx
0x18000fb42  jle     short loc_18000FB4D
0x18000fb44  movzx   ebx, bx
0x18000fb47  or      ebx, 80070000h
0x18000fb4d  mov     ecx, ebx; this
0x18000fb4f  mov     [rsp+68h+var_18], ebx
0x18000fb53  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fb58  mov     rcx, [rsp+68h+arg_28]
0x18000fb60  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000fb67  mov     [rsp+68h+var_14], eax
0x18000fb6b  lea     rax, [rsp+68h+var_18]
0x18000fb70  mov     [rsp+68h+var_38], rax
0x18000fb75  mov     [rsp+68h+var_40], rcx
0x18000fb7a  mov     rcx, r9
0x18000fb7d  mov     [rsp+68h+var_10], 0
0x18000fb85  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fb8a  mov     eax, ebx
0x18000fb8c  add     rsp, 60h
0x18000fb90  pop     rbx
0x18000fb91  retn
```
