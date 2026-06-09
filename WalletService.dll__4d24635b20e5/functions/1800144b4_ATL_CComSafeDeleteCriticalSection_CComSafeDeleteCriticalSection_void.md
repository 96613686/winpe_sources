# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x1800144b4`
- end: `0x1800144cd`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014558`
- `0x180017648`
- `0x180034194`

## callees

- `0x1800144b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800144c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800144c2`

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
0x1800144b4  sub     rsp, 28h
0x1800144b8  cmp     byte ptr [rcx+28h], 0
0x1800144bc  jz      short loc_1800144C8
0x1800144be  mov     byte ptr [rcx+28h], 0
0x1800144c2  call    cs:__imp_DeleteCriticalSection
0x1800144c8  add     rsp, 28h
0x1800144cc  retn
```
