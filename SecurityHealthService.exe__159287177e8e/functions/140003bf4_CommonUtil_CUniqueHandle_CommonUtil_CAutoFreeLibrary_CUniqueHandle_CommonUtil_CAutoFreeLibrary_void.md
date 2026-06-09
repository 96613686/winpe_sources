# CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)

- ea: `0x140003bf4`
- end: `0x140003c0b`
- name: `??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `23`
- prototype: `BOOL __fastcall(HMODULE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001259d`
- `0x1400125af`

## callees

- `0x140003bf4`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140003c00`
- `KERNEL32!FreeLibrary` at `0x140003c00`

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
0x140003bf4  sub     rsp, 28h
0x140003bf8  mov     rcx, [rcx]; hLibModule
0x140003bfb  test    rcx, rcx
0x140003bfe  jz      short loc_140003C06
0x140003c00  call    cs:__imp_FreeLibrary
0x140003c06  add     rsp, 28h
0x140003c0a  retn
```
