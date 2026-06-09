# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140002ce0`
- end: `0x140002cfe`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140001d80`
- `0x140002460`
- `0x1400052f8`
- `0x140005464`
- `0x140005630`
- `0x140006744`
- `0x140006e0c`
- `0x140006f70`
- `0x140008e08`
- `0x140008e8c`

## callees

- `0x140002d04`

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
0x140002ce0  sub     rsp, 48h
0x140002ce4  mov     rax, [rsp+48h]
0x140002ce9  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140002cee  mov     [rsp+48h+var_20], rax; __int64
0x140002cf3  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140002cf8  nop
0x140002cf9  add     rsp, 48h
0x140002cfd  retn
```
