# CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)

- ea: `0x180006000`
- end: `0x180006017`
- name: `??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009b81`
- `0x180009b93`

## callees

- `0x180006000`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000600c`
- `KERNEL32!FreeLibrary` at `0x18000600c`

## pseudocode

```c
BOOL __fastcall CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(
        HMODULE *a1)
{
  HMODULE v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return FreeLibrary(v1);
  return result;
}

```

## disassembly

```asm
0x180006000  sub     rsp, 28h
0x180006004  mov     rcx, [rcx]; hLibModule
0x180006007  test    rcx, rcx
0x18000600a  jz      short loc_180006012
0x18000600c  call    cs:__imp_FreeLibrary
0x180006012  add     rsp, 28h
0x180006016  retn
```
