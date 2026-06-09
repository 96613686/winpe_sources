# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000b968`
- end: `0x18000b998`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `48`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007a10`
- `0x1800085b0`
- `0x18000b5dc`

## callees

- `0x180002cc4`

## string_xrefs

- `0x18000b971`: `shell\deviceux\contexthandlers\removedevice\src\contexthandler.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    (int)a2,
    (__int64)"shell\\deviceux\\contexthandlers\\removedevice\\src\\contexthandler.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18000b968  sub     rsp, 48h
0x18000b96c  mov     rax, [rsp+48h]
0x18000b971  lea     r8, aShellDeviceuxC; "shell\\deviceux\\contexthandlers\\remov"...
0x18000b978  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000b97d  xor     r9d, r9d; int
0x18000b980  mov     [rsp+48h+var_20], rax; __int64
0x18000b985  mov     [rsp+48h+var_28], 0; __int64
0x18000b98e  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000b993  add     rsp, 48h
0x18000b997  retn
```
