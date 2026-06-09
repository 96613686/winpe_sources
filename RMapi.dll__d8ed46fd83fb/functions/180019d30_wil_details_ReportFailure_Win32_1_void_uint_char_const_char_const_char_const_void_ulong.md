# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180019d30`
- end: `0x180019d97`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `103`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001fcd8`

## callees

- `0x180007a58`
- `0x18000aab4`
- `0x180019d30`

## string_xrefs

- `0x180019d60`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

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
  __int64 v8; // r9

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<1,0>(v8, 3266, "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h");
  return v7;
}

```

## disassembly

```asm
0x180019d30  push    rbx
0x180019d32  sub     rsp, 60h
0x180019d36  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180019d3d  mov     r9, rcx
0x180019d40  test    ebx, ebx
0x180019d42  jle     short loc_180019D4D
0x180019d44  movzx   ebx, bx
0x180019d47  or      ebx, 80070000h
0x180019d4d  mov     ecx, ebx; this
0x180019d4f  mov     [rsp+68h+var_18], ebx
0x180019d53  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180019d58  mov     rcx, [rsp+68h+arg_28]
0x180019d60  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180019d67  mov     [rsp+68h+var_14], eax
0x180019d6b  mov     edx, 0CC2h
0x180019d70  lea     rax, [rsp+68h+var_18]
0x180019d75  mov     [rsp+68h+var_10], 0
0x180019d7d  mov     [rsp+68h+var_38], rax
0x180019d82  mov     [rsp+68h+var_40], rcx
0x180019d87  mov     rcx, r9
0x180019d8a  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180019d8f  mov     eax, ebx
0x180019d91  add     rsp, 60h
0x180019d95  pop     rbx
0x180019d96  retn
```
