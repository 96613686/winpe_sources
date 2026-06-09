# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180042dfc`
- end: `0x180042e15`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001900`
- `0x1800019b0`
- `0x180051b58`

## callees

- `0x180042dfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042e0a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042e0a`

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
0x180042dfc  sub     rsp, 28h
0x180042e00  cmp     byte ptr [rcx+28h], 0
0x180042e04  jz      short loc_180042E10
0x180042e06  mov     byte ptr [rcx+28h], 0
0x180042e0a  call    cs:__imp_DeleteCriticalSection
0x180042e10  add     rsp, 28h
0x180042e14  retn
```
