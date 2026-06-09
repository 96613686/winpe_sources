# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x1800194e8`
- end: `0x18001956a`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180018748`
- `0x180062a00`
- `0x180063308`
- `0x1800a6818`

## callees

- `0x1800194e8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019502`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019519`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019530`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019547`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001955e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019502`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019519`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019530`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019547`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001955e`

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
0x1800194e8  push    rbx
0x1800194ea  sub     rsp, 20h
0x1800194ee  mov     rbx, rcx
0x1800194f1  mov     rcx, [rcx+58h]
0x1800194f5  mov     qword ptr [rbx+58h], 0
0x1800194fd  test    rcx, rcx
0x180019500  jz      short loc_180019508
0x180019502  call    cs:__imp_SRCache_Free
0x180019508  mov     rcx, [rbx+48h]
0x18001950c  mov     qword ptr [rbx+48h], 0
0x180019514  test    rcx, rcx
0x180019517  jz      short loc_18001951F
0x180019519  call    cs:__imp_SRCache_Free
0x18001951f  mov     rcx, [rbx+40h]
0x180019523  mov     qword ptr [rbx+40h], 0
0x18001952b  test    rcx, rcx
0x18001952e  jz      short loc_180019536
0x180019530  call    cs:__imp_SRCache_Free
0x180019536  mov     rcx, [rbx+38h]
0x18001953a  mov     qword ptr [rbx+38h], 0
0x180019542  test    rcx, rcx
0x180019545  jz      short loc_18001954D
0x180019547  call    cs:__imp_SRCache_Free
0x18001954d  mov     rcx, [rbx+8]
0x180019551  mov     qword ptr [rbx+8], 0
0x180019559  test    rcx, rcx
0x18001955c  jz      short loc_180019564
0x18001955e  call    cs:__imp_SRCache_Free
0x180019564  add     rsp, 20h
0x180019568  pop     rbx
0x180019569  retn
```
