# CSPath::~CSPath(void)

- ea: `0x18000ca40`
- end: `0x18000ca57`
- name: `??1CSPath@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b089`

## callees

- `0x18000ca40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca4c`

## pseudocode

```c
void __fastcall CSPath::~CSPath(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    LocalFree(v1);
}

```

## disassembly

```asm
0x18000ca40  sub     rsp, 28h
0x18000ca44  mov     rcx, [rcx]; hMem
0x18000ca47  test    rcx, rcx
0x18000ca4a  jz      short loc_18000CA52
0x18000ca4c  call    cs:__imp_LocalFree
0x18000ca52  add     rsp, 28h
0x18000ca56  retn
```
