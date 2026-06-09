# CNetDiagHelperEx::~CNetDiagHelperEx(void)

- ea: `0x1800036d0`
- end: `0x1800036fc`
- name: `??1CNetDiagHelperEx@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CNetDiagHelperEx *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010096`

## callees

- `0x1800036d0`
- `0x180005050`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800036f0`
- `KERNEL32!DeleteCriticalSection` at `0x1800036f0`

## pseudocode

```c
void __fastcall CNetDiagHelperEx::~CNetDiagHelperEx(CNetDiagHelperEx *this)
{
  _attributes_array_t::FreeAll((CNetDiagHelperEx *)((char *)this + 24));
  if ( *((_BYTE *)this + 112) )
  {
    *((_BYTE *)this + 112) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  }
}

```

## disassembly

```asm
0x1800036d0  push    rbx
0x1800036d2  sub     rsp, 20h
0x1800036d6  mov     rbx, rcx
0x1800036d9  add     rcx, 18h; this
0x1800036dd  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x1800036e2  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800036e6  cmp     byte ptr [rcx+28h], 0
0x1800036ea  jz      short loc_1800036F6
0x1800036ec  mov     byte ptr [rcx+28h], 0
0x1800036f0  call    cs:__imp_DeleteCriticalSection
0x1800036f6  add     rsp, 20h
0x1800036fa  pop     rbx
0x1800036fb  retn
```
