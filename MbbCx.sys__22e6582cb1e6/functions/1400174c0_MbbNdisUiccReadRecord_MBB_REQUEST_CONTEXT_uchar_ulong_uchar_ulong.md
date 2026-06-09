# MbbNdisUiccReadRecord(_MBB_REQUEST_CONTEXT *,uchar *,ulong *,uchar *,ulong *)

- ea: `0x1400174c0`
- end: `0x1400174cf`
- name: `?MbbNdisUiccReadRecord@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK12@Z`
- size: `15`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140020b38`

## pseudocode

```c
__int64 __fastcall MbbNdisUiccReadRecord(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  return MbbUtilUiccAccessRecord(a1, a2, a3);
}

```

## disassembly

```asm
0x1400174c0  sub     rsp, 28h
0x1400174c4  call    ?MbbUtilUiccAccessRecord@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z; MbbUtilUiccAccessRecord(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)
0x1400174c9  add     rsp, 28h
0x1400174cd  retn
```
