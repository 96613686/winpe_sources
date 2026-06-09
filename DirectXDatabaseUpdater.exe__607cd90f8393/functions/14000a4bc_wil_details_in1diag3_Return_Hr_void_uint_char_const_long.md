# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x14000a4bc`
- end: `0x14000a4da`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `33`
- callee_count: `1`
- tags: ``

## callers

- `0x1400066d8`
- `0x140006844`
- `0x140006a40`
- `0x140007980`
- `0x140007ad8`
- `0x140008a14`
- `0x140008b78`
- `0x14000b0cc`
- `0x14000d038`
- `0x14000d0bc`
- `0x14000d384`
- `0x14000d940`
- `0x14000fa90`
- `0x14000ff7c`
- `0x1400100e0`
- `0x140010ac0`
- `0x140010c84`
- `0x140010ce8`
- `0x140011418`
- `0x140011674`
- `0x140011804`
- `0x1400120b0`
- `0x14001225c`
- `0x1400122f8`
- `0x1400136f0`
- `0x14001376c`
- `0x140013d10`
- `0x140013f5c`
- `0x140014900`
- `0x140014be4`
- `0x140014db4`
- `0x1400181fc`
- `0x140018274`

## callees

- `0x1400044e4`

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
0x14000a4bc  sub     rsp, 48h
0x14000a4c0  mov     rax, [rsp+48h]
0x14000a4c5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x14000a4ca  mov     [rsp+48h+var_20], rax; __int64
0x14000a4cf  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000a4d4  nop
0x14000a4d5  add     rsp, 48h
0x14000a4d9  retn
```
