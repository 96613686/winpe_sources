# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x180008ec0`
- end: `0x180008f9e`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `222`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180007120`
- `0x180015f14`
- `0x180046750`
- `0x18004d174`
- `0x180058aec`
- `0x18009ba48`
- `0x18009cdef`

## callees

- `0x180008ec0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f57`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f72`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f8a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f57`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f72`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f8a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008f97`

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
    SRCache_Free();
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v6 )
    SRCache_Free();
  v7 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v7 )
    SRCache_Free();
  v8 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v8 )
    SRCache_Free();
  v9 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v9 )
    SRCache_Free();
}

```

## disassembly

```asm
0x180008ec0  push    rbx
0x180008ec2  sub     rsp, 20h
0x180008ec6  mov     rbx, rcx
0x180008ec9  mov     rcx, [rcx+58h]
0x180008ecd  mov     qword ptr [rbx+58h], 0
0x180008ed5  test    rcx, rcx
0x180008ed8  jnz     short loc_180008F57
0x180008eda  mov     rcx, [rbx+50h]
0x180008ede  mov     qword ptr [rbx+50h], 0
0x180008ee6  test    rcx, rcx
0x180008ee9  jnz     short loc_180008F62
0x180008eeb  mov     rcx, [rbx+48h]
0x180008eef  mov     qword ptr [rbx+48h], 0
0x180008ef7  test    rcx, rcx
0x180008efa  jnz     short loc_180008F6A
0x180008efc  mov     rcx, [rbx+40h]
0x180008f00  mov     qword ptr [rbx+40h], 0
0x180008f08  test    rcx, rcx
0x180008f0b  jnz     short loc_180008F72
0x180008f0d  mov     rcx, [rbx+38h]
0x180008f11  mov     qword ptr [rbx+38h], 0
0x180008f19  test    rcx, rcx
0x180008f1c  jnz     short loc_180008F7A
0x180008f1e  mov     rcx, [rbx+30h]
0x180008f22  mov     qword ptr [rbx+30h], 0
0x180008f2a  test    rcx, rcx
0x180008f2d  jnz     short loc_180008F82
0x180008f2f  mov     rcx, [rbx+20h]
0x180008f33  mov     qword ptr [rbx+20h], 0
0x180008f3b  test    rcx, rcx
0x180008f3e  jnz     short loc_180008F8A
0x180008f40  mov     rcx, [rbx+18h]
0x180008f44  mov     qword ptr [rbx+18h], 0
0x180008f4c  test    rcx, rcx
0x180008f4f  jnz     short loc_180008F92
0x180008f51  add     rsp, 20h
0x180008f55  pop     rbx
0x180008f56  retn
0x180008f57  call    cs:__imp_SRCache_Free
0x180008f5d  jmp     loc_180008EDA
0x180008f62  call    cs:__imp_SRCache_Free
0x180008f68  jmp     short loc_180008EEB
0x180008f6a  call    cs:__imp_SRCache_Free
0x180008f70  jmp     short loc_180008EFC
0x180008f72  call    cs:__imp_SRCache_Free
0x180008f78  jmp     short loc_180008F0D
0x180008f7a  call    cs:__imp_SRCache_Free
0x180008f80  jmp     short loc_180008F1E
0x180008f82  call    cs:__imp_SRCache_Free
0x180008f88  jmp     short loc_180008F2F
0x180008f8a  call    cs:__imp_SRCache_Free
0x180008f90  jmp     short loc_180008F40
0x180008f92  add     rsp, 20h
0x180008f96  pop     rbx
0x180008f97  jmp     cs:__imp_SRCache_Free
```
