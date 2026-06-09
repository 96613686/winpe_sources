# NetpApiStatusToNtStatus

- ea: `0x18000db54`
- end: `0x18000db78`
- name: `NetpApiStatusToNtStatus`
- size: `36`
- prototype: `__int64 __fastcall(int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d90`
- `0x1800058e0`
- `0x18000caa0`
- `0x18000d51c`
- `0x180013a30`
- `0x180014750`
- `0x180014c2c`
- `0x18001640c`

## callees

- `0x18000db54`

## pseudocode

```c
__int64 __fastcall NetpApiStatusToNtStatus(int a1)
{
  __int64 i; // rax

  for ( i = 0; (unsigned int)i < 0x7A; i = (unsigned int)(i + 1) )
  {
    if ( LODWORD(ErrorMap[i]) == a1 )
      return HIDWORD(ErrorMap[i]);
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x18000db54  xor     eax, eax
0x18000db56  lea     r8, ErrorMap
0x18000db5d  cmp     eax, 7Ah ; 'z'
0x18000db60  jnb     short loc_18000DB72
0x18000db62  cmp     [r8+rax*8], ecx
0x18000db66  jz      short loc_18000DB6C
0x18000db68  inc     eax
0x18000db6a  jmp     short loc_18000DB5D
0x18000db6c  mov     eax, [r8+rax*8+4]
0x18000db71  retn
0x18000db72  mov     eax, 0C00000E5h
0x18000db77  retn
```
