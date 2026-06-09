# RenderCommon::SafeIntExceptionHandler<PrintCore::WindowsError>::SafeIntOnOverflow(void)

- ea: `0x18000d8f8`
- end: `0x18000d933`
- name: `?SafeIntOnOverflow@?$SafeIntExceptionHandler@VWindowsError@PrintCore@@@RenderCommon@@SAXXZ`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c89c`
- `0x18000d93c`
- `0x18000d9dc`

## callees

- `0x1800021a0`
- `0x18000a0ac`

## pseudocode

```c
void __noreturn RenderCommon::SafeIntExceptionHandler<PrintCore::WindowsError>::SafeIntOnOverflow()
{
  _BYTE pExceptionObject[72]; // [rsp+30h] [rbp-48h] BYREF

  PrintCore::WindowsError::WindowsError(
    (PrintCore::WindowsError *)pExceptionObject,
    -1073741675,
    "Safe Int Overflow",
    word_180012D7A,
    0);
  throw (PrintCore::WindowsError *)pExceptionObject;
}

```

## disassembly

```asm
0x18000d8f8  sub     rsp, 78h
0x18000d8fc  lea     r9, word_180012D7A; char *
0x18000d903  mov     [rsp+78h+var_58], 0; unsigned int
0x18000d90b  lea     r8, aSafeIntOverflo; "Safe Int Overflow"
0x18000d912  mov     edx, 0C0000095h; int
0x18000d917  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18000d91c  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x18000d921  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x18000d928  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000d92d  call    _CxxThrowException_0
```
