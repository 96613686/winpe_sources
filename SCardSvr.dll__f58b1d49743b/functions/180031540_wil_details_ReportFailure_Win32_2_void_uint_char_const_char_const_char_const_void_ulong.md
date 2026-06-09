# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180031540`
- end: `0x1800315b0`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800319c0`

## callees

- `0x18001bf8c`
- `0x18002355c`
- `0x180031540`

## string_xrefs

- `0x180031572`: `ds\security\ngc\ctnrsvc\client\gids\ngcgidshandlerclient.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<2>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // r10d
  _DWORD v11[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v11[0] = v7;
  v11[1] = wil::details::HrToNtStatus((wil::details *)v7, 0);
  v11[2] = v8;
  wil::details::ReportFailure_Base<2,0>(
    v9,
    82,
    (unsigned int)"ds\\security\\ngc\\ctnrsvc\\client\\gids\\ngcgidshandlerclient.cpp",
    0,
    v8,
    a6,
    (__int64)v11);
  return v7;
}

```

## disassembly

```asm
0x180031540  push    rbx
0x180031542  sub     rsp, 60h
0x180031546  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18003154d  xor     edx, edx; int
0x18003154f  mov     r10, rcx
0x180031552  test    ebx, ebx
0x180031554  jle     short loc_18003155F
0x180031556  movzx   ebx, bx
0x180031559  or      ebx, 80070000h
0x18003155f  mov     ecx, ebx; this
0x180031561  mov     [rsp+68h+var_18], ebx
0x180031565  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003156a  mov     rcx, [rsp+68h+arg_28]
0x180031572  lea     r8, aDsSecurityNgcC; "ds\\security\\ngc\\ctnrsvc\\client\\gid"...
0x180031579  mov     [rsp+68h+var_20], edx
0x18003157d  xor     r9d, r9d
0x180031580  mov     [rsp+68h+var_14], eax
0x180031584  lea     rax, [rsp+68h+var_18]
0x180031589  mov     [rsp+68h+var_38], rax
0x18003158e  mov     [rsp+68h+var_40], rcx
0x180031593  mov     rcx, r10
0x180031596  mov     [rsp+68h+var_48], rdx
0x18003159b  mov     [rsp+68h+var_10], edx
0x18003159f  lea     edx, [r9+52h]
0x1800315a3  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800315a8  mov     eax, ebx
0x1800315aa  add     rsp, 60h
0x1800315ae  pop     rbx
0x1800315af  retn
```
