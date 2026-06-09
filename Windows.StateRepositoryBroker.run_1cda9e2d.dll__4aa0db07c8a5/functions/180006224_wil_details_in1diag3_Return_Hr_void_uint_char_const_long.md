# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180006224`
- end: `0x180006242`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `51`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b90`
- `0x180006fe0`
- `0x180007030`
- `0x180007550`
- `0x1800075a0`
- `0x180007ac8`
- `0x180007bc0`
- `0x180007f28`
- `0x1800080cc`
- `0x180008270`
- `0x1800082d0`
- `0x180008330`
- `0x180008390`
- `0x180008420`
- `0x180008480`
- `0x1800084e0`
- `0x180008570`
- `0x1800085d0`
- `0x180008630`
- `0x1800086c0`
- `0x180008720`
- `0x180008780`
- `0x180008810`
- `0x180008870`
- `0x1800088d0`
- `0x180008960`
- `0x1800089c0`
- `0x180008a20`
- `0x180008a80`
- `0x180008b10`
- `0x180008b68`
- `0x180008e00`
- `0x180008e60`
- `0x180008ec0`
- `0x180008f20`
- `0x180008f80`
- `0x180008fe0`
- `0x180009040`
- `0x1800090a0`
- `0x180009100`
- `0x180009160`
- `0x1800091f0`
- `0x180009250`
- `0x1800092a8`
- `0x180009a20`
- `0x180009af8`
- `0x180009d80`
- `0x180009f2c`
- `0x180009fc0`
- `0x18000a1b8`

## callees

- `0x18000358c`

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
0x180006224  sub     rsp, 48h
0x180006228  mov     rax, [rsp+48h]
0x18000622d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006232  mov     [rsp+48h+var_20], rax; __int64
0x180006237  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000623c  nop
0x18000623d  add     rsp, 48h
0x180006241  retn
```
