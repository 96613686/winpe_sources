# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140004724`
- end: `0x140004742`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002d58`
- `0x1400030fc`
- `0x140003c94`
- `0x14000516c`

## callees

- `0x1400021a8`

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
0x140004724  sub     rsp, 48h
0x140004728  mov     rax, [rsp+48h]
0x14000472d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140004732  mov     [rsp+48h+var_20], rax; __int64
0x140004737  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000473c  nop
0x14000473d  add     rsp, 48h
0x140004741  retn
```
