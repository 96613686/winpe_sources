# _com_issue_error(long)

- ea: `0x18001c484`
- end: `0x18001c490`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `12`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800071e8`
- `0x180007258`
- `0x1800072d0`
- `0x1800079e8`
- `0x18001c4c0`

## callees

- `0x18001c75c`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1)
{
  _com_raise_error(a1, 0);
}

```

## disassembly

```asm
0x18001c484  sub     rsp, 28h
0x18001c488  xor     edx, edx; struct IErrorInfo *
0x18001c48a  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
