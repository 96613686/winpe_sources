# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180005b28`
- end: `0x180005b46`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `43`
- callee_count: `1`
- tags: ``

## callers

- `0x1800040b4`
- `0x180004d50`
- `0x180005434`
- `0x180005f94`
- `0x180006d60`
- `0x180006dd0`
- `0x180006e40`
- `0x180006eb0`
- `0x180006f20`
- `0x180006fc0`
- `0x180007020`
- `0x1800070d0`
- `0x180007c88`
- `0x180007e38`
- `0x180008040`
- `0x180008190`
- `0x1800082d0`
- `0x1800084a0`
- `0x1800087b0`
- `0x180008948`
- `0x180008a9c`
- `0x180008d10`
- `0x180008fe0`
- `0x1800090dc`
- `0x180009330`
- `0x1800095fc`
- `0x18000d2a0`
- `0x18000d3f8`
- `0x18000ddf4`
- `0x18000df50`
- `0x18000e2c8`
- `0x18000eb3c`
- `0x18000eeec`
- `0x18000ef9c`
- `0x18000f0b8`
- `0x18000f270`
- `0x18000f5f0`
- `0x18000f710`
- `0x18000f814`
- `0x18000f910`
- `0x18000fa9c`
- `0x18000fba4`
- `0x18000ff2c`

## callees

- `0x180003750`

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
0x180005b28  sub     rsp, 48h
0x180005b2c  mov     rax, [rsp+48h]
0x180005b31  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180005b36  mov     [rsp+48h+var_20], rax; __int64
0x180005b3b  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005b40  add     rsp, 48h
0x180005b44  retn
```
