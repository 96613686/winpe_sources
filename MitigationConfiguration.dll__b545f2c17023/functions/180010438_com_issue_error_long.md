# _com_issue_error(long)

- ea: `0x180010438`
- end: `0x180010444`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `12`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fc90`

## callees

- `0x180010608`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1)
{
  _com_raise_error(a1, 0);
}

```

## disassembly

```asm
0x180010438  sub     rsp, 28h
0x18001043c  xor     edx, edx; struct IErrorInfo *
0x18001043e  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
