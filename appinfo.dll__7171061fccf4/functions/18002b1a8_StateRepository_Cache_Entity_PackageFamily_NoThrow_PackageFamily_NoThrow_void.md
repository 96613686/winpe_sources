# StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)

- ea: `0x18002b1a8`
- end: `0x18002b1e5`
- name: `??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PackageFamily_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180036898`

## callees

- `0x18002b1a8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002b1c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002b1d9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002b1c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002b1d9`

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
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v3 )
    SRCache_Free(v3);
}

```

## disassembly

```asm
0x18002b1a8  push    rbx
0x18002b1aa  sub     rsp, 20h
0x18002b1ae  mov     rbx, rcx
0x18002b1b1  mov     rcx, [rcx+60h]
0x18002b1b5  mov     qword ptr [rbx+60h], 0
0x18002b1bd  test    rcx, rcx
0x18002b1c0  jz      short loc_18002B1C8
0x18002b1c2  call    cs:__imp_SRCache_Free
0x18002b1c8  mov     rcx, [rbx+8]
0x18002b1cc  mov     qword ptr [rbx+8], 0
0x18002b1d4  test    rcx, rcx
0x18002b1d7  jz      short loc_18002B1DF
0x18002b1d9  call    cs:__imp_SRCache_Free
0x18002b1df  add     rsp, 20h
0x18002b1e3  pop     rbx
0x18002b1e4  retn
```
