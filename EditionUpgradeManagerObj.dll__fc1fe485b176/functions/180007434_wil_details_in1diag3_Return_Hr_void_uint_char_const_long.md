# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180007434`
- end: `0x180007451`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bc4`
- `0x180003f94`
- `0x18000438c`
- `0x180005520`
- `0x180007e20`
- `0x18000de6c`
- `0x18000e0b4`
- `0x18000e2fc`
- `0x18000e544`

## callees

- `0x180002bec`

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
0x180007434  sub     rsp, 48h
0x180007438  mov     rax, [rsp+48h]
0x18000743d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180007442  mov     [rsp+48h+var_20], rax; __int64
0x180007447  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000744c  add     rsp, 48h
0x180007450  retn
```
