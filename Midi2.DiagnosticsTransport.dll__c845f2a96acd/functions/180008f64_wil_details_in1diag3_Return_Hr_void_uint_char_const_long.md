# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180008f64`
- end: `0x180008f82`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180005198`
- `0x180006100`
- `0x180007104`
- `0x180009a5c`
- `0x18000b9f0`
- `0x18000ccf8`
- `0x18000d0b4`
- `0x18000d31c`
- `0x18000f4f0`
- `0x180010a90`
- `0x180010b70`
- `0x180011010`
- `0x1800111f8`
- `0x1800112d0`
- `0x1800119a0`
- `0x180011b5c`

## callees

- `0x18000439c`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x180008f64  sub     rsp, 48h
0x180008f68  mov     rax, [rsp+48h]
0x180008f6d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180008f72  mov     [rsp+48h+var_20], rax; __int64
0x180008f77  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008f7c  nop
0x180008f7d  add     rsp, 48h
0x180008f81  retn
```
