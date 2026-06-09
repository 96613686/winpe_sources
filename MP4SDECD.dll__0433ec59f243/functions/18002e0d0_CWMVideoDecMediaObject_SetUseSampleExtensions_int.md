# CWMVideoDecMediaObject::SetUseSampleExtensions(int)

- ea: `0x18002e0d0`
- end: `0x18002e0fc`
- name: `?SetUseSampleExtensions@CWMVideoDecMediaObject@@UEAAJH@Z`
- size: `44`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002e0d0`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::SetUseSampleExtensions(CWMVideoDecMediaObject *this, int a2)
{
  int v2; // eax

  if ( !*((_DWORD *)this - 66) )
    return 2147500033LL;
  v2 = *((_DWORD *)this - 60);
  if ( v2 != 1096174935 && v2 != 826496599 )
    return 2147500033LL;
  *((_DWORD *)this + 66) = a2;
  return 0;
}

```

## disassembly

```asm
0x18002e0d0  cmp     dword ptr [rcx-108h], 0
0x18002e0d7  jz      short loc_18002E0F6
0x18002e0d9  mov     eax, [rcx-0F0h]
0x18002e0df  cmp     eax, 41564D57h
0x18002e0e4  jz      short loc_18002E0ED
0x18002e0e6  cmp     eax, 31435657h
0x18002e0eb  jnz     short loc_18002E0F6
0x18002e0ed  mov     [rcx+108h], edx
0x18002e0f3  xor     eax, eax
0x18002e0f5  retn
0x18002e0f6  mov     eax, 80004001h
0x18002e0fb  retn
```
