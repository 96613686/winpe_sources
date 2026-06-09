# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x180009614`
- end: `0x180009696`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b20c`
- `0x1800123a8`
- `0x180016d0c`

## callees

- `0x180009614`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000962e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009645`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000965c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009673`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000968a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000962e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009645`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000965c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009673`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000968a`

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
0x180009614  push    rbx
0x180009616  sub     rsp, 20h
0x18000961a  mov     rbx, rcx
0x18000961d  mov     rcx, [rcx+58h]
0x180009621  mov     qword ptr [rbx+58h], 0
0x180009629  test    rcx, rcx
0x18000962c  jz      short loc_180009634
0x18000962e  call    cs:__imp_SRCache_Free
0x180009634  mov     rcx, [rbx+48h]
0x180009638  mov     qword ptr [rbx+48h], 0
0x180009640  test    rcx, rcx
0x180009643  jz      short loc_18000964B
0x180009645  call    cs:__imp_SRCache_Free
0x18000964b  mov     rcx, [rbx+40h]
0x18000964f  mov     qword ptr [rbx+40h], 0
0x180009657  test    rcx, rcx
0x18000965a  jz      short loc_180009662
0x18000965c  call    cs:__imp_SRCache_Free
0x180009662  mov     rcx, [rbx+38h]
0x180009666  mov     qword ptr [rbx+38h], 0
0x18000966e  test    rcx, rcx
0x180009671  jz      short loc_180009679
0x180009673  call    cs:__imp_SRCache_Free
0x180009679  mov     rcx, [rbx+8]
0x18000967d  mov     qword ptr [rbx+8], 0
0x180009685  test    rcx, rcx
0x180009688  jz      short loc_180009690
0x18000968a  call    cs:__imp_SRCache_Free
0x180009690  add     rsp, 20h
0x180009694  pop     rbx
0x180009695  retn
```
