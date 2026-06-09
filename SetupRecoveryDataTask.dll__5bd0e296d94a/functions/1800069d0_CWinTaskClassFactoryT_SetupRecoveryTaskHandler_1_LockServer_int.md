# CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::LockServer(int)

- ea: `0x1800069d0`
- end: `0x1800069e7`
- name: `?LockServer@?$CWinTaskClassFactoryT@VSetupRecoveryTaskHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800069d0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::LockServer(__int64 a1, int a2)
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
0x1800069d0  test    edx, edx
0x1800069d2  jz      short loc_1800069DD
0x1800069d4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800069db  jmp     short loc_1800069E4
0x1800069dd  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800069e4  xor     eax, eax
0x1800069e6  retn
```
