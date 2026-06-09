# CPropertyCache::getproperty(ulong,tagVARIANT *)

- ea: `0x180010e80`
- end: `0x180010e85`
- name: `?getproperty@CPropertyCache@@UEAAJKPEAUtagVARIANT@@@Z`
- size: `5`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180010104`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CPropertyCache::getproperty(unsigned __int16 **this, unsigned int a2, struct tagVARIANT *a3)
{
  return CPropertyCache::DispatchGetProperty(this, a2, a3);
}

```

## disassembly

```asm
0x180010e80  jmp     ?DispatchGetProperty@CPropertyCache@@IEAAJKPEAUtagVARIANT@@@Z; CPropertyCache::DispatchGetProperty(ulong,tagVARIANT *)
```
