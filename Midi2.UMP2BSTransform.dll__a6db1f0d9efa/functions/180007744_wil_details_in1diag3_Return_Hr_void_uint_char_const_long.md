# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180007744`
- end: `0x180007762`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003978`
- `0x1800048e0`
- `0x1800058e4`
- `0x18000823c`
- `0x18000a040`
- `0x18000c2c0`
- `0x18000caf0`

## callees

- `0x180002b78`

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
0x180007744  sub     rsp, 48h
0x180007748  mov     rax, [rsp+48h]
0x18000774d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180007752  mov     [rsp+48h+var_20], rax; __int64
0x180007757  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000775c  nop
0x18000775d  add     rsp, 48h
0x180007761  retn
```
