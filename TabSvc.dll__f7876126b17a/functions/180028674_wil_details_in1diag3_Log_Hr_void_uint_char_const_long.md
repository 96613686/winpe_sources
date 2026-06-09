# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180028674`
- end: `0x1800286aa`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `54`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180025bbc`

## callees

- `0x18001d7a8`

## string_xrefs

- `0x180028693`: `drivers\tablet\platform\pen\penservice\penservice.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    2834,
    (int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x180028674  sub     rsp, 48h
0x180028678  mov     rax, [rsp+48h]
0x18002867d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180028682  mov     [rsp+48h+var_20], rax; __int64
0x180028687  mov     [rsp+48h+var_28], 0; __int64
0x180028690  xor     r9d, r9d; int
0x180028693  lea     r8, aDriversTabletP_1; "drivers\\tablet\\platform\\pen\\penserv"...
0x18002869a  mov     edx, 0B12h; int
0x18002869f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800286a4  nop
0x1800286a5  add     rsp, 48h
0x1800286a9  retn
```
