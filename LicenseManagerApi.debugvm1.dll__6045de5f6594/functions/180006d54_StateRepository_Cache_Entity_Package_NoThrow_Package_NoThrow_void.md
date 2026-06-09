# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x180006d54`
- end: `0x180006dd6`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eaec`
- `0x180012281`

## callees

- `0x180006d54`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006d6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006d85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006d9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006db3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006dca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006d6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006d85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006d9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006db3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006dca`

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
0x180006d54  push    rbx
0x180006d56  sub     rsp, 20h
0x180006d5a  mov     rbx, rcx
0x180006d5d  mov     rcx, [rcx+58h]
0x180006d61  mov     qword ptr [rbx+58h], 0
0x180006d69  test    rcx, rcx
0x180006d6c  jz      short loc_180006D74
0x180006d6e  call    cs:__imp_SRCache_Free
0x180006d74  mov     rcx, [rbx+48h]
0x180006d78  mov     qword ptr [rbx+48h], 0
0x180006d80  test    rcx, rcx
0x180006d83  jz      short loc_180006D8B
0x180006d85  call    cs:__imp_SRCache_Free
0x180006d8b  mov     rcx, [rbx+40h]
0x180006d8f  mov     qword ptr [rbx+40h], 0
0x180006d97  test    rcx, rcx
0x180006d9a  jz      short loc_180006DA2
0x180006d9c  call    cs:__imp_SRCache_Free
0x180006da2  mov     rcx, [rbx+38h]
0x180006da6  mov     qword ptr [rbx+38h], 0
0x180006dae  test    rcx, rcx
0x180006db1  jz      short loc_180006DB9
0x180006db3  call    cs:__imp_SRCache_Free
0x180006db9  mov     rcx, [rbx+8]
0x180006dbd  mov     qword ptr [rbx+8], 0
0x180006dc5  test    rcx, rcx
0x180006dc8  jz      short loc_180006DD0
0x180006dca  call    cs:__imp_SRCache_Free
0x180006dd0  add     rsp, 20h
0x180006dd4  pop     rbx
0x180006dd5  retn
```
