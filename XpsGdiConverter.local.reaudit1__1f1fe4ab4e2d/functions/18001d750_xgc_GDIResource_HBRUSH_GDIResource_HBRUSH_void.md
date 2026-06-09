# xgc::GDIResource<HBRUSH__ *>::~GDIResource<HBRUSH__ *>(void)

- ea: `0x18001d750`
- end: `0x18001d767`
- name: `??1?$GDIResource@PEAUHBRUSH__@@@xgc@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e274`

## callees

- `0x18001d750`

## import_xrefs

- `GDI32!DeleteObject` at `0x18001d75c`
- `GDI32!DeleteObject` at `0x18001d75c`

## pseudocode

```c
BOOL __fastcall xgc::GDIResource<HBRUSH__ *>::~GDIResource<HBRUSH__ *>(void **a1)
{
  void *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return DeleteObject(v1);
  return result;
}

```

## disassembly

```asm
0x18001d750  sub     rsp, 28h
0x18001d754  mov     rcx, [rcx]; ho
0x18001d757  test    rcx, rcx
0x18001d75a  jz      short loc_18001D762
0x18001d75c  call    cs:__imp_DeleteObject
0x18001d762  add     rsp, 28h
0x18001d766  retn
```
