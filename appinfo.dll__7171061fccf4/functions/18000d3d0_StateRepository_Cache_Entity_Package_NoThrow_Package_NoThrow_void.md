# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x18000d3d0`
- end: `0x18000d449`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `121`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180018228`
- `0x1800187f0`
- `0x180035698`
- `0x180036898`

## callees

- `0x18000d3d0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d3ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d3ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d412`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d425`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d438`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d3ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d3ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d412`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d425`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000d438`

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
0x18000d3d0  mov     [rsp+arg_0], rbx
0x18000d3d5  push    rdi
0x18000d3d6  sub     rsp, 20h
0x18000d3da  mov     rbx, rcx
0x18000d3dd  xor     edi, edi
0x18000d3df  mov     rcx, [rcx+58h]
0x18000d3e3  mov     [rbx+58h], rdi
0x18000d3e7  test    rcx, rcx
0x18000d3ea  jz      short loc_18000D3F2
0x18000d3ec  call    cs:__imp_SRCache_Free
0x18000d3f2  mov     rcx, [rbx+48h]
0x18000d3f6  mov     [rbx+48h], rdi
0x18000d3fa  test    rcx, rcx
0x18000d3fd  jz      short loc_18000D405
0x18000d3ff  call    cs:__imp_SRCache_Free
0x18000d405  mov     rcx, [rbx+40h]
0x18000d409  mov     [rbx+40h], rdi
0x18000d40d  test    rcx, rcx
0x18000d410  jz      short loc_18000D418
0x18000d412  call    cs:__imp_SRCache_Free
0x18000d418  mov     rcx, [rbx+38h]
0x18000d41c  mov     [rbx+38h], rdi
0x18000d420  test    rcx, rcx
0x18000d423  jz      short loc_18000D42B
0x18000d425  call    cs:__imp_SRCache_Free
0x18000d42b  mov     rcx, [rbx+8]
0x18000d42f  mov     [rbx+8], rdi
0x18000d433  test    rcx, rcx
0x18000d436  jz      short loc_18000D43E
0x18000d438  call    cs:__imp_SRCache_Free
0x18000d43e  mov     rbx, [rsp+28h+arg_0]
0x18000d443  add     rsp, 20h
0x18000d447  pop     rdi
0x18000d448  retn
```
