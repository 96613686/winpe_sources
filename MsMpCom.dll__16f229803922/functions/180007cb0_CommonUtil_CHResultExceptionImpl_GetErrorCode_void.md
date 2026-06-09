# CommonUtil::CHResultExceptionImpl::GetErrorCode(void)

- ea: `0x180007cb0`
- end: `0x180007cb4`
- name: `?GetErrorCode@CHResultExceptionImpl@CommonUtil@@UEBAJXZ`
- size: `4`
- prototype: `__int64 __fastcall(CommonUtil::CHResultExceptionImpl *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CommonUtil::CHResultExceptionImpl::GetErrorCode(CommonUtil::CHResultExceptionImpl *this)
{
  return *((unsigned int *)this + 10);
}

```

## disassembly

```asm
0x180007cb0  mov     eax, [rcx+28h]
0x180007cb3  retn
```
