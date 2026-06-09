# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1400080f4`
- end: `0x14000811e`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `42`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140008124`
- `0x140008368`
- `0x14000849c`
- `0x1400086f0`
- `0x140008790`
- `0x140008a3c`
- `0x140008fb0`
- `0x140009080`

## callees

- `0x140002364`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, 0, 0, retaddr, v4);
}

```

## disassembly

```asm
0x1400080f4  sub     rsp, 48h
0x1400080f8  mov     rax, [rsp+48h]
0x1400080fd  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140008102  mov     [rsp+48h+var_20], rax; __int64
0x140008107  mov     [rsp+48h+var_28], 0; __int64
0x140008110  xor     r9d, r9d; int
0x140008113  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140008118  nop
0x140008119  add     rsp, 48h
0x14000811d  retn
```
