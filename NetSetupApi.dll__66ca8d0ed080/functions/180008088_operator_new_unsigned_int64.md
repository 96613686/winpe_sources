# operator new(unsigned __int64)

- ea: `0x180008088`
- end: `0x1800080ce`
- name: `??2@YAPEAX_K@Z`
- size: `70`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003b90`
- `0x1800069e0`
- `0x180008120`
- `0x1800092b0`
- `0x18000eb78`
- `0x180010f18`
- `0x18001291c`

## callees

- `0x180008030`
- `0x180008088`
- `0x180008912`
- `0x18000892a`
- `0x18000895c`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008088  push    rbx
0x18000808a  sub     rsp, 40h
0x18000808e  mov     rbx, rcx
0x180008091  jmp     short loc_1800080A2
0x180008093  mov     rcx, rbx; Size
0x180008096  call    _callnewh_0
0x18000809b  test    eax, eax
0x18000809d  jz      short loc_1800080B2
0x18000809f  mov     rcx, rbx; Size
0x1800080a2  call    malloc_0
0x1800080a7  test    rax, rax
0x1800080aa  jz      short loc_180008093
0x1800080ac  add     rsp, 40h
0x1800080b0  pop     rbx
0x1800080b1  retn
0x1800080b2  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800080b7  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800080bc  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800080c3  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800080c8  call    _CxxThrowException_0
```
