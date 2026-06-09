# StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)

- ea: `0x180078ab4`
- end: `0x180078b1f`
- name: `??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PackageExtension_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180078fd0`
- `0x180088131`

## callees

- `0x180078ab4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078ace`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078ae5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078afc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078ace`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078ae5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078afc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b13`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(
        StateRepository::Cache::Entity::PackageExtension_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v5 )
    SRCache_Free();
}

```

## disassembly

```asm
0x180078ab4  push    rbx
0x180078ab6  sub     rsp, 20h
0x180078aba  mov     rbx, rcx
0x180078abd  mov     rcx, [rcx+38h]
0x180078ac1  mov     qword ptr [rbx+38h], 0
0x180078ac9  test    rcx, rcx
0x180078acc  jz      short loc_180078AD4
0x180078ace  call    cs:__imp_SRCache_Free
0x180078ad4  mov     rcx, [rbx+30h]
0x180078ad8  mov     qword ptr [rbx+30h], 0
0x180078ae0  test    rcx, rcx
0x180078ae3  jz      short loc_180078AEB
0x180078ae5  call    cs:__imp_SRCache_Free
0x180078aeb  mov     rcx, [rbx+28h]
0x180078aef  mov     qword ptr [rbx+28h], 0
0x180078af7  test    rcx, rcx
0x180078afa  jz      short loc_180078B02
0x180078afc  call    cs:__imp_SRCache_Free
0x180078b02  mov     rcx, [rbx+18h]
0x180078b06  mov     qword ptr [rbx+18h], 0
0x180078b0e  test    rcx, rcx
0x180078b11  jz      short loc_180078B19
0x180078b13  call    cs:__imp_SRCache_Free
0x180078b19  add     rsp, 20h
0x180078b1d  pop     rbx
0x180078b1e  retn
```
