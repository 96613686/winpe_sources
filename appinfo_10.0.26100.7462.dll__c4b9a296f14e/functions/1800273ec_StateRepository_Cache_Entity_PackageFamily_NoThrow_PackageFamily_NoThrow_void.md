# StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)

- ea: `0x1800273ec`
- end: `0x180027430`
- name: `??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PackageFamily_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800337f8`

## callees

- `0x1800273ec`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180027403`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002741d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180027403`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002741d`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(
        StateRepository::Cache::Entity::PackageFamily_NoThrow *this,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx

  v3 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  if ( v3 )
    SRCache_Free(v3, a2);
  v4 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v4 )
    SRCache_Free(v4, a2);
}

```

## disassembly

```asm
0x1800273ec  push    rbx
0x1800273ee  sub     rsp, 20h
0x1800273f2  mov     rbx, rcx
0x1800273f5  mov     rcx, [rcx+60h]
0x1800273f9  and     qword ptr [rbx+60h], 0
0x1800273fe  test    rcx, rcx
0x180027401  jz      short loc_18002740F
0x180027403  call    cs:__imp_SRCache_Free
0x18002740a  nop     dword ptr [rax+rax+00h]
0x18002740f  mov     rcx, [rbx+8]
0x180027413  and     qword ptr [rbx+8], 0
0x180027418  test    rcx, rcx
0x18002741b  jz      short loc_180027429
0x18002741d  call    cs:__imp_SRCache_Free
0x180027424  nop     dword ptr [rax+rax+00h]
0x180027429  add     rsp, 20h
0x18002742d  pop     rbx
0x18002742e  retn
```
