# StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)

- ea: `0x180012364`
- end: `0x1800123a1`
- name: `??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PackageFamily_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800123a8`
- `0x180016d0c`

## callees

- `0x180012364`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001237e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012395`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001237e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012395`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(
        StateRepository::Cache::Entity::PackageFamily_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v3 )
    SRCache_Free();
}

```

## disassembly

```asm
0x180012364  push    rbx
0x180012366  sub     rsp, 20h
0x18001236a  mov     rbx, rcx
0x18001236d  mov     rcx, [rcx+60h]
0x180012371  mov     qword ptr [rbx+60h], 0
0x180012379  test    rcx, rcx
0x18001237c  jz      short loc_180012384
0x18001237e  call    cs:__imp_SRCache_Free
0x180012384  mov     rcx, [rbx+8]
0x180012388  mov     qword ptr [rbx+8], 0
0x180012390  test    rcx, rcx
0x180012393  jz      short loc_18001239B
0x180012395  call    cs:__imp_SRCache_Free
0x18001239b  add     rsp, 20h
0x18001239f  pop     rbx
0x1800123a0  retn
```
