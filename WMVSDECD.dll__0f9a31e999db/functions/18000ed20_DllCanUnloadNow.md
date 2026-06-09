# DllCanUnloadNow

- ea: `0x18000ed20`
- end: `0x18000ed3e`
- name: `DllCanUnloadNow`
- size: `30`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ed20`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( dword_180048EC8 > 0 )
    LODWORD(v0) = 1;
  else
    return dword_180048EC4 != 0;
  return v0;
}

```

## disassembly

```asm
0x18000ed20  cmp     cs:dword_180048EC8, 0
0x18000ed27  jg      short loc_18000ED38
0x18000ed29  mov     ecx, cs:dword_180048EC4
0x18000ed2f  xor     eax, eax
0x18000ed31  test    ecx, ecx
0x18000ed33  setnz   al
0x18000ed36  retn
0x18000ed38  mov     eax, 1
0x18000ed3d  retn
```
