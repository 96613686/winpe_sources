# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140006984`
- end: `0x1400069a2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x140004d88`
- `0x140004ef4`
- `0x140004fe4`
- `0x140005888`
- `0x140005b78`
- `0x1400062e8`
- `0x140006ec0`
- `0x1400074dc`
- `0x140007560`
- `0x140007f34`
- `0x140009414`
- `0x14000b5a0`
- `0x14000bc54`
- `0x14000bdc4`
- `0x14000e128`
- `0x1400104c0`
- `0x140010a68`
- `0x140012bd0`
- `0x14001464c`
- `0x140015b98`
- `0x140015d98`

## callees

- `0x140003c24`

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
0x140006984  sub     rsp, 48h
0x140006988  mov     rax, [rsp+48h]
0x14000698d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140006992  mov     [rsp+48h+var_20], rax; __int64
0x140006997  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000699c  nop
0x14000699d  add     rsp, 48h
0x1400069a1  retn
```
