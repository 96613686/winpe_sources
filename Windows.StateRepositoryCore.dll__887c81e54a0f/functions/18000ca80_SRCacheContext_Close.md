# SRCacheContext_Close

- ea: `0x18000ca80`
- end: `0x18000ca93`
- name: `SRCacheContext_Close`
- size: `19`
- prototype: `HKEY *__fastcall(HKEY *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000bf7c`
- `0x18000ca80`

## pseudocode

```c
HKEY *__fastcall SRCacheContext_Close(HKEY *a1)
{
  HKEY *result; // rax

  if ( a1 )
    return SRCacheContext::`scalar deleting destructor'(a1);
  return result;
}

```

## disassembly

```asm
0x18000ca80  sub     rsp, 28h
0x18000ca84  test    rcx, rcx
0x18000ca87  jz      short loc_18000CA8E
0x18000ca89  call    ??_GSRCacheContext@@QEAAPEAXI@Z; SRCacheContext::`scalar deleting destructor'(uint)
0x18000ca8e  add     rsp, 28h
0x18000ca92  retn
```
