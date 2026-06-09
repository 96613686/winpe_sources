# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18001637c`
- end: `0x1800163b2`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `54`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015c0c`

## callees

- `0x180002d80`

## string_xrefs

- `0x18001639b`: `mincore\textinput\dev\mtf\datasources\filterds\lib\regreader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    157,
    (__int64)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\regreader.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18001637c  sub     rsp, 48h
0x180016380  mov     rax, [rsp+48h]
0x180016385  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18001638a  mov     [rsp+48h+var_20], rax; __int64
0x18001638f  mov     [rsp+48h+var_28], 0; __int64
0x180016398  xor     r9d, r9d; int
0x18001639b  lea     r8, aMincoreTextinp_0; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x1800163a2  mov     edx, 9Dh; int
0x1800163a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800163ac  nop
0x1800163ad  add     rsp, 48h
0x1800163b1  retn
```
