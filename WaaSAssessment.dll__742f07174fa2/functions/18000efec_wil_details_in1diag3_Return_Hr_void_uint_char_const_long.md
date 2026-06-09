# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18000efec`
- end: `0x18000f009`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c450`
- `0x18000c820`
- `0x18000c990`
- `0x18000ccf0`
- `0x18000cfac`
- `0x18000d300`
- `0x18000d690`
- `0x18000d9e0`
- `0x18000dc30`
- `0x18000dd50`
- `0x18000df40`
- `0x18000e0f0`
- `0x18000e300`
- `0x18000e440`
- `0x18000e530`
- `0x18000e620`
- `0x18000e900`
- `0x18000ea60`
- `0x18000f36c`
- `0x1800114d8`
- `0x180012308`
- `0x180012e08`
- `0x180012fc8`
- `0x1800138d0`
- `0x18001592c`
- `0x180019290`
- `0x1800193b8`
- `0x1800194f4`
- `0x1800195b4`

## callees

- `0x18000bad0`

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
0x18000efec  sub     rsp, 48h
0x18000eff0  mov     rax, [rsp+48h]
0x18000eff5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000effa  mov     [rsp+48h+var_20], rax; __int64
0x18000efff  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000f004  add     rsp, 48h
0x18000f008  retn
```
