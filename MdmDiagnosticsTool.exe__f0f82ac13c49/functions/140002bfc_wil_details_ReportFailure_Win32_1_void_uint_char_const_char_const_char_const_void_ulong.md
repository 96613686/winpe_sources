# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x140002bfc`
- end: `0x140002c5e`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006268`

## callees

- `0x140002374`
- `0x140002bfc`
- `0x1400050f0`

## string_xrefs

- `0x140002c2c`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
0x140002bfc  push    rbx
0x140002bfe  sub     rsp, 60h
0x140002c02  mov     ebx, dword ptr [rsp+68h+arg_30]
0x140002c09  mov     r9, rcx
0x140002c0c  test    ebx, ebx
0x140002c0e  jle     short loc_140002C19
0x140002c10  movzx   ebx, bx
0x140002c13  or      ebx, 80070000h
0x140002c19  mov     ecx, ebx; this
0x140002c1b  mov     [rsp+68h+var_18], ebx
0x140002c1f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002c24  mov     rcx, [rsp+68h+arg_28]
0x140002c2c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002c33  mov     [rsp+68h+var_14], eax
0x140002c37  lea     rax, [rsp+68h+var_18]
0x140002c3c  mov     [rsp+68h+var_38], rax
0x140002c41  mov     [rsp+68h+var_40], rcx
0x140002c46  mov     rcx, r9
0x140002c49  mov     [rsp+68h+var_10], 0
0x140002c51  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140002c56  mov     eax, ebx
0x140002c58  add     rsp, 60h
0x140002c5c  pop     rbx
0x140002c5d  retn
```
