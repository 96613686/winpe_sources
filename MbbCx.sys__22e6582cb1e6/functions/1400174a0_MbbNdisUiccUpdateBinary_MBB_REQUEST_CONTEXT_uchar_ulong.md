# MbbNdisUiccUpdateBinary(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x1400174a0`
- end: `0x1400174af`
- name: `?MbbNdisUiccUpdateBinary@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `15`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140020a58`

## pseudocode

```c
__int64 __fastcall MbbNdisUiccUpdateBinary(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  return MbbUtilUiccAccessBinary(a1, a2, a3);
}

```

## disassembly

```asm
0x1400174a0  sub     rsp, 28h
0x1400174a4  call    ?MbbUtilUiccAccessBinary@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z; MbbUtilUiccAccessBinary(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)
0x1400174a9  add     rsp, 28h
0x1400174ad  retn
```
