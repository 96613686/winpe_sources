# _com_issue_error(long)

- ea: `0x140009474`
- end: `0x14000947e`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `10`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400030e8`
- `0x140003568`

## callees

- `0x140009558`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1, struct IErrorInfo *a2)
{
  _com_raise_error(a1, a2);
}

```

## disassembly

```asm
0x140009474  sub     rsp, 28h
0x140009478  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
