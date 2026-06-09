# StructuredQuery1::VirtualPropertyMap::~VirtualPropertyMap(void)

- ea: `0x180051798`
- end: `0x1800517cc`
- name: `??1VirtualPropertyMap@StructuredQuery1@@AEAA@XZ`
- size: `52`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180051750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800517af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800517b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800517af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800517b9`

## pseudocode

```c
void __fastcall StructuredQuery1::VirtualPropertyMap::~VirtualPropertyMap(LPVOID *this)
{
  *this = &StructuredQuery1::VirtualPropertyMap::`vftable';
  CoTaskMemFree(this[4]);
  CoTaskMemFree(this[8]);
  _InterlockedDecrement(&dword_1800B134C);
}

```

## disassembly

```asm
0x180051798  push    rbx
0x18005179a  sub     rsp, 20h
0x18005179e  lea     rax, ??_7VirtualPropertyMap@StructuredQuery1@@6B@; const StructuredQuery1::VirtualPropertyMap::`vftable'
0x1800517a5  mov     rbx, rcx
0x1800517a8  mov     [rcx], rax
0x1800517ab  mov     rcx, [rcx+20h]; pv
0x1800517af  call    cs:__imp_CoTaskMemFree
0x1800517b5  mov     rcx, [rbx+40h]; pv
0x1800517b9  call    cs:__imp_CoTaskMemFree
0x1800517bf  lock dec cs:dword_1800B134C
0x1800517c6  add     rsp, 20h
0x1800517ca  pop     rbx
0x1800517cb  retn
```
