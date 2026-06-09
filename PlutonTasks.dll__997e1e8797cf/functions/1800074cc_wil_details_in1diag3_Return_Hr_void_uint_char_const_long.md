# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800074cc`
- end: `0x1800074ea`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d18`
- `0x180003e80`
- `0x180004084`
- `0x180005478`
- `0x180005d50`
- `0x180005e74`
- `0x180008210`
- `0x180008284`

## callees

- `0x180002be4`

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
0x1800074cc  sub     rsp, 48h
0x1800074d0  mov     rax, [rsp+48h]
0x1800074d5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800074da  mov     [rsp+48h+var_20], rax; __int64
0x1800074df  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800074e4  nop
0x1800074e5  add     rsp, 48h
0x1800074e9  retn
```
