# DecrementServerReferenceCount(void)

- ea: `0x180006034`
- end: `0x18000604f`
- name: `?DecrementServerReferenceCount@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `23`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004860`
- `0x180008ca0`
- `0x180014558`
- `0x180017680`
- `0x18001aa50`
- `0x18001db28`
- `0x18001ee18`
- `0x1800201c0`
- `0x1800209c0`
- `0x180021250`
- `0x180024960`
- `0x1800251f0`
- `0x180026150`
- `0x180029394`
- `0x18002b81c`
- `0x18002bd10`
- `0x18002c248`
- `0x18002c970`
- `0x18002d10c`
- `0x180033440`
- `0x180034194`
- `0x1800350a0`
- `0x180035e00`

## callees

- `0x180006034`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180006042`
- `combase!__imp_CoReleaseSharedService` at `0x180006042`

## pseudocode

```c
__int64 DecrementServerReferenceCount(void)
{
  if ( RWService::g_ulServiceId )
    CoReleaseSharedService();
  return 0;
}

```

## disassembly

```asm
0x180006034  sub     rsp, 28h
0x180006038  mov     ecx, cs:?g_ulServiceId@RWService@@2KA; ulong RWService::g_ulServiceId
0x18000603e  test    ecx, ecx
0x180006040  jz      short loc_180006048
0x180006042  call    cs:__imp_CoReleaseSharedService
0x180006048  xor     eax, eax
0x18000604a  add     rsp, 28h
0x18000604e  retn
```
