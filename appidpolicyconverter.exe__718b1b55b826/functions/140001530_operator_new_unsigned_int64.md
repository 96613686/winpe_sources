# operator new(unsigned __int64)

- ea: `0x140001530`
- end: `0x140001576`
- name: `??2@YAPEAX_K@Z`
- size: `70`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `28`
- callee_count: `5`
- tags: ``

## callers

- `0x140001588`
- `0x1400068bc`
- `0x14000696c`
- `0x140006a24`
- `0x140006ac8`
- `0x140008188`
- `0x14000878c`
- `0x1400091f4`
- `0x1400092a8`
- `0x14000935c`
- `0x140009410`
- `0x140009520`
- `0x1400096c4`
- `0x140009804`
- `0x1400098c0`
- `0x14000b4a4`
- `0x14000dec4`
- `0x14000e340`
- `0x14000eae8`
- `0x14000ef0c`
- `0x14000f44c`
- `0x140010490`
- `0x14001052c`
- `0x140010b2c`
- `0x1400116c8`
- `0x1400134a0`
- `0x140014000`
- `0x14001411a`

## callees

- `0x140001530`
- `0x140001cc4`
- `0x140001cdc`
- `0x140001d1c`
- `0x140009b64`

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
0x140001530  push    rbx
0x140001532  sub     rsp, 40h
0x140001536  mov     rbx, rcx
0x140001539  jmp     short loc_14000154A
0x14000153b  mov     rcx, rbx; Size
0x14000153e  call    _callnewh_0
0x140001543  test    eax, eax
0x140001545  jz      short loc_14000155A
0x140001547  mov     rcx, rbx; Size
0x14000154a  call    malloc_0
0x14000154f  test    rax, rax
0x140001552  jz      short loc_14000153B
0x140001554  add     rsp, 40h
0x140001558  pop     rbx
0x140001559  retn
0x14000155a  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000155f  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140001564  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000156b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140001570  call    _CxxThrowException_0
```
