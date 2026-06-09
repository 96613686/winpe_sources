# StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)

- ea: `0x18012fb4c`
- end: `0x18012fbe5`
- name: `??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PkgExtension_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18012f5d0`
- `0x18016ba50`

## callees

- `0x18012fb4c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fb66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fb7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fb94`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fbab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fbc2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fbd9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fb66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fb7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fb94`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fbab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fbc2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18012fbd9`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(
        StateRepository::Cache::Entity::PkgExtension_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v2 )
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v6 )
    SRCache_Free(v6);
  v7 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v7 )
    SRCache_Free(v7);
}

```

## disassembly

```asm
0x18012fb4c  push    rbx
0x18012fb4e  sub     rsp, 20h
0x18012fb52  mov     rbx, rcx
0x18012fb55  mov     rcx, [rcx+38h]
0x18012fb59  mov     qword ptr [rbx+38h], 0
0x18012fb61  test    rcx, rcx
0x18012fb64  jz      short loc_18012FB6C
0x18012fb66  call    cs:__imp_SRCache_Free
0x18012fb6c  mov     rcx, [rbx+28h]
0x18012fb70  mov     qword ptr [rbx+28h], 0
0x18012fb78  test    rcx, rcx
0x18012fb7b  jz      short loc_18012FB83
0x18012fb7d  call    cs:__imp_SRCache_Free
0x18012fb83  mov     rcx, [rbx+20h]
0x18012fb87  mov     qword ptr [rbx+20h], 0
0x18012fb8f  test    rcx, rcx
0x18012fb92  jz      short loc_18012FB9A
0x18012fb94  call    cs:__imp_SRCache_Free
0x18012fb9a  mov     rcx, [rbx+18h]
0x18012fb9e  mov     qword ptr [rbx+18h], 0
0x18012fba6  test    rcx, rcx
0x18012fba9  jz      short loc_18012FBB1
0x18012fbab  call    cs:__imp_SRCache_Free
0x18012fbb1  mov     rcx, [rbx+10h]
0x18012fbb5  mov     qword ptr [rbx+10h], 0
0x18012fbbd  test    rcx, rcx
0x18012fbc0  jz      short loc_18012FBC8
0x18012fbc2  call    cs:__imp_SRCache_Free
0x18012fbc8  mov     rcx, [rbx+8]
0x18012fbcc  mov     qword ptr [rbx+8], 0
0x18012fbd4  test    rcx, rcx
0x18012fbd7  jz      short loc_18012FBDF
0x18012fbd9  call    cs:__imp_SRCache_Free
0x18012fbdf  add     rsp, 20h
0x18012fbe3  pop     rbx
0x18012fbe4  retn
```
