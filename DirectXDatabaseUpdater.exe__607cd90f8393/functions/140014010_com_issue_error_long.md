# _com_issue_error(long)

- ea: `0x140014010`
- end: `0x140014021`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `17`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400135c0`

## callees

- `0x1400140fc`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error()
{
  _com_raise_error(-2147024882, 0);
}

```

## disassembly

```asm
0x140014010  sub     rsp, 28h
0x140014014  xor     edx, edx; struct IErrorInfo *
0x140014016  mov     ecx, 8007000Eh; int
0x14001401b  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
