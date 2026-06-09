# _com_issue_error(long)

- ea: `0x140009aa4`
- end: `0x140009aae`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `10`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003184`
- `0x1400035f0`

## callees

- `0x140009b90`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1, struct IErrorInfo *a2)
{
  _com_raise_error(a1, a2);
}

```

## disassembly

```asm
0x140009aa4  sub     rsp, 28h
0x140009aa8  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
