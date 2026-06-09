# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000ad58`
- end: `0x18000ad71`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ace4`
- `0x18000ad04`
- `0x18000adbc`
- `0x18000eab0`
- `0x18000eb6c`
- `0x180014094`
- `0x18001413c`
- `0x180014204`
- `0x1800187dc`

## callees

- `0x18000ad58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ad66`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ad66`

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
0x18000ad58  sub     rsp, 28h
0x18000ad5c  cmp     byte ptr [rcx+28h], 0
0x18000ad60  jz      short loc_18000AD6C
0x18000ad62  mov     byte ptr [rcx+28h], 0
0x18000ad66  call    cs:__imp_DeleteCriticalSection
0x18000ad6c  add     rsp, 28h
0x18000ad70  retn
```
