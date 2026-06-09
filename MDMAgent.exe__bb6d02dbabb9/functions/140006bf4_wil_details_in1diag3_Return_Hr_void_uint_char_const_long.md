# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140006bf4`
- end: `0x140006c13`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `31`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x140004e2c`
- `0x140004fa8`
- `0x140005144`
- `0x140005a44`
- `0x140005d48`
- `0x140006510`
- `0x140007160`
- `0x14000779c`
- `0x140007820`
- `0x14000829c`
- `0x140009804`
- `0x14000bac4`
- `0x14000c1a0`
- `0x14000c314`
- `0x14000e84c`
- `0x140010cf0`
- `0x1400112b0`
- `0x14001351c`
- `0x1400151d8`
- `0x140016808`
- `0x140016a28`

## callees

- `0x140003cd4`

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
0x140006bf4  sub     rsp, 48h
0x140006bf8  mov     rax, [rsp+48h]
0x140006bfd  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140006c02  mov     [rsp+48h+var_20], rax; __int64
0x140006c07  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006c0c  nop
0x140006c0d  add     rsp, 48h
0x140006c11  retn
```
