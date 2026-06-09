# CWinTaskHandler::LockServer(int)

- ea: `0x18000c5d0`
- end: `0x18000c5e7`
- name: `?LockServer@CWinTaskHandler@@CAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x18000c5c0`

## callees

- `0x18000c5d0`

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
0x18000c5d0  test    ecx, ecx
0x18000c5d2  jz      short loc_18000C5DD
0x18000c5d4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000c5db  jmp     short loc_18000C5E4
0x18000c5dd  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000c5e4  xor     eax, eax
0x18000c5e6  retn
```
