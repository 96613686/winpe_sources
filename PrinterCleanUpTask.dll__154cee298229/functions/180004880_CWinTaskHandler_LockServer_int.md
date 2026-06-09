# CWinTaskHandler::LockServer(int)

- ea: `0x180004880`
- end: `0x180004897`
- name: `?LockServer@CWinTaskHandler@@CAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180004870`

## callees

- `0x180004880`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::LockServer(int a1)
{
  if ( a1 )
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  else
    _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  return 0;
}

```

## disassembly

```asm
0x180004880  test    ecx, ecx
0x180004882  jz      short loc_18000488D
0x180004884  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000488b  jmp     short loc_180004894
0x18000488d  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180004894  xor     eax, eax
0x180004896  retn
```
