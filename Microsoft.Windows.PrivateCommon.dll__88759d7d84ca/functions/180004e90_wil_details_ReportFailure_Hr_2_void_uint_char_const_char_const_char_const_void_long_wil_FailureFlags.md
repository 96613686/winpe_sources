# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180004e90`
- end: `0x180004ef5`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `101`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c30`
- `0x180002ca0`
- `0x1800039a0`
- `0x1800051e0`

## callees

- `0x180002990`
- `0x180004f00`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        int a1,
        int a2,
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
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7, a2);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(a1, v10, v9, v8, a5, a6, (unsigned int)v12);
}

```

## disassembly

```asm
0x180004e90  push    rbx
0x180004e92  sub     rsp, 60h
0x180004e96  mov     rbx, rcx
0x180004e99  mov     r10, r8
0x180004e9c  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180004ea3  mov     r11d, edx
0x180004ea6  mov     [rsp+68h+var_18], ecx
0x180004eaa  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004eaf  mov     [rsp+68h+var_14], eax
0x180004eb3  mov     r8, r10
0x180004eb6  xor     eax, eax
0x180004eb8  mov     edx, r11d
0x180004ebb  mov     [rsp+68h+var_20], eax
0x180004ebf  mov     rcx, rbx
0x180004ec2  mov     [rsp+68h+var_10], eax
0x180004ec6  lea     rax, [rsp+68h+var_18]
0x180004ecb  mov     [rsp+68h+var_38], rax
0x180004ed0  mov     rax, [rsp+68h+arg_28]
0x180004ed8  mov     [rsp+68h+var_40], rax
0x180004edd  mov     rax, [rsp+68h+arg_20]
0x180004ee5  mov     [rsp+68h+var_48], rax
0x180004eea  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180004eef  add     rsp, 60h
0x180004ef3  pop     rbx
0x180004ef4  retn
```
