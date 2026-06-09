# SRPkgExtensionIteratorContext::~SRPkgExtensionIteratorContext(void)

- ea: `0x180016d0c`
- end: `0x180016d71`
- name: `??1SRPkgExtensionIteratorContext@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(SRPkgExtensionIteratorContext *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180016d78`

## callees

- `0x180009614`
- `0x18001216c`
- `0x180012364`
- `0x180016c98`
- `0x180016d0c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180016d50`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180016d50`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180016d65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180016d65`

## pseudocode

```c
void __fastcall SRPkgExtensionIteratorContext::~SRPkgExtensionIteratorContext(SRPkgExtensionIteratorContext *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((SRPkgExtensionIteratorContext *)((char *)this + 272));
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((SRPkgExtensionIteratorContext *)((char *)this + 168));
  StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((SRPkgExtensionIteratorContext *)((char *)this + 104));
  StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((SRPkgExtensionIteratorContext *)((char *)this + 32));
  v2 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v2 )
    SRCacheContext_Close(v2);
  v3 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v3 )
    SRCacheManager_Close(v3);
}

```

## disassembly

```asm
0x180016d0c  push    rbx
0x180016d0e  sub     rsp, 20h
0x180016d12  mov     rbx, rcx
0x180016d15  add     rcx, 110h; this
0x180016d1c  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x180016d21  lea     rcx, [rbx+0A8h]; this
0x180016d28  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180016d2d  lea     rcx, [rbx+68h]; this
0x180016d31  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x180016d36  lea     rcx, [rbx+20h]; this
0x180016d3a  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x180016d3f  mov     rcx, [rbx+8]
0x180016d43  mov     qword ptr [rbx+8], 0
0x180016d4b  test    rcx, rcx
0x180016d4e  jz      short loc_180016D56
0x180016d50  call    cs:__imp_SRCacheContext_Close
0x180016d56  mov     rcx, [rbx]
0x180016d59  mov     qword ptr [rbx], 0
0x180016d60  test    rcx, rcx
0x180016d63  jz      short loc_180016D6B
0x180016d65  call    cs:__imp_SRCacheManager_Close
0x180016d6b  add     rsp, 20h
0x180016d6f  pop     rbx
0x180016d70  retn
```
