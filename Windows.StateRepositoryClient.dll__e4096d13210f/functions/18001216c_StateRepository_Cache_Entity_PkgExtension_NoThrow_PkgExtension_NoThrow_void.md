# StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)

- ea: `0x18001216c`
- end: `0x180012205`
- name: `??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PkgExtension_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800123a8`
- `0x180016d0c`

## callees

- `0x18001216c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012186`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001219d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800121b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800121cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800121e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800121f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012186`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001219d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800121b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800121cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800121e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800121f9`

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
0x18001216c  push    rbx
0x18001216e  sub     rsp, 20h
0x180012172  mov     rbx, rcx
0x180012175  mov     rcx, [rcx+38h]
0x180012179  mov     qword ptr [rbx+38h], 0
0x180012181  test    rcx, rcx
0x180012184  jz      short loc_18001218C
0x180012186  call    cs:__imp_SRCache_Free
0x18001218c  mov     rcx, [rbx+28h]
0x180012190  mov     qword ptr [rbx+28h], 0
0x180012198  test    rcx, rcx
0x18001219b  jz      short loc_1800121A3
0x18001219d  call    cs:__imp_SRCache_Free
0x1800121a3  mov     rcx, [rbx+20h]
0x1800121a7  mov     qword ptr [rbx+20h], 0
0x1800121af  test    rcx, rcx
0x1800121b2  jz      short loc_1800121BA
0x1800121b4  call    cs:__imp_SRCache_Free
0x1800121ba  mov     rcx, [rbx+18h]
0x1800121be  mov     qword ptr [rbx+18h], 0
0x1800121c6  test    rcx, rcx
0x1800121c9  jz      short loc_1800121D1
0x1800121cb  call    cs:__imp_SRCache_Free
0x1800121d1  mov     rcx, [rbx+10h]
0x1800121d5  mov     qword ptr [rbx+10h], 0
0x1800121dd  test    rcx, rcx
0x1800121e0  jz      short loc_1800121E8
0x1800121e2  call    cs:__imp_SRCache_Free
0x1800121e8  mov     rcx, [rbx+8]
0x1800121ec  mov     qword ptr [rbx+8], 0
0x1800121f4  test    rcx, rcx
0x1800121f7  jz      short loc_1800121FF
0x1800121f9  call    cs:__imp_SRCache_Free
0x1800121ff  add     rsp, 20h
0x180012203  pop     rbx
0x180012204  retn
```
