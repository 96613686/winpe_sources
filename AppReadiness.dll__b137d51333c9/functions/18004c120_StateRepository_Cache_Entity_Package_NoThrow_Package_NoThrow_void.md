# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x18004c120`
- end: `0x18004c1a2`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18005ac6c`
- `0x180078056`

## callees

- `0x18004c120`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c13a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c151`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c168`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c17f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c196`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c13a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c151`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c168`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c17f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c196`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(
        StateRepository::Cache::Entity::Package_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v6 )
    SRCache_Free();
}

```

## disassembly

```asm
0x18004c120  push    rbx
0x18004c122  sub     rsp, 20h
0x18004c126  mov     rbx, rcx
0x18004c129  mov     rcx, [rcx+58h]
0x18004c12d  mov     qword ptr [rbx+58h], 0
0x18004c135  test    rcx, rcx
0x18004c138  jz      short loc_18004C140
0x18004c13a  call    cs:__imp_SRCache_Free
0x18004c140  mov     rcx, [rbx+48h]
0x18004c144  mov     qword ptr [rbx+48h], 0
0x18004c14c  test    rcx, rcx
0x18004c14f  jz      short loc_18004C157
0x18004c151  call    cs:__imp_SRCache_Free
0x18004c157  mov     rcx, [rbx+40h]
0x18004c15b  mov     qword ptr [rbx+40h], 0
0x18004c163  test    rcx, rcx
0x18004c166  jz      short loc_18004C16E
0x18004c168  call    cs:__imp_SRCache_Free
0x18004c16e  mov     rcx, [rbx+38h]
0x18004c172  mov     qword ptr [rbx+38h], 0
0x18004c17a  test    rcx, rcx
0x18004c17d  jz      short loc_18004C185
0x18004c17f  call    cs:__imp_SRCache_Free
0x18004c185  mov     rcx, [rbx+8]
0x18004c189  mov     qword ptr [rbx+8], 0
0x18004c191  test    rcx, rcx
0x18004c194  jz      short loc_18004C19C
0x18004c196  call    cs:__imp_SRCache_Free
0x18004c19c  add     rsp, 20h
0x18004c1a0  pop     rbx
0x18004c1a1  retn
```
