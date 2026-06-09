# CodeIntegrity::Management::FreeExtRegistry

- ea: `0x18000ad20`
- end: `0x18000ad46`
- name: `CodeIntegrity::Management::FreeExtRegistry`
- size: `38`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a174`
- `0x18000a35c`
- `0x18000ad4c`
- `0x18000b540`
- `0x18000d688`

## callees

- `0x18000ad20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad3a`

## pseudocode

```c
HLOCAL __fastcall CodeIntegrity::Management::FreeExtRegistry(HLOCAL *hMem)
{
  HLOCAL result; // rax

  if ( hMem )
  {
    LocalFree(hMem[3]);
    return LocalFree(hMem);
  }
  return result;
}

```

## disassembly

```asm
0x18000ad20  test    rcx, rcx
0x18000ad23  jz      short locret_18000AD45
0x18000ad25  push    rbx
0x18000ad26  sub     rsp, 20h
0x18000ad2a  mov     rbx, rcx
0x18000ad2d  mov     rcx, [rcx+18h]; hMem
0x18000ad31  call    cs:__imp_LocalFree
0x18000ad37  mov     rcx, rbx; hMem
0x18000ad3a  call    cs:__imp_LocalFree
0x18000ad40  add     rsp, 20h
0x18000ad44  pop     rbx
0x18000ad45  retn
```
