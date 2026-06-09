# _com_issue_error(long)

- ea: `0x180003894`
- end: `0x1800038a0`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `12`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `50`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800034a4`
- `0x18000381c`
- `0x180003870`
- `0x180003d64`
- `0x180003f0c`
- `0x1800051bc`
- `0x180016474`
- `0x180016540`
- `0x18001681c`
- `0x180016bf4`
- `0x180017aa4`
- `0x180018860`
- `0x180019ae8`
- `0x18001a168`
- `0x18001a260`
- `0x18002c684`
- `0x18002d468`
- `0x18002e1b0`
- `0x18002ee48`
- `0x180030be4`
- `0x180030c5c`
- `0x180031d50`
- `0x1800330a4`
- `0x180034078`
- `0x18003757c`
- `0x180038898`
- `0x18004113c`
- `0x180041364`
- `0x1800419c4`
- `0x18004c9dc`
- `0x18004d27c`
- `0x18004d2c4`
- `0x18004d30c`
- `0x18004d354`
- `0x18004d400`
- `0x18004d4b4`
- `0x18004de38`
- `0x18004f400`
- `0x18004f6e0`
- `0x18004f7d0`
- `0x18004f960`
- `0x18004fa50`
- `0x18004fb70`
- `0x18004fc60`
- `0x180050b70`
- `0x180055740`
- `0x180058e10`
- `0x1800594e0`
- `0x180059860`
- `0x18005d528`

## callees

- `0x180036b9c`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1)
{
  _com_raise_error(a1, 0);
}

```

## disassembly

```asm
0x180003894  sub     rsp, 28h
0x180003898  xor     edx, edx; struct IErrorInfo *
0x18000389a  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
