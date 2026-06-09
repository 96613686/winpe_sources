# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180002c40`
- end: `0x180002c5d`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002270`
- `0x180002c64`

## callees

- `0x180001cc0`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((__int64)this, (int)a2, a3, (__int64)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x180002c40  sub     rsp, 48h
0x180002c44  mov     rax, [rsp+48h]
0x180002c49  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180002c4e  mov     [rsp+48h+var_20], rax; __int64
0x180002c53  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180002c58  add     rsp, 48h
0x180002c5c  retn
```
