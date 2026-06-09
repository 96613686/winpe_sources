# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000fe20`
- end: `0x18000fe8b`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `107`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010100`

## callees

- `0x18000274c`
- `0x1800049b8`
- `0x18000fe20`

## string_xrefs

- `0x18000fe50`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`

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
  int v8; // edx
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-48h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v12[0] = v7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v7, a2);
  v12[2] = 0;
  wil::details::ReportFailure_Base<1,0>(
    v9,
    v8,
    (int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
    v9,
    v11,
    a6,
    (int)v12,
    0);
  return v7;
}

```

## disassembly

```asm
0x18000fe20  push    rbx
0x18000fe22  sub     rsp, 60h
0x18000fe26  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000fe2d  mov     r9, rcx
0x18000fe30  test    ebx, ebx
0x18000fe32  jle     short loc_18000FE3D
0x18000fe34  movzx   ebx, bx
0x18000fe37  or      ebx, 80070000h
0x18000fe3d  mov     ecx, ebx; this
0x18000fe3f  mov     [rsp+68h+var_18], ebx
0x18000fe43  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fe48  mov     rcx, [rsp+68h+arg_28]
0x18000fe50  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000fe57  mov     [rsp+68h+var_14], eax
0x18000fe5b  lea     rax, [rsp+68h+var_18]
0x18000fe60  mov     [rsp+68h+var_30], 0
0x18000fe69  mov     [rsp+68h+var_38], rax
0x18000fe6e  mov     [rsp+68h+var_40], rcx
0x18000fe73  mov     rcx, r9
0x18000fe76  mov     [rsp+68h+var_10], 0
0x18000fe7e  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fe83  mov     eax, ebx
0x18000fe85  add     rsp, 60h
0x18000fe89  pop     rbx
0x18000fe8a  retn
```
