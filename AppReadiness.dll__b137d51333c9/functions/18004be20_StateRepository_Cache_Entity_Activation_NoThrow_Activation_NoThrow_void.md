# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x18004be20`
- end: `0x18004bed0`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004da98`
- `0x180077f00`

## callees

- `0x18004be20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004be3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004be51`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004be68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004be7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004be96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bead`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bec4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004be3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004be51`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004be68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004be7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004be96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bead`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bec4`

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
0x18004be20  push    rbx
0x18004be22  sub     rsp, 20h
0x18004be26  mov     rbx, rcx
0x18004be29  mov     rcx, [rcx+40h]
0x18004be2d  mov     qword ptr [rbx+40h], 0
0x18004be35  test    rcx, rcx
0x18004be38  jz      short loc_18004BE40
0x18004be3a  call    cs:__imp_SRCache_Free
0x18004be40  mov     rcx, [rbx+38h]
0x18004be44  mov     qword ptr [rbx+38h], 0
0x18004be4c  test    rcx, rcx
0x18004be4f  jz      short loc_18004BE57
0x18004be51  call    cs:__imp_SRCache_Free
0x18004be57  mov     rcx, [rbx+30h]
0x18004be5b  mov     qword ptr [rbx+30h], 0
0x18004be63  test    rcx, rcx
0x18004be66  jz      short loc_18004BE6E
0x18004be68  call    cs:__imp_SRCache_Free
0x18004be6e  mov     rcx, [rbx+28h]
0x18004be72  mov     qword ptr [rbx+28h], 0
0x18004be7a  test    rcx, rcx
0x18004be7d  jz      short loc_18004BE85
0x18004be7f  call    cs:__imp_SRCache_Free
0x18004be85  mov     rcx, [rbx+20h]
0x18004be89  mov     qword ptr [rbx+20h], 0
0x18004be91  test    rcx, rcx
0x18004be94  jz      short loc_18004BE9C
0x18004be96  call    cs:__imp_SRCache_Free
0x18004be9c  mov     rcx, [rbx+18h]
0x18004bea0  mov     qword ptr [rbx+18h], 0
0x18004bea8  test    rcx, rcx
0x18004beab  jz      short loc_18004BEB3
0x18004bead  call    cs:__imp_SRCache_Free
0x18004beb3  mov     rcx, [rbx+8]
0x18004beb7  mov     qword ptr [rbx+8], 0
0x18004bebf  test    rcx, rcx
0x18004bec2  jz      short loc_18004BECA
0x18004bec4  call    cs:__imp_SRCache_Free
0x18004beca  add     rsp, 20h
0x18004bece  pop     rbx
0x18004becf  retn
```
