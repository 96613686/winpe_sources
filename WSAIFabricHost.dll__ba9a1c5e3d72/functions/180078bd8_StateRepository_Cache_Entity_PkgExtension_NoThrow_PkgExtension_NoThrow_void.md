# StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)

- ea: `0x180078bd8`
- end: `0x180078c71`
- name: `??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PkgExtension_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180078fd0`
- `0x18008811f`

## callees

- `0x180078bd8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078bf2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c09`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078bf2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c09`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078c65`

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
    SRCache_Free();
  v3 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v6 )
    SRCache_Free();
  v7 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v7 )
    SRCache_Free();
}

```

## disassembly

```asm
0x180078bd8  push    rbx
0x180078bda  sub     rsp, 20h
0x180078bde  mov     rbx, rcx
0x180078be1  mov     rcx, [rcx+38h]
0x180078be5  mov     qword ptr [rbx+38h], 0
0x180078bed  test    rcx, rcx
0x180078bf0  jz      short loc_180078BF8
0x180078bf2  call    cs:__imp_SRCache_Free
0x180078bf8  mov     rcx, [rbx+28h]
0x180078bfc  mov     qword ptr [rbx+28h], 0
0x180078c04  test    rcx, rcx
0x180078c07  jz      short loc_180078C0F
0x180078c09  call    cs:__imp_SRCache_Free
0x180078c0f  mov     rcx, [rbx+20h]
0x180078c13  mov     qword ptr [rbx+20h], 0
0x180078c1b  test    rcx, rcx
0x180078c1e  jz      short loc_180078C26
0x180078c20  call    cs:__imp_SRCache_Free
0x180078c26  mov     rcx, [rbx+18h]
0x180078c2a  mov     qword ptr [rbx+18h], 0
0x180078c32  test    rcx, rcx
0x180078c35  jz      short loc_180078C3D
0x180078c37  call    cs:__imp_SRCache_Free
0x180078c3d  mov     rcx, [rbx+10h]
0x180078c41  mov     qword ptr [rbx+10h], 0
0x180078c49  test    rcx, rcx
0x180078c4c  jz      short loc_180078C54
0x180078c4e  call    cs:__imp_SRCache_Free
0x180078c54  mov     rcx, [rbx+8]
0x180078c58  mov     qword ptr [rbx+8], 0
0x180078c60  test    rcx, rcx
0x180078c63  jz      short loc_180078C6B
0x180078c65  call    cs:__imp_SRCache_Free
0x180078c6b  add     rsp, 20h
0x180078c6f  pop     rbx
0x180078c70  retn
```
