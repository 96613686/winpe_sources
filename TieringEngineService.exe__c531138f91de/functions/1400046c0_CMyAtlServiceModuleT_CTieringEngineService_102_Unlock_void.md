# CMyAtlServiceModuleT<CTieringEngineService,102>::Unlock(void)

- ea: `0x1400046c0`
- end: `0x1400046cb`
- name: `?Unlock@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@UEAAJXZ`
- size: `11`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CMyAtlServiceModuleT<CTieringEngineService,102>::Unlock(__int64 a1)
{
  return (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(a1 + 12));
}

```

## disassembly

```asm
0x1400046c0  or      eax, 0FFFFFFFFh
0x1400046c3  lock xadd [rcx+0Ch], eax
0x1400046c8  dec     eax
0x1400046ca  retn
```
