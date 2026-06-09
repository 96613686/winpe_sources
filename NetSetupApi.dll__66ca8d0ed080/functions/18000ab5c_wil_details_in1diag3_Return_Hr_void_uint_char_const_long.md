# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18000ab5c`
- end: `0x18000ab83`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `39`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x18000966c`
- `0x180009848`
- `0x18000a18c`
- `0x18000a680`
- `0x18000aff0`
- `0x18000bd18`
- `0x18000be20`
- `0x18000c188`
- `0x18000c354`
- `0x18000c4a8`
- `0x18000c660`
- `0x18000c760`
- `0x18000c860`
- `0x18000c8e0`
- `0x18000c960`
- `0x18000ca10`

## callees

- `0x180008e74`

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
0x18000ab5c  sub     rsp, 58h
0x18000ab60  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000ab69  mov     rax, [rsp+58h]
0x18000ab6e  mov     dword ptr [rsp+58h+var_28], r9d; wil::details *
0x18000ab73  mov     [rsp+58h+var_30], rax; __int64
0x18000ab78  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ab7d  nop
0x18000ab7e  add     rsp, 58h
0x18000ab82  retn
```
