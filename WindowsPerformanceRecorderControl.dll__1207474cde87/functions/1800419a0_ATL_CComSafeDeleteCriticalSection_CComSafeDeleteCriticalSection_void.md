# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x1800419a0`
- end: `0x1800419b9`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038984`
- `0x180041554`
- `0x180041858`
- `0x18004196c`
- `0x180041990`
- `0x180050fa0`
- `0x180057ab4`

## callees

- `0x1800419a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800419ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800419ae`

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
0x1800419a0  sub     rsp, 28h
0x1800419a4  cmp     byte ptr [rcx+28h], 0
0x1800419a8  jz      short loc_1800419B4
0x1800419aa  mov     byte ptr [rcx+28h], 0
0x1800419ae  call    cs:__imp_DeleteCriticalSection
0x1800419b4  add     rsp, 28h
0x1800419b8  retn
```
