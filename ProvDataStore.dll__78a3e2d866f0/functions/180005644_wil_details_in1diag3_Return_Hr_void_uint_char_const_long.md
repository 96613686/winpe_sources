# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180005644`
- end: `0x180005662`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180003670`
- `0x180003a9c`
- `0x180004868`
- `0x18000608c`
- `0x180007050`
- `0x1800095e8`
- `0x180009aa0`
- `0x180009bd0`
- `0x18000c070`
- `0x18000cd94`
- `0x18000e184`

## callees

- `0x18000291c`

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
0x180005644  sub     rsp, 48h
0x180005648  mov     rax, [rsp+48h]
0x18000564d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180005652  mov     [rsp+48h+var_20], rax; __int64
0x180005657  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000565c  nop
0x18000565d  add     rsp, 48h
0x180005661  retn
```
