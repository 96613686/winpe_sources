# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800048e4`
- end: `0x180004902`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180002eb8`
- `0x180003288`
- `0x180003e54`
- `0x18000532c`
- `0x180007438`
- `0x180007870`
- `0x18000799c`
- `0x180008230`
- `0x18000a270`
- `0x18000a380`
- `0x18000a870`
- `0x18000a920`
- `0x18000aa70`
- `0x18000ab10`
- `0x18000acd0`

## callees

- `0x1800022f4`

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
0x1800048e4  sub     rsp, 48h
0x1800048e8  mov     rax, [rsp+48h]
0x1800048ed  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800048f2  mov     [rsp+48h+var_20], rax; __int64
0x1800048f7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800048fc  nop
0x1800048fd  add     rsp, 48h
0x180004901  retn
```
