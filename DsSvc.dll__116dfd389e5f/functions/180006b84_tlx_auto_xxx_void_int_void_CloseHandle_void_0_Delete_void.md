# tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)

- ea: `0x180006b84`
- end: `0x180006b9b`
- name: `?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ`
- size: `23`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000417c`
- `0x1800043cc`
- `0x180006070`
- `0x18000ddb8`
- `0x1800124b0`
- `0x180012748`
- `0x1800129fc`
- `0x180014574`
- `0x180014a18`
- `0x18001a06c`

## callees

- `0x180006b84`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b90`

## pseudocode

```c
BOOL __fastcall tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(void **a1)
{
  void *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return CloseHandle(v1);
  return result;
}

```

## disassembly

```asm
0x180006b84  sub     rsp, 28h
0x180006b88  mov     rcx, [rcx]; hObject
0x180006b8b  test    rcx, rcx
0x180006b8e  jz      short loc_180006B96
0x180006b90  call    cs:__imp_CloseHandle
0x180006b96  add     rsp, 28h
0x180006b9a  retn
```
