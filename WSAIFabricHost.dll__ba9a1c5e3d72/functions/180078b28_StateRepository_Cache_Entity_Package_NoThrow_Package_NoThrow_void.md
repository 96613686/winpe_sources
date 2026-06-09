# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x180078b28`
- end: `0x180078baa`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180078fd0`
- `0x180088143`

## callees

- `0x180078b28`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b42`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b59`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b87`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b42`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b59`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b87`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078b9e`

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
0x180078b28  push    rbx
0x180078b2a  sub     rsp, 20h
0x180078b2e  mov     rbx, rcx
0x180078b31  mov     rcx, [rcx+58h]
0x180078b35  mov     qword ptr [rbx+58h], 0
0x180078b3d  test    rcx, rcx
0x180078b40  jz      short loc_180078B48
0x180078b42  call    cs:__imp_SRCache_Free
0x180078b48  mov     rcx, [rbx+48h]
0x180078b4c  mov     qword ptr [rbx+48h], 0
0x180078b54  test    rcx, rcx
0x180078b57  jz      short loc_180078B5F
0x180078b59  call    cs:__imp_SRCache_Free
0x180078b5f  mov     rcx, [rbx+40h]
0x180078b63  mov     qword ptr [rbx+40h], 0
0x180078b6b  test    rcx, rcx
0x180078b6e  jz      short loc_180078B76
0x180078b70  call    cs:__imp_SRCache_Free
0x180078b76  mov     rcx, [rbx+38h]
0x180078b7a  mov     qword ptr [rbx+38h], 0
0x180078b82  test    rcx, rcx
0x180078b85  jz      short loc_180078B8D
0x180078b87  call    cs:__imp_SRCache_Free
0x180078b8d  mov     rcx, [rbx+8]
0x180078b91  mov     qword ptr [rbx+8], 0
0x180078b99  test    rcx, rcx
0x180078b9c  jz      short loc_180078BA4
0x180078b9e  call    cs:__imp_SRCache_Free
0x180078ba4  add     rsp, 20h
0x180078ba8  pop     rbx
0x180078ba9  retn
```
