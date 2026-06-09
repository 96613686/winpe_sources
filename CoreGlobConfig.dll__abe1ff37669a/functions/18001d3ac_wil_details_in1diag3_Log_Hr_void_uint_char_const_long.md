# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18001d3ac`
- end: `0x18001d3dd`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800126c4`
- `0x1800190bc`
- `0x18001b6e0`
- `0x18001f0b0`
- `0x180020010`
- `0x1800203b0`
- `0x180020490`

## callees

- `0x180005e24`

## string_xrefs

- `0x18001d3cb`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    (int)a2,
    (int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18001d3ac  sub     rsp, 48h
0x18001d3b0  mov     rax, [rsp+48h]
0x18001d3b5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18001d3ba  mov     [rsp+48h+var_20], rax; __int64
0x18001d3bf  mov     [rsp+48h+var_28], 0; __int64
0x18001d3c8  xor     r9d, r9d; int
0x18001d3cb  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001d3d2  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001d3d7  nop
0x18001d3d8  add     rsp, 48h
0x18001d3dc  retn
```
