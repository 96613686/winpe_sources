# CCriticalSectionObject::~CCriticalSectionObject(void)

- ea: `0x180015b40`
- end: `0x180015b64`
- name: `??1CCriticalSectionObject@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CCriticalSectionObject *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002fbc0`
- `0x180030c90`
- `0x180030e50`

## callees

- `0x180015b40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015b58`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015b58`

## pseudocode

```c
void __fastcall CCriticalSectionObject::~CCriticalSectionObject(CCriticalSectionObject *this)
{
  *(_QWORD *)this = &CCriticalSectionObject::`vftable';
  if ( !*((_DWORD *)this + 12) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180015b40  sub     rsp, 28h
0x180015b44  lea     rax, ??_7CCriticalSectionObject@@6B@; const CCriticalSectionObject::`vftable'
0x180015b4b  mov     [rcx], rax
0x180015b4e  cmp     dword ptr [rcx+30h], 0
0x180015b52  jnz     short loc_180015B5F
0x180015b54  add     rcx, 8; lpCriticalSection
0x180015b58  call    cs:__imp_DeleteCriticalSection
0x180015b5e  nop
0x180015b5f  add     rsp, 28h
0x180015b63  retn
```
