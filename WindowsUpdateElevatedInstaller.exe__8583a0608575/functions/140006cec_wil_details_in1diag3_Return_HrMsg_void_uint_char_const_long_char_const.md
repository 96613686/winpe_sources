# wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)

- ea: `0x140006cec`
- end: `0x140006d23`
- name: `?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ`
- size: `55`
- prototype: `void(wil::details::in1diag3 *this, void *, int, const char *, __int64, const char *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006038`
- `0x1400068b4`

## callees

- `0x14000612c`

## pseudocode

```c
void wil::details::in1diag3::Return_HrMsg(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        __int64 a5,
        const char *a6,
        ...)
{
  int v6; // [rsp+20h] [rbp-48h]
  wil::details *v7; // [rsp+30h] [rbp-38h]
  __int64 retaddr; // [rsp+68h] [rbp+0h]

  LODWORD(v7) = (_DWORD)a4;
  wil::details::ReportFailure_HrMsg<1>((int)this, (int)a2, a3, (int)a4, v6, retaddr, v7, a5, (va_list)&a6);
}

```

## disassembly

```asm
0x140006cec  mov     r11, rsp
0x140006cef  sub     rsp, 68h
0x140006cf3  mov     qword ptr [r11-18h], 0
0x140006cfb  lea     rax, [r11+30h]
0x140006cff  mov     r10, [rsp+68h]
0x140006d04  mov     [r11-28h], rax
0x140006d08  mov     rax, [r11+28h]
0x140006d0c  mov     [r11-30h], rax
0x140006d10  mov     [r11-38h], r9d
0x140006d14  mov     [r11-40h], r10
0x140006d18  call    ??$ReportFailure_HrMsg@$00@details@wil@@YAXPEAXIPEBD110J1PEAD@Z; wil::details::ReportFailure_HrMsg<1>(void *,uint,char const *,char const *,char const *,void *,long,char const *,char *)
0x140006d1d  nop
0x140006d1e  add     rsp, 68h
0x140006d22  retn
```
