# _com_issue_error(long)

- ea: `0x140008c18`
- end: `0x140008c24`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `12`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000476c`
- `0x140009170`
- `0x1400091e0`
- `0x14001900c`

## callees

- `0x140008d0c`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1)
{
  _com_raise_error(a1, 0);
}

```

## disassembly

```asm
0x140008c18  sub     rsp, 28h
0x140008c1c  xor     edx, edx; struct IErrorInfo *
0x140008c1e  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
