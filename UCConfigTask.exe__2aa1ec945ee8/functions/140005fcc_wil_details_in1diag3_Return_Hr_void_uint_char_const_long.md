# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140005fcc`
- end: `0x140005fea`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140003478`
- `0x1400035e4`
- `0x1400037b0`
- `0x1400045b8`
- `0x140004e38`
- `0x140004f68`
- `0x140006af8`
- `0x140006b7c`
- `0x140007c60`

## callees

- `0x1400023d4`

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
0x140005fcc  sub     rsp, 48h
0x140005fd0  mov     rax, [rsp+48h]
0x140005fd5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140005fda  mov     [rsp+48h+var_20], rax; __int64
0x140005fdf  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005fe4  nop
0x140005fe5  add     rsp, 48h
0x140005fe9  retn
```
