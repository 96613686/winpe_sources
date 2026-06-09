# CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::LockServer(int)

- ea: `0x18000dd20`
- end: `0x18000dd37`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCDrvRecoveryOnRebootHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000dd20`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::LockServer(__int64 a1, int a2)
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
0x18000dd20  test    edx, edx
0x18000dd22  jz      short loc_18000DD2D
0x18000dd24  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000dd2b  jmp     short loc_18000DD34
0x18000dd2d  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000dd34  xor     eax, eax
0x18000dd36  retn
```
