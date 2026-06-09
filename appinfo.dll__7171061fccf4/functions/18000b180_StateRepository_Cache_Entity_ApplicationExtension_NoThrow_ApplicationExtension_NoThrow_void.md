# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x18000b180`
- end: `0x18000b1fb`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a938`

## callees

- `0x18000b180`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b1a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b1bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b1cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b1e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b1f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b1a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b1bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b1cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b1e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b1f3`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v2 )
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v6 )
    SRCache_Free(v6);
}

```

## disassembly

```asm
0x18000b180  mov     [rsp+arg_0], rbx
0x18000b185  push    rdi
0x18000b186  sub     rsp, 20h
0x18000b18a  mov     rbx, rcx
0x18000b18d  xor     edi, edi
0x18000b18f  mov     rcx, [rcx+40h]
0x18000b193  mov     [rbx+40h], rdi
0x18000b197  test    rcx, rcx
0x18000b19a  jnz     short loc_18000B1F3
0x18000b19c  mov     rcx, [rbx+38h]
0x18000b1a0  mov     [rbx+38h], rdi
0x18000b1a4  test    rcx, rcx
0x18000b1a7  jz      short loc_18000B1AF
0x18000b1a9  call    cs:__imp_SRCache_Free
0x18000b1af  mov     rcx, [rbx+30h]
0x18000b1b3  mov     [rbx+30h], rdi
0x18000b1b7  test    rcx, rcx
0x18000b1ba  jz      short loc_18000B1C2
0x18000b1bc  call    cs:__imp_SRCache_Free
0x18000b1c2  mov     rcx, [rbx+28h]
0x18000b1c6  mov     [rbx+28h], rdi
0x18000b1ca  test    rcx, rcx
0x18000b1cd  jz      short loc_18000B1D5
0x18000b1cf  call    cs:__imp_SRCache_Free
0x18000b1d5  mov     rcx, [rbx+18h]
0x18000b1d9  mov     [rbx+18h], rdi
0x18000b1dd  test    rcx, rcx
0x18000b1e0  jz      short loc_18000B1E8
0x18000b1e2  call    cs:__imp_SRCache_Free
0x18000b1e8  mov     rbx, [rsp+28h+arg_0]
0x18000b1ed  add     rsp, 20h
0x18000b1f1  pop     rdi
0x18000b1f2  retn
0x18000b1f3  call    cs:__imp_SRCache_Free
0x18000b1f9  jmp     short loc_18000B19C
```
