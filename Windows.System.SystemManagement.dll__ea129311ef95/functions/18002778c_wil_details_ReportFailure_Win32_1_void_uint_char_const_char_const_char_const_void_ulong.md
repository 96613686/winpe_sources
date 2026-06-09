# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18002778c`
- end: `0x1800277f7`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `107`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180027904`

## callees

- `0x180004050`
- `0x18000706c`
- `0x18002778c`

## string_xrefs

- `0x1800277bc`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

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
  wil::details::ReportFailure_Base<1,0>(
    v9,
    v8,
    "onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp");
  return v7;
}

```

## disassembly

```asm
0x18002778c  push    rbx
0x18002778e  sub     rsp, 60h
0x180027792  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180027799  mov     r9, rcx
0x18002779c  test    ebx, ebx
0x18002779e  jle     short loc_1800277A9
0x1800277a0  movzx   ebx, bx
0x1800277a3  or      ebx, 80070000h
0x1800277a9  mov     ecx, ebx; this
0x1800277ab  mov     [rsp+68h+var_18], ebx
0x1800277af  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800277b4  mov     rcx, [rsp+68h+arg_28]
0x1800277bc  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800277c3  mov     [rsp+68h+var_14], eax
0x1800277c7  lea     rax, [rsp+68h+var_18]
0x1800277cc  mov     [rsp+68h+var_30], 0
0x1800277d5  mov     [rsp+68h+var_38], rax
0x1800277da  mov     [rsp+68h+var_40], rcx
0x1800277df  mov     rcx, r9
0x1800277e2  mov     [rsp+68h+var_10], 0
0x1800277ea  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800277ef  mov     eax, ebx
0x1800277f1  add     rsp, 60h
0x1800277f5  pop     rbx
0x1800277f6  retn
```
