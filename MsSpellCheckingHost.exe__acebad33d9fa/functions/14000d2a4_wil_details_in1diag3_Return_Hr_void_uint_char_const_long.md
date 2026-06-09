# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x14000d2a4`
- end: `0x14000d2c2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140009088`
- `0x14000942c`
- `0x14000992c`
- `0x14000ab30`
- `0x14000e0ac`

## callees

- `0x140007034`

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
0x14000d2a4  sub     rsp, 48h
0x14000d2a8  mov     rax, [rsp+48h]
0x14000d2ad  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x14000d2b2  mov     [rsp+48h+var_20], rax; __int64
0x14000d2b7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000d2bc  nop
0x14000d2bd  add     rsp, 48h
0x14000d2c1  retn
```
