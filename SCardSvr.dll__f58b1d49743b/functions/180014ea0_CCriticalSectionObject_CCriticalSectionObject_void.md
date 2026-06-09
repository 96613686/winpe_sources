# CCriticalSectionObject::~CCriticalSectionObject(void)

- ea: `0x180014ea0`
- end: `0x180014ec3`
- name: `??1CCriticalSectionObject@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(CCriticalSectionObject *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180017a84`
- `0x180017b6c`
- `0x18002438c`
- `0x180034090`
- `0x180034e21`
- `0x180035f8f`

## callees

- `0x180014ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014eb8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014eb8`

## pseudocode

```c
void __fastcall CCriticalSectionObject::~CCriticalSectionObject(CCriticalSectionObject *this)
{
  bool v1; // zf

  v1 = *((_DWORD *)this + 12) == 0;
  *(_QWORD *)this = &CCriticalSectionObject::`vftable';
  if ( v1 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180014ea0  sub     rsp, 28h
0x180014ea4  cmp     dword ptr [rcx+30h], 0
0x180014ea8  lea     rax, ??_7CCriticalSectionObject@@6B@; const CCriticalSectionObject::`vftable'
0x180014eaf  mov     [rcx], rax
0x180014eb2  jnz     short loc_180014EBE
0x180014eb4  add     rcx, 8; lpCriticalSection
0x180014eb8  call    cs:__imp_DeleteCriticalSection
0x180014ebe  add     rsp, 28h
0x180014ec2  retn
```
