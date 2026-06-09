# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x14000644c`
- end: `0x140006473`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `39`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400048f8`
- `0x140004cc8`
- `0x140005a18`
- `0x140006f1c`
- `0x140007f3c`
- `0x140009580`
- `0x14000c164`
- `0x14000f160`
- `0x140011244`
- `0x140011440`
- `0x140011704`

## callees

- `0x140003ab0`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-38h]
  wil::details *v5; // [rsp+30h] [rbp-28h]
  __int64 retaddr; // [rsp+58h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x14000644c  sub     rsp, 58h
0x140006450  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x140006459  mov     rax, [rsp+58h]
0x14000645e  mov     dword ptr [rsp+58h+var_28], r9d; wil::details *
0x140006463  mov     [rsp+58h+var_30], rax; __int64
0x140006468  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000646d  nop
0x14000646e  add     rsp, 58h
0x140006472  retn
```
