# CommonUtil::CUniqueHandle<CommonUtil::CAutoFreeLibrary>::~CUniqueHandle<CommonUtil::CAutoFreeLibrary>(void)

- ea: `0x140023498`
- end: `0x1400234af`
- name: `??1?$CUniqueHandle@UCAutoFreeLibrary@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400259dc`
- `0x140025a37`
- `0x140025a43`

## callees

- `0x140023498`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400234a4`
- `KERNEL32!FreeLibrary` at `0x1400234a4`

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
0x140023498  sub     rsp, 28h
0x14002349c  mov     rcx, [rcx]; hLibModule
0x14002349f  test    rcx, rcx
0x1400234a2  jz      short loc_1400234AA
0x1400234a4  call    cs:__imp_FreeLibrary
0x1400234aa  add     rsp, 28h
0x1400234ae  retn
```
