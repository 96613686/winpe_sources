# CWinTaskHandler::LockServer(int)

- ea: `0x180005920`
- end: `0x180005937`
- name: `?LockServer@CWinTaskHandler@@CAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180005910`

## callees

- `0x180005920`

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
0x180005920  test    ecx, ecx
0x180005922  jz      short loc_18000592D
0x180005924  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000592b  jmp     short loc_180005934
0x18000592d  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180005934  xor     eax, eax
0x180005936  retn
```
