# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x18001b280`
- end: `0x18001b302`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001afd4`
- `0x1800514a0`

## callees

- `0x18001b280`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b29a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b2b1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b2c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b2df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b2f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b29a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b2b1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b2c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b2df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b2f6`

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
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v6 )
    SRCache_Free(v6);
}

```

## disassembly

```asm
0x18001b280  push    rbx
0x18001b282  sub     rsp, 20h
0x18001b286  mov     rbx, rcx
0x18001b289  mov     rcx, [rcx+58h]
0x18001b28d  mov     qword ptr [rbx+58h], 0
0x18001b295  test    rcx, rcx
0x18001b298  jz      short loc_18001B2A0
0x18001b29a  call    cs:__imp_SRCache_Free
0x18001b2a0  mov     rcx, [rbx+48h]
0x18001b2a4  mov     qword ptr [rbx+48h], 0
0x18001b2ac  test    rcx, rcx
0x18001b2af  jz      short loc_18001B2B7
0x18001b2b1  call    cs:__imp_SRCache_Free
0x18001b2b7  mov     rcx, [rbx+40h]
0x18001b2bb  mov     qword ptr [rbx+40h], 0
0x18001b2c3  test    rcx, rcx
0x18001b2c6  jz      short loc_18001B2CE
0x18001b2c8  call    cs:__imp_SRCache_Free
0x18001b2ce  mov     rcx, [rbx+38h]
0x18001b2d2  mov     qword ptr [rbx+38h], 0
0x18001b2da  test    rcx, rcx
0x18001b2dd  jz      short loc_18001B2E5
0x18001b2df  call    cs:__imp_SRCache_Free
0x18001b2e5  mov     rcx, [rbx+8]
0x18001b2e9  mov     qword ptr [rbx+8], 0
0x18001b2f1  test    rcx, rcx
0x18001b2f4  jz      short loc_18001B2FC
0x18001b2f6  call    cs:__imp_SRCache_Free
0x18001b2fc  add     rsp, 20h
0x18001b300  pop     rbx
0x18001b301  retn
```
