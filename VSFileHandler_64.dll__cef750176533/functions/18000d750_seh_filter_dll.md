# _seh_filter_dll

- ea: `0x18000d750`
- end: `0x18000d763`
- name: `_seh_filter_dll`
- size: `19`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800077e8`

## callees

- `0x18000d750`
- `0x18000d764`

## pseudocode

```c
int __cdecl seh_filter_dll(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  if ( ExceptionNum == -529697949 )
    return seh_filter_exe(0xE06D7363, ExceptionPtr);
  else
    return 0;
}

```

## disassembly

```asm
0x18000d750  mov     eax, 0E06D7363h
0x18000d755  cmp     ecx, eax
0x18000d757  jz      short loc_18000D75C
0x18000d759  xor     eax, eax
0x18000d75b  retn
0x18000d75c  mov     ecx, eax
0x18000d75e  jmp     _seh_filter_exe
```
