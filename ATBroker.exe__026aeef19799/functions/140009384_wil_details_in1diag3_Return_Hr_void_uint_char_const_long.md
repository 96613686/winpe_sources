# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140009384`
- end: `0x1400093a1`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400040c8`
- `0x140004498`
- `0x140004974`
- `0x1400064b8`
- `0x140009e9c`
- `0x14000c8b4`
- `0x140011c60`

## callees

- `0x140002f2c`

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
0x140009384  sub     rsp, 48h
0x140009388  mov     rax, [rsp+48h]
0x14000938d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140009392  mov     [rsp+48h+var_20], rax; __int64
0x140009397  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000939c  add     rsp, 48h
0x1400093a0  retn
```
