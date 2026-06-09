# CProviderRegistrationCache::`scalar deleting destructor'(uint)

- ea: `0x180013d40`
- end: `0x180013d70`
- name: `??_GCProviderRegistrationCache@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CProviderRegistrationCache *__fastcall(CProviderRegistrationCache *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180013cb4`
- `0x180013d40`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013d5c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013d5c`

## pseudocode

```c
CProviderRegistrationCache *__fastcall CProviderRegistrationCache::`scalar deleting destructor'(
        CProviderRegistrationCache *this,
        char a2)
{
  CProviderRegistrationCache::~CProviderRegistrationCache(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180013d40  mov     [rsp+arg_0], rbx
0x180013d45  push    rdi
0x180013d46  sub     rsp, 20h
0x180013d4a  mov     ebx, edx
0x180013d4c  mov     rdi, rcx
0x180013d4f  call    ??1CProviderRegistrationCache@@UEAA@XZ; CProviderRegistrationCache::~CProviderRegistrationCache(void)
0x180013d54  test    bl, 1
0x180013d57  jz      short loc_180013D62
0x180013d59  mov     rcx, rdi
0x180013d5c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013d62  mov     rbx, [rsp+28h+arg_0]
0x180013d67  mov     rax, rdi
0x180013d6a  add     rsp, 20h
0x180013d6e  pop     rdi
0x180013d6f  retn
```
