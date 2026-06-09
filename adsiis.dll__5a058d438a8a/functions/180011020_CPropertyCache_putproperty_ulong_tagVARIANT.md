# CPropertyCache::putproperty(ulong,tagVARIANT)

- ea: `0x180011020`
- end: `0x18001102e`
- name: `?putproperty@CPropertyCache@@UEAAJKUtagVARIANT@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800103bc`

## pseudocode

```c
__int64 __fastcall CPropertyCache::putproperty(CPropertyCache *this, unsigned int a2, struct tagVARIANT *a3)
{
  return CPropertyCache::DispatchPutProperty(this, a2, a3);
}

```

## disassembly

```asm
0x180011020  sub     rsp, 28h
0x180011024  call    ?DispatchPutProperty@CPropertyCache@@IEAAJKAEAUtagVARIANT@@@Z; CPropertyCache::DispatchPutProperty(ulong,tagVARIANT &)
0x180011029  add     rsp, 28h
0x18001102d  retn
```
