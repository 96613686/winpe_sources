# CWiaExtensionHost64Factory::LockServer(int)

- ea: `0x180001f30`
- end: `0x180001f47`
- name: `?LockServer@CWiaExtensionHost64Factory@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(CWiaExtensionHost64Factory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001f30`

## pseudocode

```c
__int64 __fastcall CWiaExtensionHost64Factory::LockServer(CWiaExtensionHost64Factory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
  else
    _InterlockedDecrement((volatile signed __int32 *)&g_cRef);
  return 0;
}

```

## disassembly

```asm
0x180001f30  test    edx, edx
0x180001f32  jz      short loc_180001F3D
0x180001f34  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x180001f3b  jmp     short loc_180001F44
0x180001f3d  lock dec cs:?g_cRef@@3KA; ulong g_cRef
0x180001f44  xor     eax, eax
0x180001f46  retn
```
