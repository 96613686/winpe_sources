# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180023530`
- end: `0x18002354a`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180023594`

## callees

- `0x180023530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002353e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002353e`

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
0x180023530  sub     rsp, 28h
0x180023534  cmp     byte ptr [rcx+28h], 0
0x180023538  jz      short loc_180023545
0x18002353a  mov     byte ptr [rcx+28h], 0
0x18002353e  call    cs:__imp_DeleteCriticalSection
0x180023544  nop
0x180023545  add     rsp, 28h
0x180023549  retn
```
