# CommonUtil::CUniqueHandle<CommonUtil::CMpUtilsUninitialize>::~CUniqueHandle<CommonUtil::CMpUtilsUninitialize>(void)

- ea: `0x14001d278`
- end: `0x14001d28f`
- name: `??1?$CUniqueHandle@UCMpUtilsUninitialize@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140026258`

## callees

- `0x140003088`
- `0x14001d278`

## pseudocode

```c
void __fastcall CommonUtil::CUniqueHandle<CommonUtil::CMpUtilsUninitialize>::~CUniqueHandle<CommonUtil::CMpUtilsUninitialize>(
        struct CommonUtil::MpUtilsType **a1)
{
  struct CommonUtil::MpUtilsType *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CommonUtil::CMpUtilsUninitialize::Release(v1);
}

```

## disassembly

```asm
0x14001d278  sub     rsp, 28h
0x14001d27c  mov     rcx, [rcx]; struct CommonUtil::MpUtilsType *
0x14001d27f  test    rcx, rcx
0x14001d282  jz      short loc_14001D28A
0x14001d284  call    ?Release@CMpUtilsUninitialize@CommonUtil@@SAXPEAUMpUtilsType@2@@Z; CommonUtil::CMpUtilsUninitialize::Release(CommonUtil::MpUtilsType *)
0x14001d289  nop
0x14001d28a  add     rsp, 28h
0x14001d28e  retn
```
