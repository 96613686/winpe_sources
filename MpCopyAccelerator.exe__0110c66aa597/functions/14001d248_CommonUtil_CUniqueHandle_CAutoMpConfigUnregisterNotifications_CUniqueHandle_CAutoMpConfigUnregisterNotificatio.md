# CommonUtil::CUniqueHandle<CAutoMpConfigUnregisterNotifications>::~CUniqueHandle<CAutoMpConfigUnregisterNotifications>(void)

- ea: `0x14001d248`
- end: `0x14001d25f`
- name: `??1?$CUniqueHandle@UCAutoMpConfigUnregisterNotifications@@@CommonUtil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400262d7`

## callees

- `0x14001d248`

## import_xrefs

- `MpClient!MpConfigUnregisterNotifications` at `0x14001d254`
- `MpClient!MpConfigUnregisterNotifications` at `0x14001d254`

## pseudocode

```c
__int64 __fastcall CommonUtil::CUniqueHandle<CAutoMpConfigUnregisterNotifications>::~CUniqueHandle<CAutoMpConfigUnregisterNotifications>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return MpConfigUnregisterNotifications();
  return result;
}

```

## disassembly

```asm
0x14001d248  sub     rsp, 28h
0x14001d24c  mov     rcx, [rcx]
0x14001d24f  test    rcx, rcx
0x14001d252  jz      short loc_14001D25A
0x14001d254  call    cs:__imp_MpConfigUnregisterNotifications
0x14001d25a  add     rsp, 28h
0x14001d25e  retn
```
