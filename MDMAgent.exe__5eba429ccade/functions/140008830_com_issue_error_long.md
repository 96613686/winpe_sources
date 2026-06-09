# _com_issue_error(long)

- ea: `0x140008830`
- end: `0x14000883c`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `12`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400046a4`
- `0x140008d58`
- `0x140008dc8`
- `0x1400182d8`

## callees

- `0x14000891c`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1)
{
  _com_raise_error(a1, 0);
}

```

## disassembly

```asm
0x140008830  sub     rsp, 28h
0x140008834  xor     edx, edx; struct IErrorInfo *
0x140008836  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
