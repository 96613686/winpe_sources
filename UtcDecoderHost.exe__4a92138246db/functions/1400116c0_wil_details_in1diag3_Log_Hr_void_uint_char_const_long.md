# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x1400116c0`
- end: `0x1400116ea`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `42`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f8c0`
- `0x14000fa04`
- `0x14000fccc`
- `0x14001071c`

## callees

- `0x1400098f8`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>((__int64)this, (int)a2, a3, 0, 0, retaddr, v4);
}

```

## disassembly

```asm
0x1400116c0  sub     rsp, 48h
0x1400116c4  mov     rax, [rsp+48h]
0x1400116c9  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1400116ce  mov     [rsp+48h+var_20], rax; __int64
0x1400116d3  mov     [rsp+48h+var_28], 0; __int64
0x1400116dc  xor     r9d, r9d; int
0x1400116df  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400116e4  nop
0x1400116e5  add     rsp, 48h
0x1400116e9  retn
```
