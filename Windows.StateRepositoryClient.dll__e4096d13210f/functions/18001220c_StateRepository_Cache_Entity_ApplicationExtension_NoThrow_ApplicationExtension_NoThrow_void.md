# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x18001220c`
- end: `0x18001228e`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800123a8`

## callees

- `0x18001220c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012226`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001223d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012254`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001226b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012282`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012226`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001223d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012254`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001226b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012282`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v2 )
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v6 )
    SRCache_Free(v6);
}

```

## disassembly

```asm
0x18001220c  push    rbx
0x18001220e  sub     rsp, 20h
0x180012212  mov     rbx, rcx
0x180012215  mov     rcx, [rcx+40h]
0x180012219  mov     qword ptr [rbx+40h], 0
0x180012221  test    rcx, rcx
0x180012224  jz      short loc_18001222C
0x180012226  call    cs:__imp_SRCache_Free
0x18001222c  mov     rcx, [rbx+38h]
0x180012230  mov     qword ptr [rbx+38h], 0
0x180012238  test    rcx, rcx
0x18001223b  jz      short loc_180012243
0x18001223d  call    cs:__imp_SRCache_Free
0x180012243  mov     rcx, [rbx+30h]
0x180012247  mov     qword ptr [rbx+30h], 0
0x18001224f  test    rcx, rcx
0x180012252  jz      short loc_18001225A
0x180012254  call    cs:__imp_SRCache_Free
0x18001225a  mov     rcx, [rbx+28h]
0x18001225e  mov     qword ptr [rbx+28h], 0
0x180012266  test    rcx, rcx
0x180012269  jz      short loc_180012271
0x18001226b  call    cs:__imp_SRCache_Free
0x180012271  mov     rcx, [rbx+18h]
0x180012275  mov     qword ptr [rbx+18h], 0
0x18001227d  test    rcx, rcx
0x180012280  jz      short loc_180012288
0x180012282  call    cs:__imp_SRCache_Free
0x180012288  add     rsp, 20h
0x18001228c  pop     rbx
0x18001228d  retn
```
