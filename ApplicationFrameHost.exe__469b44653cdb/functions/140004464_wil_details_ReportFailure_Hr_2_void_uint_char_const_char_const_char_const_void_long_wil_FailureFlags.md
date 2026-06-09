# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x140004464`
- end: `0x1400044cf`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `107`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140002a40`
- `0x140002bf0`
- `0x140002d60`
- `0x1400069e0`
- `0x14000a26c`

## callees

- `0x1400025e0`
- `0x140004370`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        wil::details *a7)
{
  int v8; // r9d
  int v9; // r10d
  int v10; // r11d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v12[0] = (_DWORD)a7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(a1, v10, v9, v8, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x140004464  push    rbx
0x140004466  sub     rsp, 60h
0x14000446a  mov     rbx, rcx
0x14000446d  mov     r10, r8
0x140004470  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x140004477  mov     r11d, edx
0x14000447a  mov     [rsp+68h+var_18], ecx
0x14000447e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004483  mov     [rsp+68h+var_14], eax
0x140004487  mov     r8, r10
0x14000448a  mov     [rsp+68h+var_20], 0
0x140004492  lea     rax, [rsp+68h+var_18]
0x140004497  mov     [rsp+68h+var_38], rax
0x14000449c  mov     edx, r11d
0x14000449f  mov     rax, [rsp+68h+arg_28]
0x1400044a7  mov     rcx, rbx
0x1400044aa  mov     [rsp+68h+var_40], rax
0x1400044af  mov     rax, [rsp+68h+arg_20]
0x1400044b7  mov     [rsp+68h+var_48], rax
0x1400044bc  mov     [rsp+68h+var_10], 0
0x1400044c4  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1400044c9  add     rsp, 60h
0x1400044cd  pop     rbx
0x1400044ce  retn
```
