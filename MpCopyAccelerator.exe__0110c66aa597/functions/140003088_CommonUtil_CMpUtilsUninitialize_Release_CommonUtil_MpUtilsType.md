# CommonUtil::CMpUtilsUninitialize::Release(CommonUtil::MpUtilsType *)

- ea: `0x140003088`
- end: `0x14000309b`
- name: `?Release@CMpUtilsUninitialize@CommonUtil@@SAXPEAUMpUtilsType@2@@Z`
- size: `19`
- prototype: `void __fastcall(struct CommonUtil::MpUtilsType *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001d278`
- `0x14001dba4`

## callees

- `0x1400026c8`
- `0x140003088`

## pseudocode

```c
void __fastcall CommonUtil::CMpUtilsUninitialize::Release(struct CommonUtil::MpUtilsType *a1)
{
  if ( a1 )
    MpUtilsUninitialize();
}

```

## disassembly

```asm
0x140003088  sub     rsp, 28h
0x14000308c  test    rcx, rcx
0x14000308f  jz      short loc_140003096
0x140003091  call    MpUtilsUninitialize
0x140003096  add     rsp, 28h
0x14000309a  retn
```
