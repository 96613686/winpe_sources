# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x14000629c`
- end: `0x14000630c`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140006d2c`

## callees

- `0x140001fa8`
- `0x140003e14`
- `0x14000629c`

## string_xrefs

- `0x1400062cc`: `onecore\enduser\windowsupdate\muse\orchestrator\common\lib\usocommon\registrymanager.cpp`

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
  int v8; // r9d
  int v10; // [rsp+20h] [rbp-48h]
  _DWORD v11[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v11[0] = v7;
  v11[1] = wil::details::HrToNtStatus((wil::details *)v7, a2);
  v11[2] = 0;
  wil::details::ReportFailure_Base<1,0>(
    v8,
    1700,
    (int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\common\\lib\\usocommon\\registrymanager.cpp",
    v8,
    v10,
    a6,
    (int)v11,
    0);
  return v7;
}

```

## disassembly

```asm
0x14000629c  push    rbx
0x14000629e  sub     rsp, 60h
0x1400062a2  mov     ebx, dword ptr [rsp+68h+arg_30]
0x1400062a9  mov     r9, rcx
0x1400062ac  test    ebx, ebx
0x1400062ae  jle     short loc_1400062B9
0x1400062b0  movzx   ebx, bx
0x1400062b3  or      ebx, 80070000h
0x1400062b9  mov     ecx, ebx; this
0x1400062bb  mov     [rsp+68h+var_18], ebx
0x1400062bf  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400062c4  mov     rcx, [rsp+68h+arg_28]
0x1400062cc  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1400062d3  mov     [rsp+68h+var_14], eax
0x1400062d7  mov     edx, 6A4h
0x1400062dc  lea     rax, [rsp+68h+var_18]
0x1400062e1  mov     [rsp+68h+var_30], 0
0x1400062ea  mov     [rsp+68h+var_38], rax
0x1400062ef  mov     [rsp+68h+var_40], rcx
0x1400062f4  mov     rcx, r9
0x1400062f7  mov     [rsp+68h+var_10], 0
0x1400062ff  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140006304  mov     eax, ebx
0x140006306  add     rsp, 60h
0x14000630a  pop     rbx
0x14000630b  retn
```
