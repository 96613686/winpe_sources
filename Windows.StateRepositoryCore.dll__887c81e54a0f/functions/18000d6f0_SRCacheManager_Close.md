# SRCacheManager_Close

- ea: `0x18000d6f0`
- end: `0x18000d703`
- name: `SRCacheManager_Close`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d534`
- `0x18000d6f0`

## pseudocode

```c
SRCacheManager *__fastcall SRCacheManager_Close(SRCacheManager *a1)
{
  SRCacheManager *result; // rax

  if ( a1 )
    return SRCacheManager::`scalar deleting destructor'(a1);
  return result;
}

```

## disassembly

```asm
0x18000d6f0  sub     rsp, 28h
0x18000d6f4  test    rcx, rcx
0x18000d6f7  jz      short loc_18000D6FE
0x18000d6f9  call    ??_GSRCacheManager@@QEAAPEAXI@Z; SRCacheManager::`scalar deleting destructor'(uint)
0x18000d6fe  add     rsp, 28h
0x18000d702  retn
```
