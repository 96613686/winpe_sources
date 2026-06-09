# wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)

- ea: `0x180009088`
- end: `0x1800090bf`
- name: `?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ`
- size: `55`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int, const char *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007438`
- `0x18000799c`
- `0x180008230`

## callees

- `0x1800059a8`

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
0x180009088  mov     r11, rsp
0x18000908b  sub     rsp, 68h
0x18000908f  mov     qword ptr [r11-18h], 0
0x180009097  lea     rax, [r11+30h]
0x18000909b  mov     r10, [rsp+68h]
0x1800090a0  mov     [r11-28h], rax
0x1800090a4  mov     rax, [r11+28h]
0x1800090a8  mov     [r11-30h], rax
0x1800090ac  mov     [r11-38h], r9d
0x1800090b0  mov     [r11-40h], r10
0x1800090b4  call    ??$ReportFailure_HrMsg@$00@details@wil@@YAXPEAXIPEBD110J1PEAD@Z; wil::details::ReportFailure_HrMsg<1>(void *,uint,char const *,char const *,char const *,void *,long,char const *,char *)
0x1800090b9  nop
0x1800090ba  add     rsp, 68h
0x1800090be  retn
```
