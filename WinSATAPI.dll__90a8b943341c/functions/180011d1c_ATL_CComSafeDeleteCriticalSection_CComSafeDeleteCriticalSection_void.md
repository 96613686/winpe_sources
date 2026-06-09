# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180011d1c`
- end: `0x180011d3c`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010a90`
- `0x180011d9c`
- `0x18001448c`
- `0x1800144cc`
- `0x180014548`
- `0x1800145a0`
- `0x1800145d4`
- `0x18001460c`
- `0x18001d500`
- `0x180020940`

## callees

- `0x180011d1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011d2a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011d2a`

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
0x180011d1c  sub     rsp, 28h
0x180011d20  cmp     byte ptr [rcx+28h], 0
0x180011d24  jz      short loc_180011D36
0x180011d26  mov     byte ptr [rcx+28h], 0
0x180011d2a  call    cs:__imp_DeleteCriticalSection
0x180011d31  nop     dword ptr [rax+rax+00h]
0x180011d36  add     rsp, 28h
0x180011d3a  retn
```
