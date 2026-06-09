# CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>::LockServer(int)

- ea: `0x180014da0`
- end: `0x180014db7`
- name: `?LockServer@?$CComClassFactoryT@VCEditionUpgradeManager@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014da0`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>::LockServer(
        __int64 a1,
        int a2)
{
  if ( a2 )
    _InterlockedIncrement(&CComProcessCounter<0>::g_lServerLockCount);
  else
    _InterlockedDecrement(&CComProcessCounter<0>::g_lServerLockCount);
  return 0;
}

```

## disassembly

```asm
0x180014da0  test    edx, edx
0x180014da2  jz      short loc_180014DAD
0x180014da4  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x180014dab  jmp     short loc_180014DB4
0x180014dad  lock dec cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x180014db4  xor     eax, eax
0x180014db6  retn
```
