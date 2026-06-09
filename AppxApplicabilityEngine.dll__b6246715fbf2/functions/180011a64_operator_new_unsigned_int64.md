# operator new(unsigned __int64)

- ea: `0x180011a64`
- end: `0x180011aab`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `66`
- callee_count: `4`
- tags: ``

## callers

- `0x180001a78`
- `0x180001d88`
- `0x180001ef0`
- `0x180004494`
- `0x1800046f8`
- `0x180004e60`
- `0x180009f34`
- `0x18000a468`
- `0x18000a5dc`
- `0x18000abd0`
- `0x18000ad10`
- `0x18000b8d8`
- `0x18000bb30`
- `0x18000c694`
- `0x18000c738`
- `0x18000c8a0`
- `0x18000d7ec`
- `0x18000d84c`
- `0x18000e2c0`
- `0x18000e498`
- `0x18000f1b4`
- `0x18000f418`
- `0x180010590`
- `0x180010754`
- `0x18001201c`
- `0x18001206c`
- `0x180013860`
- `0x180013878`
- `0x180016db8`
- `0x1800176b4`
- `0x180018120`
- `0x1800181d8`
- `0x180018260`
- `0x180018300`
- `0x18001836c`
- `0x18001849c`
- `0x18001852c`
- `0x18001865c`
- `0x180018b84`
- `0x180018c8c`
- `0x180018dd0`
- `0x180018ea4`
- `0x180018f08`
- `0x180019080`
- `0x180019798`
- `0x18001a144`
- `0x18001a248`
- `0x18001a380`
- `0x18001b7bc`
- `0x18001e964`

## callees

- `0x180011a1c`
- `0x180011a64`
- `0x180013288`
- `0x180013294`

## import_xrefs

- `msvcrt!malloc` at `0x180011a7e`
- `msvcrt!malloc` at `0x180011a7e`

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
0x180011a64  push    rbx
0x180011a66  sub     rsp, 40h
0x180011a6a  mov     rbx, rcx
0x180011a6d  jmp     short loc_180011A7E
0x180011a6f  mov     rcx, rbx; Size
0x180011a72  call    _callnewh_0
0x180011a77  test    eax, eax
0x180011a79  jz      short loc_180011A8F
0x180011a7b  mov     rcx, rbx; Size
0x180011a7e  call    cs:__imp_malloc
0x180011a84  test    rax, rax
0x180011a87  jz      short loc_180011A6F
0x180011a89  add     rsp, 40h
0x180011a8d  pop     rbx
0x180011a8e  retn
0x180011a8f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180011a94  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180011a99  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180011aa0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180011aa5  call    _CxxThrowException_0
```
