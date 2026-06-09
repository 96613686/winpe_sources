# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x18004d5ac`
- end: `0x18004d62e`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004d174`

## callees

- `0x18004d5ac`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d5c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d5dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d5f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d60b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d622`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d5c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d5dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d5f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d60b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d622`

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
0x18004d5ac  push    rbx
0x18004d5ae  sub     rsp, 20h
0x18004d5b2  mov     rbx, rcx
0x18004d5b5  mov     rcx, [rcx+40h]
0x18004d5b9  mov     qword ptr [rbx+40h], 0
0x18004d5c1  test    rcx, rcx
0x18004d5c4  jz      short loc_18004D5CC
0x18004d5c6  call    cs:__imp_SRCache_Free
0x18004d5cc  mov     rcx, [rbx+38h]
0x18004d5d0  mov     qword ptr [rbx+38h], 0
0x18004d5d8  test    rcx, rcx
0x18004d5db  jz      short loc_18004D5E3
0x18004d5dd  call    cs:__imp_SRCache_Free
0x18004d5e3  mov     rcx, [rbx+30h]
0x18004d5e7  mov     qword ptr [rbx+30h], 0
0x18004d5ef  test    rcx, rcx
0x18004d5f2  jz      short loc_18004D5FA
0x18004d5f4  call    cs:__imp_SRCache_Free
0x18004d5fa  mov     rcx, [rbx+28h]
0x18004d5fe  mov     qword ptr [rbx+28h], 0
0x18004d606  test    rcx, rcx
0x18004d609  jz      short loc_18004D611
0x18004d60b  call    cs:__imp_SRCache_Free
0x18004d611  mov     rcx, [rbx+18h]
0x18004d615  mov     qword ptr [rbx+18h], 0
0x18004d61d  test    rcx, rcx
0x18004d620  jz      short loc_18004D628
0x18004d622  call    cs:__imp_SRCache_Free
0x18004d628  add     rsp, 20h
0x18004d62c  pop     rbx
0x18004d62d  retn
```
