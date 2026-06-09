# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180006804`
- end: `0x180006822`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023c8`
- `0x18000267c`
- `0x180004140`
- `0x1800046d8`
- `0x180004ae4`
- `0x1800059a8`
- `0x180007340`
- `0x18000752c`
- `0x180007fa0`
- `0x1800095d0`
- `0x18000ab90`
- `0x18000ad54`
- `0x18000b680`
- `0x18000ba5c`
- `0x18000be24`
- `0x18000be8c`

## callees

- `0x1800031f8`

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
0x180006804  sub     rsp, 48h
0x180006808  mov     rax, [rsp+48h]
0x18000680d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006812  mov     [rsp+48h+var_20], rax; __int64
0x180006817  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000681c  nop
0x18000681d  add     rsp, 48h
0x180006821  retn
```
