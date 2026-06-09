# DllCanUnloadNow

- ea: `0x180017ba0`
- end: `0x180017bac`
- name: `DllCanUnloadNow`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return CComProcessCounter<0>::g_lServerLockCount != 0;
}

```

## disassembly

```asm
0x180017ba0  xor     eax, eax
0x180017ba2  cmp     cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA, eax; long CComProcessCounter<0>::g_lServerLockCount
0x180017ba8  setnz   al
0x180017bab  retn
```
