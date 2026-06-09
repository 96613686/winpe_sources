# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18001ee6c`
- end: `0x18001ee85`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ec98`

## callees

- `0x18001ee6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ee7a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ee7a`

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
0x18001ee6c  sub     rsp, 28h
0x18001ee70  cmp     byte ptr [rcx+28h], 0
0x18001ee74  jz      short loc_18001EE80
0x18001ee76  mov     byte ptr [rcx+28h], 0
0x18001ee7a  call    cs:__imp_DeleteCriticalSection
0x18001ee80  add     rsp, 28h
0x18001ee84  retn
```
