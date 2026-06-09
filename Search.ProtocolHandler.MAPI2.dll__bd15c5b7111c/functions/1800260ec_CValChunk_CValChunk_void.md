# CValChunk::~CValChunk(void)

- ea: `0x1800260ec`
- end: `0x18002611f`
- name: `??1CValChunk@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(CValChunk *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002620c`

## callees

- `0x180011884`
- `0x1800260ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800260fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800260fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026108`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026108`

## pseudocode

```c
void __fastcall CValChunk::~CValChunk(CValChunk *this)
{
  PROPVARIANT *v2; // rcx

  v2 = (PROPVARIANT *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    PropVariantClear(v2);
    CoTaskMemFree(*((LPVOID *)this + 9));
  }
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)this - 24LL));
}

```

## disassembly

```asm
0x1800260ec  push    rbx
0x1800260ee  sub     rsp, 20h
0x1800260f2  mov     rbx, rcx
0x1800260f5  mov     rcx, [rcx+48h]; pvar
0x1800260f9  test    rcx, rcx
0x1800260fc  jz      short loc_18002610E
0x1800260fe  call    cs:__imp_PropVariantClear
0x180026104  mov     rcx, [rbx+48h]; pv
0x180026108  call    cs:__imp_CoTaskMemFree
0x18002610e  mov     rcx, [rbx]
0x180026111  sub     rcx, 18h; this
0x180026115  add     rsp, 20h
0x180026119  pop     rbx
0x18002611a  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
