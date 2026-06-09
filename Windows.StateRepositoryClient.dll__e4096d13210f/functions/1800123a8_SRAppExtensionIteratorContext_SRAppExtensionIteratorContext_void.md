# SRAppExtensionIteratorContext::~SRAppExtensionIteratorContext(void)

- ea: `0x1800123a8`
- end: `0x180012419`
- name: `??1SRAppExtensionIteratorContext@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(SRAppExtensionIteratorContext *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180012420`

## callees

- `0x180009614`
- `0x18001216c`
- `0x18001220c`
- `0x180012294`
- `0x180012364`
- `0x1800123a8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800123f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800123f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18001240d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18001240d`

## pseudocode

```c
void __fastcall SRAppExtensionIteratorContext::~SRAppExtensionIteratorContext(SRAppExtensionIteratorContext *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((SRAppExtensionIteratorContext *)((char *)this + 384));
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((SRAppExtensionIteratorContext *)((char *)this + 280));
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((SRAppExtensionIteratorContext *)((char *)this + 184));
  StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((SRAppExtensionIteratorContext *)((char *)this + 104));
  StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((SRAppExtensionIteratorContext *)((char *)this + 32));
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
0x1800123a8  push    rbx
0x1800123aa  sub     rsp, 20h
0x1800123ae  mov     rbx, rcx
0x1800123b1  add     rcx, 180h; this
0x1800123b8  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x1800123bd  lea     rcx, [rbx+118h]; this
0x1800123c4  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800123c9  lea     rcx, [rbx+0B8h]; this
0x1800123d0  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x1800123d5  lea     rcx, [rbx+68h]; this
0x1800123d9  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800123de  lea     rcx, [rbx+20h]; this
0x1800123e2  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x1800123e7  mov     rcx, [rbx+8]
0x1800123eb  mov     qword ptr [rbx+8], 0
0x1800123f3  test    rcx, rcx
0x1800123f6  jz      short loc_1800123FE
0x1800123f8  call    cs:__imp_SRCacheContext_Close
0x1800123fe  mov     rcx, [rbx]
0x180012401  mov     qword ptr [rbx], 0
0x180012408  test    rcx, rcx
0x18001240b  jz      short loc_180012413
0x18001240d  call    cs:__imp_SRCacheManager_Close
0x180012413  add     rsp, 20h
0x180012417  pop     rbx
0x180012418  retn
```
