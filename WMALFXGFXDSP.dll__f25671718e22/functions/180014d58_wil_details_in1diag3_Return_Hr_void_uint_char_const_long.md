# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180014d58`
- end: `0x180014d75`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800090e0`
- `0x1800125b0`
- `0x180076c4c`
- `0x1800770c8`
- `0x18007732c`
- `0x1800775a0`
- `0x180077874`
- `0x180078128`
- `0x180078694`
- `0x180079150`
- `0x1800794d0`

## callees

- `0x180014d7c`

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
0x180014d58  sub     rsp, 48h
0x180014d5c  mov     rax, [rsp+48h]
0x180014d61  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180014d66  mov     [rsp+48h+var_20], rax; __int64
0x180014d6b  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180014d70  add     rsp, 48h
0x180014d74  retn
```
