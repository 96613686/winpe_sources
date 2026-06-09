# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x18000b0a4`
- end: `0x18000b16b`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a938`
- `0x180018228`
- `0x1800187f0`
- `0x180035698`

## callees

- `0x18000b0a4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b0be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b0d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b0ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b103`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b11a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b131`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b148`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b15f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b0be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b0d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b0ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b103`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b11a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b131`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b148`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b15f`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(
        StateRepository::Cache::Entity::Application_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  v2 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v2 )
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v6 )
    SRCache_Free(v6);
  v7 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v7 )
    SRCache_Free(v7);
  v8 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v8 )
    SRCache_Free(v8);
  v9 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v9 )
    SRCache_Free(v9);
}

```

## disassembly

```asm
0x18000b0a4  push    rbx
0x18000b0a6  sub     rsp, 20h
0x18000b0aa  mov     rbx, rcx
0x18000b0ad  mov     rcx, [rcx+58h]
0x18000b0b1  mov     qword ptr [rbx+58h], 0
0x18000b0b9  test    rcx, rcx
0x18000b0bc  jz      short loc_18000B0C4
0x18000b0be  call    cs:__imp_SRCache_Free
0x18000b0c4  mov     rcx, [rbx+50h]
0x18000b0c8  mov     qword ptr [rbx+50h], 0
0x18000b0d0  test    rcx, rcx
0x18000b0d3  jz      short loc_18000B0DB
0x18000b0d5  call    cs:__imp_SRCache_Free
0x18000b0db  mov     rcx, [rbx+48h]
0x18000b0df  mov     qword ptr [rbx+48h], 0
0x18000b0e7  test    rcx, rcx
0x18000b0ea  jz      short loc_18000B0F2
0x18000b0ec  call    cs:__imp_SRCache_Free
0x18000b0f2  mov     rcx, [rbx+40h]
0x18000b0f6  mov     qword ptr [rbx+40h], 0
0x18000b0fe  test    rcx, rcx
0x18000b101  jz      short loc_18000B109
0x18000b103  call    cs:__imp_SRCache_Free
0x18000b109  mov     rcx, [rbx+38h]
0x18000b10d  mov     qword ptr [rbx+38h], 0
0x18000b115  test    rcx, rcx
0x18000b118  jz      short loc_18000B120
0x18000b11a  call    cs:__imp_SRCache_Free
0x18000b120  mov     rcx, [rbx+30h]
0x18000b124  mov     qword ptr [rbx+30h], 0
0x18000b12c  test    rcx, rcx
0x18000b12f  jz      short loc_18000B137
0x18000b131  call    cs:__imp_SRCache_Free
0x18000b137  mov     rcx, [rbx+20h]
0x18000b13b  mov     qword ptr [rbx+20h], 0
0x18000b143  test    rcx, rcx
0x18000b146  jz      short loc_18000B14E
0x18000b148  call    cs:__imp_SRCache_Free
0x18000b14e  mov     rcx, [rbx+18h]
0x18000b152  mov     qword ptr [rbx+18h], 0
0x18000b15a  test    rcx, rcx
0x18000b15d  jz      short loc_18000B165
0x18000b15f  call    cs:__imp_SRCache_Free
0x18000b165  add     rsp, 20h
0x18000b169  pop     rbx
0x18000b16a  retn
```
