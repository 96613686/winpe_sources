# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000ec90`
- end: `0x18000ecb0`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018174`

## callees

- `0x18000ec90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ec9e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ec9e`

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
0x18000ec90  sub     rsp, 28h
0x18000ec94  cmp     byte ptr [rcx+28h], 0
0x18000ec98  jz      short loc_18000ECAA
0x18000ec9a  mov     byte ptr [rcx+28h], 0
0x18000ec9e  call    cs:__imp_DeleteCriticalSection
0x18000eca5  nop     dword ptr [rax+rax+00h]
0x18000ecaa  add     rsp, 28h
0x18000ecae  retn
```
