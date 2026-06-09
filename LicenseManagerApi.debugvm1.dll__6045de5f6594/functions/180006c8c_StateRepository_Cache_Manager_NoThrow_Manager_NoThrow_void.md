# StateRepository::Cache::Manager_NoThrow::~Manager_NoThrow(void)

- ea: `0x180006c8c`
- end: `0x180006cad`
- name: `??1Manager_NoThrow@Cache@StateRepository@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(StateRepository::Cache::Manager_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001226f`

## callees

- `0x180006c8c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180006ca2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180006ca2`

## pseudocode

```c
void __fastcall StateRepository::Cache::Manager_NoThrow::~Manager_NoThrow(
        StateRepository::Cache::Manager_NoThrow *this)
{
  __int64 v1; // rax

  v1 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v1 )
    SRCacheManager_Close(v1);
}

```

## disassembly

```asm
0x180006c8c  sub     rsp, 28h
0x180006c90  mov     rax, [rcx]
0x180006c93  mov     qword ptr [rcx], 0
0x180006c9a  test    rax, rax
0x180006c9d  jz      short loc_180006CA8
0x180006c9f  mov     rcx, rax
0x180006ca2  call    cs:__imp_SRCacheManager_Close
0x180006ca8  add     rsp, 28h
0x180006cac  retn
```
