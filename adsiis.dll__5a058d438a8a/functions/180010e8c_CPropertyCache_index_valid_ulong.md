# CPropertyCache::index_valid(ulong)

- ea: `0x180010e8c`
- end: `0x180010e9d`
- name: `?index_valid@CPropertyCache@@QEAAHK@Z`
- size: `17`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b00`
- `0x180010ac4`
- `0x180011034`

## callees

- `0x180010e8c`

## pseudocode

```c
bool __fastcall CPropertyCache::index_valid(CPropertyCache *this, unsigned int a2)
{
  int v2; // ecx
  bool result; // al

  v2 = *((_DWORD *)this + 2);
  result = 0;
  if ( v2 )
    return a2 <= v2 - 1;
  return result;
}

```

## disassembly

```asm
0x180010e8c  mov     ecx, [rcx+8]
0x180010e8f  xor     eax, eax
0x180010e91  test    ecx, ecx
0x180010e93  jz      short locret_180010E9C
0x180010e95  dec     ecx
0x180010e97  cmp     edx, ecx
0x180010e99  setbe   al
0x180010e9c  retn
```
