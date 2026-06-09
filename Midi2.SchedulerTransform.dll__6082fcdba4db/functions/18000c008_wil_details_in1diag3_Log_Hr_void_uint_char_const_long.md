# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000c008`
- end: `0x18000c039`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000af80`
- `0x18000cf13`
- `0x18000cfbc`
- `0x18000d09b`
- `0x18000d20c`
- `0x18000d2b5`

## callees

- `0x180002cd8`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, __int64 a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    a2,
    (__int64)"avcore\\midi2\\transform\\schedulertransform\\midi2.schedulermiditransform.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18000c008  sub     rsp, 48h
0x18000c00c  mov     rax, [rsp+48h]
0x18000c011  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000c016  mov     [rsp+48h+var_20], rax; __int64
0x18000c01b  mov     [rsp+48h+var_28], 0; __int64
0x18000c024  xor     r9d, r9d; int
0x18000c027  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transform\\schedulertran"...
0x18000c02e  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000c033  nop
0x18000c034  add     rsp, 48h
0x18000c038  retn
```
