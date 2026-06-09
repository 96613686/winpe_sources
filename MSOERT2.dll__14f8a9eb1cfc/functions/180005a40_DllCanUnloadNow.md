# DllCanUnloadNow

- ea: `0x180005a40`
- end: `0x180005a6d`
- name: `DllCanUnloadNow`
- size: `45`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005a40`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax
  __int32 v1; // ecx

  result = 1;
  v1 = _InterlockedExchange(&g_cRef, g_cRef);
  if ( v1 == g_cRef )
    return _InterlockedExchange(&g_cLock, g_cLock) != 0;
  return result;
}

```

## disassembly

```asm
0x180005a40  mov     ecx, cs:?g_cRef@@3JA; long g_cRef
0x180005a46  mov     eax, 1
0x180005a4b  xchg    ecx, cs:?g_cRef@@3JA; long g_cRef
0x180005a51  cmp     ecx, cs:?g_cRef@@3JA; long g_cRef
0x180005a57  jnz     short locret_180005A6C
0x180005a59  mov     edx, cs:?g_cLock@@3JA; long g_cLock
0x180005a5f  xor     ecx, ecx
0x180005a61  xchg    edx, cs:?g_cLock@@3JA; long g_cLock
0x180005a67  test    edx, edx
0x180005a69  cmovz   eax, ecx
0x180005a6c  retn
```
