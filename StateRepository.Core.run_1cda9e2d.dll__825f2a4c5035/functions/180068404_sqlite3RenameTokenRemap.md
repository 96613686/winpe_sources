# sqlite3RenameTokenRemap

- ea: `0x180068404`
- end: `0x18006841f`
- name: `sqlite3RenameTokenRemap`
- size: `27`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d01c`
- `0x180017fac`
- `0x180031b38`
- `0x18004bb50`
- `0x18004ed80`
- `0x18004f6d8`
- `0x18005eea8`
- `0x18006cdd8`
- `0x18007eb60`
- `0x18007eba0`
- `0x180086e18`

## callees

- `0x180068404`

## pseudocode

```c
_QWORD *__fastcall sqlite3RenameTokenRemap(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *result; // rax

  for ( result = *(_QWORD **)(a1 + 416); result; result = (_QWORD *)result[3] )
  {
    if ( *result == a3 )
    {
      *result = a2;
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180068404  mov     rax, [rcx+1A0h]
0x18006840b  test    rax, rax
0x18006840e  jz      short locret_18006841E
0x180068410  cmp     [rax], r8
0x180068413  jz      short loc_18006841B
0x180068415  mov     rax, [rax+18h]
0x180068419  jmp     short loc_18006840B
0x18006841b  mov     [rax], rdx
0x18006841e  retn
```
