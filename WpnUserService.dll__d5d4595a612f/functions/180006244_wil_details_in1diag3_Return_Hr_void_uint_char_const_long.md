# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180006244`
- end: `0x180006262`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800045b8`
- `0x180004988`
- `0x1800056a8`
- `0x180006d0c`
- `0x18000896c`
- `0x180009da8`
- `0x18000a1d8`
- `0x18000b740`
- `0x18000bf30`
- `0x18000e9e8`
- `0x180010444`
- `0x180010884`
- `0x18001096c`

## callees

- `0x1800039c8`

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
0x180006244  sub     rsp, 48h
0x180006248  mov     rax, [rsp+48h]
0x18000624d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006252  mov     [rsp+48h+var_20], rax; __int64
0x180006257  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000625c  nop
0x18000625d  add     rsp, 48h
0x180006261  retn
```
