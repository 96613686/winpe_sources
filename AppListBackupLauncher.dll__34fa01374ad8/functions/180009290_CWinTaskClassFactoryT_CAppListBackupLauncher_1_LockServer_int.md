# CWinTaskClassFactoryT<CAppListBackupLauncher,1>::LockServer(int)

- ea: `0x180009290`
- end: `0x1800092a7`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCAppListBackupLauncher@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180009290`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CAppListBackupLauncher,1>::LockServer(__int64 a1, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  else
    _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  return 0;
}

```

## disassembly

```asm
0x180009290  test    edx, edx
0x180009292  jz      short loc_18000929D
0x180009294  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000929b  jmp     short loc_1800092A4
0x18000929d  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800092a4  xor     eax, eax
0x1800092a6  retn
```
