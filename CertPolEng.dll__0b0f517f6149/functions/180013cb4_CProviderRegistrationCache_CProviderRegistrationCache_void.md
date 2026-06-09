# CProviderRegistrationCache::~CProviderRegistrationCache(void)

- ea: `0x180013cb4`
- end: `0x180013cee`
- name: `??1CProviderRegistrationCache@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CProviderRegistrationCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013d40`

## callees

- `0x18000c65c`
- `0x180013c90`
- `0x180017d18`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::~CProviderRegistrationCache(CProviderRegistrationCache *this)
{
  *(_QWORD *)this = &CProviderRegistrationCache::`vftable';
  CProviderRegistrationCache::ShutDown(this, 1);
  CIdentityPolicy::~CIdentityPolicy((CProviderRegistrationCache *)((char *)this + 280));
  CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::~CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>((__int64)this + 144);
}

```

## disassembly

```asm
0x180013cb4  push    rbx
0x180013cb6  sub     rsp, 20h
0x180013cba  lea     rax, ??_7CProviderRegistrationCache@@6B@; const CProviderRegistrationCache::`vftable'
0x180013cc1  mov     edx, 1; int
0x180013cc6  mov     [rcx], rax
0x180013cc9  mov     rbx, rcx
0x180013ccc  call    ?ShutDown@CProviderRegistrationCache@@QEAAKH@Z; CProviderRegistrationCache::ShutDown(int)
0x180013cd1  lea     rcx, [rbx+118h]; this
0x180013cd8  call    ??1CIdentityPolicy@@UEAA@XZ; CIdentityPolicy::~CIdentityPolicy(void)
0x180013cdd  lea     rcx, [rbx+90h]
0x180013ce4  add     rsp, 20h
0x180013ce8  pop     rbx
0x180013ce9  jmp     ??1?$CPtrArrayTemplate@VCProviderEntry@@U?$AutoPtrTraits@VCProviderEntry@@@@@@QEAA@XZ; CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::~CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>(void)
```
