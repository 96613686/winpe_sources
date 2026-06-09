# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x14000bedc`
- end: `0x14000befa`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140007b30`
- `0x140007c98`
- `0x1400092d8`
- `0x14000a120`
- `0x14000af14`
- `0x14000b058`
- `0x14000cb30`
- `0x14000cba4`

## callees

- `0x140006fcc`

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
0x14000bedc  sub     rsp, 48h
0x14000bee0  mov     rax, [rsp+48h]
0x14000bee5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x14000beea  mov     [rsp+48h+var_20], rax; __int64
0x14000beef  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000bef4  nop
0x14000bef5  add     rsp, 48h
0x14000bef9  retn
```
