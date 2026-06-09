# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18003dc78`
- end: `0x18003dced`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `117`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18003dcf4`

## callees

- `0x180006930`
- `0x180008dac`

## string_xrefs

- `0x18003dcd9`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // r8
  int v9; // edx
  int v10; // r10d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned __int16)a7 | 0x80070000;
  if ( (int)a7 <= 0 )
    v7 = (unsigned int)a7;
  v12[0] = v7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v7, a2);
  v12[2] = v8;
  wil::details::ReportFailure_Base<2,0>(
    v10,
    v9,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    0,
    v8,
    a6,
    (__int64)v12,
    v8);
  return v7;
}

```

## disassembly

```asm
0x18003dc78  push    rbx
0x18003dc7a  sub     rsp, 60h
0x18003dc7e  mov     eax, dword ptr [rsp+68h+arg_30]
0x18003dc85  mov     r10, rcx
0x18003dc88  movzx   ebx, ax
0x18003dc8b  xor     r8d, r8d
0x18003dc8e  or      ebx, 80070000h
0x18003dc94  test    eax, eax
0x18003dc96  cmovle  ebx, eax
0x18003dc99  mov     ecx, ebx; this
0x18003dc9b  mov     [rsp+68h+var_18], ebx
0x18003dc9f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003dca4  mov     rcx, [rsp+68h+arg_28]
0x18003dcac  xor     r9d, r9d
0x18003dcaf  mov     [rsp+68h+var_20], r8d
0x18003dcb4  mov     [rsp+68h+var_30], r8
0x18003dcb9  mov     [rsp+68h+var_14], eax
0x18003dcbd  lea     rax, [rsp+68h+var_18]
0x18003dcc2  mov     [rsp+68h+var_38], rax
0x18003dcc7  mov     [rsp+68h+var_40], rcx
0x18003dccc  mov     rcx, r10
0x18003dccf  mov     [rsp+68h+var_48], r8
0x18003dcd4  mov     [rsp+68h+var_10], r8d
0x18003dcd9  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003dce0  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18003dce5  mov     eax, ebx
0x18003dce7  add     rsp, 60h
0x18003dceb  pop     rbx
0x18003dcec  retn
```
