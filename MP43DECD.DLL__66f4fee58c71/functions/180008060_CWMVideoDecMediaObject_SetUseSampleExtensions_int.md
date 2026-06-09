# CWMVideoDecMediaObject::SetUseSampleExtensions(int)

- ea: `0x180008060`
- end: `0x18000808c`
- name: `?SetUseSampleExtensions@CWMVideoDecMediaObject@@UEAAJH@Z`
- size: `44`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008060`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::SetUseSampleExtensions(CWMVideoDecMediaObject *this, int a2)
{
  int v2; // eax

  if ( !*((_DWORD *)this - 62) )
    return 2147500033LL;
  v2 = *((_DWORD *)this - 56);
  if ( v2 != 1096174935 && v2 != 826496599 )
    return 2147500033LL;
  *((_DWORD *)this + 173) = a2;
  return 0;
}

```

## disassembly

```asm
0x180008060  cmp     dword ptr [rcx-0F8h], 0
0x180008067  jz      short loc_180008086
0x180008069  mov     eax, [rcx-0E0h]
0x18000806f  cmp     eax, 41564D57h
0x180008074  jz      short loc_18000807D
0x180008076  cmp     eax, 31435657h
0x18000807b  jnz     short loc_180008086
0x18000807d  mov     [rcx+2B4h], edx
0x180008083  xor     eax, eax
0x180008085  retn
0x180008086  mov     eax, 80004001h
0x18000808b  retn
```
