# StructuredQuery1::TokenInformationComplete::~TokenInformationComplete(void)

- ea: `0x1800487b8`
- end: `0x1800487ec`
- name: `??1TokenInformationComplete@StructuredQuery1@@AEAA@XZ`
- size: `52`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048770`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800487cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800487cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800487d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800487d9`

## pseudocode

```c
void __fastcall StructuredQuery1::TokenInformationComplete::~TokenInformationComplete(LPVOID *this)
{
  *this = &StructuredQuery1::TokenInformationComplete::`vftable';
  CoTaskMemFree(this[2]);
  PropVariantClear(this + 3);
  _InterlockedDecrement(&dword_1800B134C);
}

```

## disassembly

```asm
0x1800487b8  push    rbx
0x1800487ba  sub     rsp, 20h
0x1800487be  lea     rax, ??_7TokenInformationComplete@StructuredQuery1@@6B@; const StructuredQuery1::TokenInformationComplete::`vftable'
0x1800487c5  mov     rbx, rcx
0x1800487c8  mov     [rcx], rax
0x1800487cb  mov     rcx, [rcx+10h]; pv
0x1800487cf  call    cs:__imp_CoTaskMemFree
0x1800487d5  lea     rcx, [rbx+18h]; pvar
0x1800487d9  call    cs:__imp_PropVariantClear
0x1800487df  lock dec cs:dword_1800B134C
0x1800487e6  add     rsp, 20h
0x1800487ea  pop     rbx
0x1800487eb  retn
```
