# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180006214`
- end: `0x180006232`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031fc`
- `0x180003504`
- `0x180004610`
- `0x180006240`
- `0x180006400`
- `0x1800073b8`
- `0x180007790`
- `0x180008010`
- `0x180008f3c`
- `0x18000d050`
- `0x18000dd6c`
- `0x18000df30`

## callees

- `0x180003e64`

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
0x180006214  sub     rsp, 48h
0x180006218  mov     rax, [rsp+48h]
0x18000621d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006222  mov     [rsp+48h+var_20], rax; __int64
0x180006227  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000622c  nop
0x18000622d  add     rsp, 48h
0x180006231  retn
```
