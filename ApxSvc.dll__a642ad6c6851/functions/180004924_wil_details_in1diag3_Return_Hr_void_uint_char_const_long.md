# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180004924`
- end: `0x180004942`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f08`
- `0x1800032d8`
- `0x180003e94`
- `0x18000536c`
- `0x180006ac4`
- `0x180006c94`

## callees

- `0x18000235c`

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
0x180004924  sub     rsp, 48h
0x180004928  mov     rax, [rsp+48h]
0x18000492d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180004932  mov     [rsp+48h+var_20], rax; __int64
0x180004937  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000493c  nop
0x18000493d  add     rsp, 48h
0x180004941  retn
```
