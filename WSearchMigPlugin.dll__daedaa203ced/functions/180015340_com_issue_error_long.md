# _com_issue_error(long)

- ea: `0x180015340`
- end: `0x180015351`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `17`
- prototype: `void __fastcall __noreturn()`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c7f0`
- `0x180011220`
- `0x1800144e0`

## callees

- `0x180015540`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error()
{
  _com_raise_error(-2147024882, 0);
}

```

## disassembly

```asm
0x180015340  sub     rsp, 28h
0x180015344  xor     edx, edx; struct IErrorInfo *
0x180015346  mov     ecx, 8007000Eh; int
0x18001534b  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
