# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180005db4`
- end: `0x180005dd2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800038c8`
- `0x180003cd4`
- `0x1800051a4`
- `0x18000698c`
- `0x180007918`
- `0x180009f70`
- `0x18000a5f0`
- `0x18000fb9c`
- `0x18000fc90`
- `0x18000fef0`
- `0x18000ffe8`
- `0x18001010c`

## callees

- `0x180002c30`

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
0x180005db4  sub     rsp, 48h
0x180005db8  mov     rax, [rsp+48h]
0x180005dbd  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180005dc2  mov     [rsp+48h+var_20], rax; __int64
0x180005dc7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005dcc  nop
0x180005dcd  add     rsp, 48h
0x180005dd1  retn
```
