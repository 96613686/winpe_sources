# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x18004bed8`
- end: `0x18004bf5a`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004da98`
- `0x180077eee`

## callees

- `0x18004bed8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bef2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf09`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bef2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf09`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf4e`

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
    SRCache_Free();
  v3 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v6 )
    SRCache_Free();
}

```

## disassembly

```asm
0x18004bed8  push    rbx
0x18004beda  sub     rsp, 20h
0x18004bede  mov     rbx, rcx
0x18004bee1  mov     rcx, [rcx+40h]
0x18004bee5  mov     qword ptr [rbx+40h], 0
0x18004beed  test    rcx, rcx
0x18004bef0  jz      short loc_18004BEF8
0x18004bef2  call    cs:__imp_SRCache_Free
0x18004bef8  mov     rcx, [rbx+38h]
0x18004befc  mov     qword ptr [rbx+38h], 0
0x18004bf04  test    rcx, rcx
0x18004bf07  jz      short loc_18004BF0F
0x18004bf09  call    cs:__imp_SRCache_Free
0x18004bf0f  mov     rcx, [rbx+30h]
0x18004bf13  mov     qword ptr [rbx+30h], 0
0x18004bf1b  test    rcx, rcx
0x18004bf1e  jz      short loc_18004BF26
0x18004bf20  call    cs:__imp_SRCache_Free
0x18004bf26  mov     rcx, [rbx+28h]
0x18004bf2a  mov     qword ptr [rbx+28h], 0
0x18004bf32  test    rcx, rcx
0x18004bf35  jz      short loc_18004BF3D
0x18004bf37  call    cs:__imp_SRCache_Free
0x18004bf3d  mov     rcx, [rbx+18h]
0x18004bf41  mov     qword ptr [rbx+18h], 0
0x18004bf49  test    rcx, rcx
0x18004bf4c  jz      short loc_18004BF54
0x18004bf4e  call    cs:__imp_SRCache_Free
0x18004bf54  add     rsp, 20h
0x18004bf58  pop     rbx
0x18004bf59  retn
```
