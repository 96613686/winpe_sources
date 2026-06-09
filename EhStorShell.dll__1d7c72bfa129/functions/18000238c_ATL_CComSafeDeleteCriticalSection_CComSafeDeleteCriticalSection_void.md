# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000238c`
- end: `0x1800023a5`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002300`

## callees

- `0x18000238c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000239a`
- `KERNEL32!DeleteCriticalSection` at `0x18000239a`

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
0x18000238c  sub     rsp, 28h
0x180002390  cmp     byte ptr [rcx+28h], 0
0x180002394  jz      short loc_1800023A0
0x180002396  mov     byte ptr [rcx+28h], 0
0x18000239a  call    cs:__imp_DeleteCriticalSection
0x1800023a0  add     rsp, 28h
0x1800023a4  retn
```
