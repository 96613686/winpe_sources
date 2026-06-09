# Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)

- ea: `0x18000bde0`
- end: `0x18000bdf5`
- name: `?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `21`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180006b04`
- `0x1800070d4`
- `0x18000f7d0`
- `0x18000fdd0`
- `0x180010420`
- `0x180010710`
- `0x1800109a0`
- `0x180010cc0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bde8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bde8`

## pseudocode

```c
char __fastcall Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(__int64 a1)
{
  LocalFree(*(HLOCAL *)(a1 + 8));
  return 1;
}

```

## disassembly

```asm
0x18000bde0  sub     rsp, 28h
0x18000bde4  mov     rcx, [rcx+8]; hMem
0x18000bde8  call    cs:__imp_LocalFree
0x18000bdee  mov     al, 1
0x18000bdf0  add     rsp, 28h
0x18000bdf4  retn
```
