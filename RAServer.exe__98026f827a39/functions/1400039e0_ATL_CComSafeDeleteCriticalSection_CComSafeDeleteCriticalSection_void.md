# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x1400039e0`
- end: `0x1400039f9`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003398`
- `0x1400033dc`
- `0x1400034c0`
- `0x14000359c`
- `0x140003a44`
- `0x140003a7c`

## callees

- `0x1400039e0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400039ee`
- `KERNEL32!DeleteCriticalSection` at `0x1400039ee`

## pseudocode

```c
void __fastcall ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(
        ATL::CComSafeDeleteCriticalSection *this)
{
  if ( *((_BYTE *)this + 40) )
  {
    *((_BYTE *)this + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)this);
  }
}

```

## disassembly

```asm
0x1400039e0  sub     rsp, 28h
0x1400039e4  cmp     byte ptr [rcx+28h], 0
0x1400039e8  jz      short loc_1400039F4
0x1400039ea  mov     byte ptr [rcx+28h], 0
0x1400039ee  call    cs:__imp_DeleteCriticalSection
0x1400039f4  add     rsp, 28h
0x1400039f8  retn
```
