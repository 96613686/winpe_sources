# PCPStorageProvider::`vector deleting destructor'(uint)

- ea: `0x18001fe60`
- end: `0x18001fecb`
- name: `??_EPCPStorageProvider@@UEAAPEAXI@Z`
- size: `107`
- prototype: `void *__fastcall(PCPStorageProvider *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001d590`
- `0x18006ba64`

## callees

- `0x18001fe60`
- `0x18001fed4`
- `0x1800768a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fe93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fe93`

## pseudocode

```c
PCPStorageProvider *__fastcall PCPStorageProvider::`vector deleting destructor'(PCPStorageProvider *this, char a2)
{
  *(_QWORD *)this = &PCPStorageProvider::`vftable';
  PCPStorageProvider::Teardown(this);
  *(_QWORD *)this = &TpmObject::`vftable';
  if ( (*((_DWORD *)this + 3) & 1) == 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &ObjectWithProperties::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0xC8);
  return this;
}

```

## disassembly

```asm
0x18001fe60  mov     [rsp+arg_0], rbx
0x18001fe65  push    rdi
0x18001fe66  sub     rsp, 20h
0x18001fe6a  lea     rax, ??_7PCPStorageProvider@@6B@; const PCPStorageProvider::`vftable'
0x18001fe71  mov     edi, edx
0x18001fe73  mov     [rcx], rax
0x18001fe76  mov     rbx, rcx
0x18001fe79  call    ?Teardown@PCPStorageProvider@@QEAAJXZ; PCPStorageProvider::Teardown(void)
0x18001fe7e  lea     rax, ??_7TpmObject@@6B@; const TpmObject::`vftable'
0x18001fe85  mov     [rbx], rax
0x18001fe88  mov     eax, [rbx+0Ch]
0x18001fe8b  test    al, 1
0x18001fe8d  jnz     short loc_18001FE9F
0x18001fe8f  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001fe93  call    cs:__imp_DeleteCriticalSection
0x18001fe9a  nop     dword ptr [rax+rax+00h]
0x18001fe9f  lea     rax, ??_7ObjectWithProperties@@6B@; const ObjectWithProperties::`vftable'
0x18001fea6  mov     [rbx], rax
0x18001fea9  test    dil, 1
0x18001fead  jz      short loc_18001FEBC
0x18001feaf  mov     edx, 0C8h; struct std::nothrow_t *
0x18001feb4  mov     rcx, rbx; void *
0x18001feb7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001febc  mov     rax, rbx
0x18001febf  mov     rbx, [rsp+28h+arg_0]
0x18001fec4  add     rsp, 20h
0x18001fec8  pop     rdi
0x18001fec9  retn
```
