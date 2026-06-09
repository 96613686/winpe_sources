# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x14001bdc0`
- end: `0x14001bdd9`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001b848`
- `0x14001be24`
- `0x14001bf90`

## callees

- `0x14001bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001bdce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001bdce`

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
0x14001bdc0  sub     rsp, 28h
0x14001bdc4  cmp     byte ptr [rcx+28h], 0
0x14001bdc8  jz      short loc_14001BDD4
0x14001bdca  mov     byte ptr [rcx+28h], 0
0x14001bdce  call    cs:__imp_DeleteCriticalSection
0x14001bdd4  add     rsp, 28h
0x14001bdd8  retn
```
