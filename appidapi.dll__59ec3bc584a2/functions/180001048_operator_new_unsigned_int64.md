# operator new(unsigned __int64)

- ea: `0x180001048`
- end: `0x18000108f`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180001444`
- `0x1800035a4`
- `0x180009682`
- `0x180009a51`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002270`
- `0x18000227c`

## import_xrefs

- `msvcrt!malloc` at `0x180001062`
- `msvcrt!malloc` at `0x180001062`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  for ( i = Size; ; Size = i )
  {
    result = malloc(Size);
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
0x180001048  push    rbx
0x18000104a  sub     rsp, 40h
0x18000104e  mov     rbx, rcx
0x180001051  jmp     short loc_180001062
0x180001053  mov     rcx, rbx; Size
0x180001056  call    _callnewh_0
0x18000105b  test    eax, eax
0x18000105d  jz      short loc_180001073
0x18000105f  mov     rcx, rbx; Size
0x180001062  call    cs:__imp_malloc
0x180001068  test    rax, rax
0x18000106b  jz      short loc_180001053
0x18000106d  add     rsp, 40h
0x180001071  pop     rbx
0x180001072  retn
0x180001073  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001078  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000107d  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001084  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001089  call    _CxxThrowException_0
```
