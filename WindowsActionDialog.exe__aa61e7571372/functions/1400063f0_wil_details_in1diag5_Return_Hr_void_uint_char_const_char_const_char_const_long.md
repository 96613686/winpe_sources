# wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)

- ea: `0x1400063f0`
- end: `0x14000641b`
- name: `?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z`
- size: `43`
- prototype: `void __fastcall(wil::details::in1diag5 *__hidden this, void *, unsigned int, const char *, const char *, wil::details *, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b70`
- `0x140003c20`
- `0x1400040e4`
- `0x140004da8`
- `0x140004f6c`
- `0x140007104`
- `0x140007a78`

## callees

- `0x140002364`

## pseudocode

```c
void __fastcall wil::details::in1diag5::Return_Hr(
        wil::details::in1diag5 *this,
        void *a2,
        int a3,
        const char *a4,
        const char *a5,
        wil::details *a6)
{
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a6;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, (__int64)a5, retaddr, v6);
}

```

## disassembly

```asm
0x1400063f0  sub     rsp, 48h
0x1400063f4  mov     r10, [rsp+48h]
0x1400063f9  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400063fd  mov     dword ptr [rsp+48h+var_18], eax; wil::details *
0x140006401  mov     [rsp+48h+var_20], r10; __int64
0x140006406  mov     rax, [rsp+48h+arg_20]
0x14000640b  mov     [rsp+48h+var_28], rax; __int64
0x140006410  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006415  nop
0x140006416  add     rsp, 48h
0x14000641a  retn
```
