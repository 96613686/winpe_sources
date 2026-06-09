# StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)

- ea: `0x180016c98`
- end: `0x180016d03`
- name: `??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PackageExtension_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016d0c`

## callees

- `0x180016c98`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016cb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016cc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016ce0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016cf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016cb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016cc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016ce0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016cf7`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(
        StateRepository::Cache::Entity::PackageExtension_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v2 )
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v5 )
    SRCache_Free(v5);
}

```

## disassembly

```asm
0x180016c98  push    rbx
0x180016c9a  sub     rsp, 20h
0x180016c9e  mov     rbx, rcx
0x180016ca1  mov     rcx, [rcx+38h]
0x180016ca5  mov     qword ptr [rbx+38h], 0
0x180016cad  test    rcx, rcx
0x180016cb0  jz      short loc_180016CB8
0x180016cb2  call    cs:__imp_SRCache_Free
0x180016cb8  mov     rcx, [rbx+30h]
0x180016cbc  mov     qword ptr [rbx+30h], 0
0x180016cc4  test    rcx, rcx
0x180016cc7  jz      short loc_180016CCF
0x180016cc9  call    cs:__imp_SRCache_Free
0x180016ccf  mov     rcx, [rbx+28h]
0x180016cd3  mov     qword ptr [rbx+28h], 0
0x180016cdb  test    rcx, rcx
0x180016cde  jz      short loc_180016CE6
0x180016ce0  call    cs:__imp_SRCache_Free
0x180016ce6  mov     rcx, [rbx+18h]
0x180016cea  mov     qword ptr [rbx+18h], 0
0x180016cf2  test    rcx, rcx
0x180016cf5  jz      short loc_180016CFD
0x180016cf7  call    cs:__imp_SRCache_Free
0x180016cfd  add     rsp, 20h
0x180016d01  pop     rbx
0x180016d02  retn
```
