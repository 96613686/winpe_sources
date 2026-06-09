# __seh_filter_dll

- ea: `0x10015fb5`
- end: `0x10015fd5`
- name: `__seh_filter_dll`
- size: `32`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10010dd6`

## callees

- `0x10015fb5`
- `0x10015fd5`

## pseudocode

```c
int __cdecl _seh_filter_dll(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  if ( ExceptionNum == -529697949 )
    return _seh_filter_exe(0xE06D7363, ExceptionPtr);
  else
    return 0;
}

```

## disassembly

```asm
0x10015fb5  mov     edi, edi
0x10015fb7  push    ebp
0x10015fb8  mov     ebp, esp
0x10015fba  mov     eax, 0E06D7363h
0x10015fbf  cmp     [ebp+ExceptionNum], eax
0x10015fc2  jz      short loc_10015FC8
0x10015fc4  xor     eax, eax
0x10015fc6  pop     ebp
0x10015fc7  retn
0x10015fc8  push    [ebp+ExceptionPtr]; ExceptionPtr
0x10015fcb  push    eax; ExceptionNum
0x10015fcc  call    __seh_filter_exe
0x10015fd1  pop     ecx
0x10015fd2  pop     ecx
0x10015fd3  pop     ebp
0x10015fd4  retn
```
