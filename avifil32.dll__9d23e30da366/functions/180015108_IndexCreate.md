# IndexCreate

- ea: `0x180015108`
- end: `0x18001513c`
- name: `IndexCreate`
- size: `52`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a060`
- `0x18000b25c`

## callees

- `0x180015108`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001511f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001511f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180015116`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180015116`

## pseudocode

```c
_DWORD *IndexCreate()
{
  HGLOBAL v0; // rax
  _DWORD *result; // rax

  v0 = GlobalAlloc(0x2042u, 0x1808u);
  result = GlobalLock(v0);
  if ( result )
  {
    *result = 0;
    result[1] = 512;
  }
  return result;
}

```

## disassembly

```asm
0x180015108  sub     rsp, 28h
0x18001510c  mov     edx, 1808h; dwBytes
0x180015111  mov     ecx, 2042h; uFlags
0x180015116  call    cs:__imp_GlobalAlloc
0x18001511c  mov     rcx, rax; hMem
0x18001511f  call    cs:__imp_GlobalLock
0x180015125  test    rax, rax
0x180015128  jz      short loc_180015137
0x18001512a  mov     dword ptr [rax], 0
0x180015130  mov     dword ptr [rax+4], 200h
0x180015137  add     rsp, 28h
0x18001513b  retn
```
