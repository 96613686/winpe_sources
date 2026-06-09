# USBSTOR_IsDeviceAsyncCapable

- ea: `0x1400090a8`
- end: `0x1400090cd`
- name: `USBSTOR_IsDeviceAsyncCapable`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400084c0`
- `0x140008590`
- `0x140028550`

## callees

- `0x1400090a8`

## pseudocode

```c
bool __fastcall USBSTOR_IsDeviceAsyncCapable(__int64 a1)
{
  bool result; // al

  result = 0;
  if ( *(_QWORD *)(a1 + 112) )
  {
    if ( *(_DWORD *)(a1 + 120) == 1 )
      return (*(_BYTE *)(*(_QWORD *)(a1 + 56) + 7LL) & 0x20) != 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400090a8  xor     al, al
0x1400090aa  cmp     qword ptr [rcx+70h], 0
0x1400090af  jz      short locret_1400090CC
0x1400090b1  mov     r8d, 1
0x1400090b7  cmp     [rcx+78h], r8d
0x1400090bb  jnz     short locret_1400090CC
0x1400090bd  mov     rcx, [rcx+38h]
0x1400090c1  movzx   eax, al
0x1400090c4  test    byte ptr [rcx+7], 20h
0x1400090c8  cmovnz  eax, r8d
0x1400090cc  retn
```
