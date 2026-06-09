# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x18004d634`
- end: `0x18004d6e4`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004d174`

## callees

- `0x18004d634`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d64e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d665`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d67c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d693`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d6aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d6c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d6d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d64e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d665`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d67c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d693`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d6aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d6c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004d6d8`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(
        StateRepository::Cache::Entity::Activation_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

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
  v6 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v6 )
    SRCache_Free();
  v7 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v7 )
    SRCache_Free();
  v8 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v8 )
    SRCache_Free();
}

```

## disassembly

```asm
0x18004d634  push    rbx
0x18004d636  sub     rsp, 20h
0x18004d63a  mov     rbx, rcx
0x18004d63d  mov     rcx, [rcx+40h]
0x18004d641  mov     qword ptr [rbx+40h], 0
0x18004d649  test    rcx, rcx
0x18004d64c  jz      short loc_18004D654
0x18004d64e  call    cs:__imp_SRCache_Free
0x18004d654  mov     rcx, [rbx+38h]
0x18004d658  mov     qword ptr [rbx+38h], 0
0x18004d660  test    rcx, rcx
0x18004d663  jz      short loc_18004D66B
0x18004d665  call    cs:__imp_SRCache_Free
0x18004d66b  mov     rcx, [rbx+30h]
0x18004d66f  mov     qword ptr [rbx+30h], 0
0x18004d677  test    rcx, rcx
0x18004d67a  jz      short loc_18004D682
0x18004d67c  call    cs:__imp_SRCache_Free
0x18004d682  mov     rcx, [rbx+28h]
0x18004d686  mov     qword ptr [rbx+28h], 0
0x18004d68e  test    rcx, rcx
0x18004d691  jz      short loc_18004D699
0x18004d693  call    cs:__imp_SRCache_Free
0x18004d699  mov     rcx, [rbx+20h]
0x18004d69d  mov     qword ptr [rbx+20h], 0
0x18004d6a5  test    rcx, rcx
0x18004d6a8  jz      short loc_18004D6B0
0x18004d6aa  call    cs:__imp_SRCache_Free
0x18004d6b0  mov     rcx, [rbx+18h]
0x18004d6b4  mov     qword ptr [rbx+18h], 0
0x18004d6bc  test    rcx, rcx
0x18004d6bf  jz      short loc_18004D6C7
0x18004d6c1  call    cs:__imp_SRCache_Free
0x18004d6c7  mov     rcx, [rbx+8]
0x18004d6cb  mov     qword ptr [rbx+8], 0
0x18004d6d3  test    rcx, rcx
0x18004d6d6  jz      short loc_18004D6DE
0x18004d6d8  call    cs:__imp_SRCache_Free
0x18004d6de  add     rsp, 20h
0x18004d6e2  pop     rbx
0x18004d6e3  retn
```
