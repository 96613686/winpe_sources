# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000e5d0`
- end: `0x18000e5e9`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800176ac`

## callees

- `0x18000e5d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e5de`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e5de`

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
0x18000e5d0  sub     rsp, 28h
0x18000e5d4  cmp     byte ptr [rcx+28h], 0
0x18000e5d8  jz      short loc_18000E5E4
0x18000e5da  mov     byte ptr [rcx+28h], 0
0x18000e5de  call    cs:__imp_DeleteCriticalSection
0x18000e5e4  add     rsp, 28h
0x18000e5e8  retn
```
