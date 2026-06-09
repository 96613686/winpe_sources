# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180005ec0`
- end: `0x180005ed9`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005e08`
- `0x180005e18`
- `0x1800083d0`
- `0x1800088f8`

## callees

- `0x180005ec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005ece`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005ece`

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
0x180005ec0  sub     rsp, 28h
0x180005ec4  cmp     byte ptr [rcx+28h], 0
0x180005ec8  jz      short loc_180005ED4
0x180005eca  mov     byte ptr [rcx+28h], 0
0x180005ece  call    cs:__imp_DeleteCriticalSection
0x180005ed4  add     rsp, 28h
0x180005ed8  retn
```
