# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140004d74`
- end: `0x140004d92`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140003440`
- `0x14000361c`
- `0x14000402c`
- `0x1400046d4`
- `0x140005440`
- `0x140006788`
- `0x14000759c`
- `0x140007ad0`
- `0x140008a10`
- `0x140008fdc`

## callees

- `0x14000293c`

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
0x140004d74  sub     rsp, 48h
0x140004d78  mov     rax, [rsp+48h]
0x140004d7d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140004d82  mov     [rsp+48h+var_20], rax; __int64
0x140004d87  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004d8c  nop
0x140004d8d  add     rsp, 48h
0x140004d91  retn
```
