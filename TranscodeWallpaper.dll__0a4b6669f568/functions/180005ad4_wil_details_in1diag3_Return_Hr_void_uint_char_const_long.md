# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180005ad4`
- end: `0x180005af2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e88`
- `0x180004258`
- `0x180004ec4`
- `0x18000659c`
- `0x180007c8c`
- `0x18000a1a8`

## callees

- `0x180003178`

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
0x180005ad4  sub     rsp, 48h
0x180005ad8  mov     rax, [rsp+48h]
0x180005add  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180005ae2  mov     [rsp+48h+var_20], rax; __int64
0x180005ae7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005aec  nop
0x180005aed  add     rsp, 48h
0x180005af1  retn
```
