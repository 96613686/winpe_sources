# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x18001617c`
- end: `0x1800161b3`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `55`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800136c8`
- `0x18001b6e0`

## callees

- `0x180005e24`

## string_xrefs

- `0x18001619f`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  unsigned int v4; // ebx
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  v4 = (unsigned int)a4;
  LODWORD(v6) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    (int)a2,
    (int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18001617c  push    rbx
0x18001617e  sub     rsp, 40h
0x180016182  mov     ebx, r9d
0x180016185  mov     rax, [rsp+48h]
0x18001618a  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x18001618e  mov     [rsp+48h+var_20], rax; __int64
0x180016193  mov     [rsp+48h+var_28], 0; __int64
0x18001619c  xor     r9d, r9d; int
0x18001619f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800161a6  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800161ab  mov     eax, ebx
0x1800161ad  add     rsp, 40h
0x1800161b1  pop     rbx
0x1800161b2  retn
```
