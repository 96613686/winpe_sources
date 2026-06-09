# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800130f8`
- end: `0x180013115`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180010724`
- `0x18001088c`
- `0x180010a54`
- `0x180011830`
- `0x1800122b8`
- `0x1800123dc`
- `0x180013a74`
- `0x180013ae8`

## callees

- `0x18000fc24`

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
0x1800130f8  sub     rsp, 48h
0x1800130fc  mov     rax, [rsp+48h]
0x180013101  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180013106  mov     [rsp+48h+var_20], rax; __int64
0x18001310b  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180013110  add     rsp, 48h
0x180013114  retn
```
