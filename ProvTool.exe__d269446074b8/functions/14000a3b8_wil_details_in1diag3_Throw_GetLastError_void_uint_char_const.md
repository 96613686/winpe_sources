# wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)

- ea: `0x14000a3b8`
- end: `0x14000a3cc`
- name: `?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ab6c`
- `0x14000b454`
- `0x14000be30`
- `0x14000cd30`

## callees

- `0x140009d64`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>((int)this, (int)a2, a3, (int)a4, v4, retaddr);
}

```

## disassembly

```asm
0x14000a3b8  sub     rsp, 38h
0x14000a3bc  mov     rax, [rsp+38h]
0x14000a3c1  mov     [rsp+38h+var_10], rax; char *
0x14000a3c6  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
