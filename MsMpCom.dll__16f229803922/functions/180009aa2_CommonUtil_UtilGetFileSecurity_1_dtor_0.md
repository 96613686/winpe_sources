# _CommonUtil::UtilGetFileSecurity_::_1_::dtor$0

- ea: `0x180009aa2`
- end: `0x180009aae`
- name: `_CommonUtil::UtilGetFileSecurity_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007d7c`

## pseudocode

```c
void __fastcall CommonUtil::UtilGetFileSecurity_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CommonUtil::CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>::~CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>((void **)(a2 + 152));
}

```

## disassembly

```asm
0x180009aa2  lea     rcx, [rdx+98h]
0x180009aa9  jmp     ??1?$CUniqueHandle@UCAutoGenericBufferDelete@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>::~CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>(void)
```
