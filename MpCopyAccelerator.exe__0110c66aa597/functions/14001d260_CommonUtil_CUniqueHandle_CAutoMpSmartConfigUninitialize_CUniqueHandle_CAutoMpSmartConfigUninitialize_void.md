# CommonUtil::CUniqueHandle<CAutoMpSmartConfigUninitialize>::~CUniqueHandle<CAutoMpSmartConfigUninitialize>(void)

- ea: `0x14001d260`
- end: `0x14001d275`
- name: `??1?$CUniqueHandle@UCAutoMpSmartConfigUninitialize@@@CommonUtil@@QEAA@XZ`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140026264`

## callees

- `0x14001d260`

## import_xrefs

- `MpClient!MpConfigUninitialize` at `0x14001d26a`
- `MpClient!MpConfigUninitialize` at `0x14001d26a`

## pseudocode

```c
__int64 __fastcall CommonUtil::CUniqueHandle<CAutoMpSmartConfigUninitialize>::~CUniqueHandle<CAutoMpSmartConfigUninitialize>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return MpConfigUninitialize();
  return result;
}

```

## disassembly

```asm
0x14001d260  sub     rsp, 28h
0x14001d264  cmp     qword ptr [rcx], 0
0x14001d268  jz      short loc_14001D270
0x14001d26a  call    cs:__imp_MpConfigUninitialize
0x14001d270  add     rsp, 28h
0x14001d274  retn
```
