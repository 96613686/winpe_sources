# CommonUtil::CHResultExceptionImpl::what(void)

- ea: `0x180007d70`
- end: `0x180007d75`
- name: `?what@CHResultExceptionImpl@CommonUtil@@UEBAPEBDXZ`
- size: `5`
- prototype: `const char *__fastcall(CommonUtil::CHResultExceptionImpl *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
const char *__fastcall CommonUtil::CHResultExceptionImpl::what(CommonUtil::CHResultExceptionImpl *this)
{
  return (char *)this + 24;
}

```

## disassembly

```asm
0x180007d70  lea     rax, [rcx+18h]
0x180007d74  retn
```
