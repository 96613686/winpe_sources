# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000f12c`
- end: `0x18000f19c`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e2b8`

## callees

- `0x180003fbc`
- `0x180008110`
- `0x18000f12c`

## string_xrefs

- `0x18000f15c`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

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
0x18000f12c  push    rbx
0x18000f12e  sub     rsp, 60h
0x18000f132  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000f139  mov     r9, rcx
0x18000f13c  test    ebx, ebx
0x18000f13e  jle     short loc_18000F149
0x18000f140  movzx   ebx, bx
0x18000f143  or      ebx, 80070000h
0x18000f149  mov     ecx, ebx; this
0x18000f14b  mov     [rsp+68h+var_18], ebx
0x18000f14f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000f154  mov     rcx, [rsp+68h+arg_28]
0x18000f15c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f163  mov     [rsp+68h+var_14], eax
0x18000f167  mov     edx, 0CC2h
0x18000f16c  lea     rax, [rsp+68h+var_18]
0x18000f171  mov     [rsp+68h+var_30], 0
0x18000f17a  mov     [rsp+68h+var_38], rax
0x18000f17f  mov     [rsp+68h+var_40], rcx
0x18000f184  mov     rcx, r9
0x18000f187  mov     [rsp+68h+var_10], 0
0x18000f18f  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000f194  mov     eax, ebx
0x18000f196  add     rsp, 60h
0x18000f19a  pop     rbx
0x18000f19b  retn
```
