# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140004a94`
- end: `0x140004ab1`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400047c8`
- `0x14000492c`
- `0x140007adc`
- `0x140007c48`
- `0x140007e14`
- `0x1400090bc`
- `0x14000afdc`
- `0x14000b060`
- `0x14000d87c`

## callees

- `0x140006d80`

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
0x140004a94  sub     rsp, 48h
0x140004a98  mov     rax, [rsp+48h]
0x140004a9d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140004aa2  mov     [rsp+48h+var_20], rax; __int64
0x140004aa7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004aac  add     rsp, 48h
0x140004ab0  retn
```
