# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000d5fc`
- end: `0x18000d627`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `43`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008040`
- `0x18000f4b0`
- `0x18000f910`

## callees

- `0x1800037a8`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, __int64 a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>((__int64)this, a2, a3, 0, 0, retaddr, v4);
}

```

## disassembly

```asm
0x18000d5fc  sub     rsp, 48h
0x18000d600  mov     rax, [rsp+48h]
0x18000d605  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000d60a  mov     [rsp+48h+var_20], rax; __int64
0x18000d60f  mov     [rsp+48h+var_28], 0; __int64
0x18000d618  xor     r9d, r9d; int
0x18000d61b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000d620  nop
0x18000d621  add     rsp, 48h
0x18000d625  retn
```
