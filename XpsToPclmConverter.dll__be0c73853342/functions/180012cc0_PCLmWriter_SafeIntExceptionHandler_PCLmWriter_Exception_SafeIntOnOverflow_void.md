# PCLmWriter::SafeIntExceptionHandler<PCLmWriter::Exception>::SafeIntOnOverflow(void)

- ea: `0x180012cc0`
- end: `0x180012d00`
- name: `?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@PCLmWriter@@@PCLmWriter@@SAXXZ`
- size: `64`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180012340`
- `0x180012c90`
- `0x180015de4`
- `0x180016da4`
- `0x180018420`
- `0x18001a3a0`

## callees

- `0x180002154`
- `0x18000f3e0`
- `0x180011600`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __noreturn PCLmWriter::SafeIntExceptionHandler<PCLmWriter::Exception>::SafeIntOnOverflow()
{
  _BYTE v0[32]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+40h] [rbp-48h] BYREF

  std::string::string(v0, "Safe Int Overflow");
  PCLmWriter::Exception::Exception((std::exception *)pExceptionObject, (__int64)v0, 0x80048601);
  throw (PCLmWriter::Exception *)pExceptionObject;
}

```

## disassembly

```asm
0x180012cc0  sub     rsp, 88h
0x180012cc7  lea     rdx, aSafeIntOverflo; "Safe Int Overflow"
0x180012cce  lea     rcx, [rsp+88h+var_68]
0x180012cd3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180012cd8  nop
0x180012cd9  mov     r8d, 80048601h
0x180012cdf  lea     rdx, [rsp+88h+var_68]
0x180012ce4  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180012ce9  call    ??0Exception@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; PCLmWriter::Exception::Exception(std::string const &,long)
0x180012cee  lea     rdx, _TI2?AVException@PCLmWriter@@; pThrowInfo
0x180012cf5  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180012cfa  call    _CxxThrowException_0
```
