# CommonUtil::CHResultExceptionImpl::GetErrorCode(void)

- ea: `0x14000e5b0`
- end: `0x14000e5b4`
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
0x14000e5b0  mov     eax, [rcx+28h]
0x14000e5b3  retn
```
