# CPropertyCache::index_valid(void)

- ea: `0x180010ea4`
- end: `0x180010eb6`
- name: `?index_valid@CPropertyCache@@QEAAHXZ`
- size: `18`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006d90`
- `0x180007dc0`

## callees

- `0x180010ea4`

## pseudocode

```c
bool __fastcall CPropertyCache::index_valid(CPropertyCache *this)
{
  int v1; // edx
  bool result; // al

  v1 = *((_DWORD *)this + 2);
  result = 0;
  if ( v1 )
    return *((_DWORD *)this + 6) <= (unsigned int)(v1 - 1);
  return result;
}

```

## disassembly

```asm
0x180010ea4  mov     edx, [rcx+8]
0x180010ea7  xor     eax, eax
0x180010ea9  test    edx, edx
0x180010eab  jz      short locret_180010EB5
0x180010ead  dec     edx
0x180010eaf  cmp     [rcx+18h], edx
0x180010eb2  setbe   al
0x180010eb5  retn
```
