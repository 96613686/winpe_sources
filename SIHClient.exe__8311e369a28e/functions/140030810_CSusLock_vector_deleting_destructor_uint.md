# CSusLock::`vector deleting destructor'(uint)

- ea: `0x140030810`
- end: `0x140030853`
- name: `??_ECSusLock@@UEAAPEAXI@Z`
- size: `67`
- prototype: `CSusLock *__fastcall(CSusLock *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x140030810`
- `0x140045de4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003082d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003082d`

## pseudocode

```c
CSusLock *__fastcall CSusLock::`vector deleting destructor'(CSusLock *this, char a2)
{
  *(_QWORD *)this = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x30);
  return this;
}

```

## disassembly

```asm
0x140030810  mov     [rsp+arg_0], rbx
0x140030815  push    rdi
0x140030816  sub     rsp, 20h
0x14003081a  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x140030821  mov     rdi, rcx
0x140030824  mov     [rcx], rax
0x140030827  mov     ebx, edx
0x140030829  add     rcx, 8; lpCriticalSection
0x14003082d  call    cs:__imp_DeleteCriticalSection
0x140030833  test    bl, 1
0x140030836  jz      short loc_140030845
0x140030838  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x14003083d  mov     rcx, rdi; void *
0x140030840  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140030845  mov     rbx, [rsp+28h+arg_0]
0x14003084a  mov     rax, rdi
0x14003084d  add     rsp, 20h
0x140030851  pop     rdi
0x140030852  retn
```
