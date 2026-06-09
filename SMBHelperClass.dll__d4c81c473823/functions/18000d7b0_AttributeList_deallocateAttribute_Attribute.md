# AttributeList::deallocateAttribute(Attribute &)

- ea: `0x18000d7b0`
- end: `0x18000d7d3`
- name: `?deallocateAttribute@AttributeList@@AEAAXAEAUAttribute@@@Z`
- size: `35`
- prototype: `void __fastcall(AttributeList *__hidden this, struct Attribute *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011148`

## callees

- `0x18000d7b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d7c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d7c8`

## pseudocode

```c
void __fastcall AttributeList::deallocateAttribute(AttributeList *this, struct Attribute *a2)
{
  void *v2; // rcx

  if ( *(_DWORD *)a2 <= 1u )
  {
    v2 = (void *)*((_QWORD *)a2 + 1);
    if ( v2 )
      CoTaskMemFree(v2);
  }
}

```

## disassembly

```asm
0x18000d7b0  sub     rsp, 28h
0x18000d7b4  mov     ecx, [rdx]
0x18000d7b6  test    ecx, ecx
0x18000d7b8  jz      short loc_18000D7BF
0x18000d7ba  cmp     ecx, 1
0x18000d7bd  jnz     short loc_18000D7CE
0x18000d7bf  mov     rcx, [rdx+8]; pv
0x18000d7c3  test    rcx, rcx
0x18000d7c6  jz      short loc_18000D7CE
0x18000d7c8  call    cs:__imp_CoTaskMemFree
0x18000d7ce  add     rsp, 28h
0x18000d7d2  retn
```
