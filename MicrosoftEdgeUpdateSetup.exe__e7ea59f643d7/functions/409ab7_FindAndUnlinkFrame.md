# __FindAndUnlinkFrame

- ea: `0x409ab7`
- end: `0x409afe`
- name: `__FindAndUnlinkFrame`
- size: `71`
- prototype: `int __cdecl(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x40ab0d`

## callees

- `0x40943c`
- `0x409ab7`
- `0x40c30b`

## pseudocode

```c
int __cdecl _FindAndUnlinkFrame(int a1)
{
  int v1; // esi
  int result; // eax
  int *i; // ecx
  int v4; // eax

  if ( a1 == *(_DWORD *)(__vcrt_getptd() + 36) )
  {
    v1 = *(_DWORD *)(a1 + 4);
    result = __vcrt_getptd();
    *(_DWORD *)(result + 36) = v1;
  }
  else
  {
    for ( i = (int *)(*(_DWORD *)(__vcrt_getptd() + 36) + 4); ; i = (int *)(v4 + 4) )
    {
      v4 = *i;
      if ( !*i )
        abort();
      if ( a1 == v4 )
        break;
    }
    result = *(_DWORD *)(a1 + 4);
    *i = result;
  }
  return result;
}

```

## disassembly

```asm
0x409ab7  push    ebp
0x409ab8  mov     ebp, esp
0x409aba  push    esi
0x409abb  call    ___vcrt_getptd
0x409ac0  mov     esi, [ebp+arg_0]
0x409ac3  cmp     esi, [eax+24h]
0x409ac6  jnz     short loc_409AD6
0x409ac8  mov     esi, [esi+4]
0x409acb  call    ___vcrt_getptd
0x409ad0  mov     [eax+24h], esi
0x409ad3  pop     esi
0x409ad4  pop     ebp
0x409ad5  retn
0x409ad6  call    ___vcrt_getptd
0x409adb  mov     ecx, [eax+24h]
0x409ade  add     ecx, 4
0x409ae1  jmp     short loc_409AEA
0x409ae3  cmp     esi, eax
0x409ae5  jz      short loc_409AF2
0x409ae7  lea     ecx, [eax+4]
0x409aea  mov     eax, [ecx]
0x409aec  test    eax, eax
0x409aee  jz      short loc_409AF9
0x409af0  jmp     short loc_409AE3
0x409af2  mov     eax, [esi+4]
0x409af5  mov     [ecx], eax
0x409af7  jmp     short loc_409AD3
0x409af9  call    _abort
```
