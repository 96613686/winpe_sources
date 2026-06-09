# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x18000cd00`
- end: `0x18000cdca`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `202`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012b9c`

## callees

- `0x18000cd00`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd80`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cdb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd80`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cd99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000cdb2`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(
        StateRepository::Cache::Entity::Activation_NoThrow *this,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  v3 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v3 )
    SRCache_Free(v3, a2);
  v4 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v4 )
    SRCache_Free(v4, a2);
  v5 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v5 )
    SRCache_Free(v5, a2);
  v6 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v6 )
    SRCache_Free(v6, a2);
  v7 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v7 )
    SRCache_Free(v7, a2);
  v8 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v8 )
    SRCache_Free(v8, a2);
  v9 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v9 )
    SRCache_Free(v9, a2);
}

```

## disassembly

```asm
0x18000cd00  mov     [rsp+arg_0], rbx
0x18000cd05  push    rdi
0x18000cd06  sub     rsp, 20h
0x18000cd0a  mov     rbx, rcx
0x18000cd0d  xor     edi, edi
0x18000cd0f  mov     rcx, [rcx+40h]
0x18000cd13  mov     [rbx+40h], rdi
0x18000cd17  test    rcx, rcx
0x18000cd1a  jz      short loc_18000CD28
0x18000cd1c  call    cs:__imp_SRCache_Free
0x18000cd23  nop     dword ptr [rax+rax+00h]
0x18000cd28  mov     rcx, [rbx+38h]
0x18000cd2c  mov     [rbx+38h], rdi
0x18000cd30  test    rcx, rcx
0x18000cd33  jz      short loc_18000CD41
0x18000cd35  call    cs:__imp_SRCache_Free
0x18000cd3c  nop     dword ptr [rax+rax+00h]
0x18000cd41  mov     rcx, [rbx+30h]
0x18000cd45  mov     [rbx+30h], rdi
0x18000cd49  test    rcx, rcx
0x18000cd4c  jz      short loc_18000CD5A
0x18000cd4e  call    cs:__imp_SRCache_Free
0x18000cd55  nop     dword ptr [rax+rax+00h]
0x18000cd5a  mov     rcx, [rbx+28h]
0x18000cd5e  mov     [rbx+28h], rdi
0x18000cd62  test    rcx, rcx
0x18000cd65  jz      short loc_18000CD73
0x18000cd67  call    cs:__imp_SRCache_Free
0x18000cd6e  nop     dword ptr [rax+rax+00h]
0x18000cd73  mov     rcx, [rbx+20h]
0x18000cd77  mov     [rbx+20h], rdi
0x18000cd7b  test    rcx, rcx
0x18000cd7e  jz      short loc_18000CD8C
0x18000cd80  call    cs:__imp_SRCache_Free
0x18000cd87  nop     dword ptr [rax+rax+00h]
0x18000cd8c  mov     rcx, [rbx+18h]
0x18000cd90  mov     [rbx+18h], rdi
0x18000cd94  test    rcx, rcx
0x18000cd97  jz      short loc_18000CDA5
0x18000cd99  call    cs:__imp_SRCache_Free
0x18000cda0  nop     dword ptr [rax+rax+00h]
0x18000cda5  mov     rcx, [rbx+8]
0x18000cda9  mov     [rbx+8], rdi
0x18000cdad  test    rcx, rcx
0x18000cdb0  jz      short loc_18000CDBE
0x18000cdb2  call    cs:__imp_SRCache_Free
0x18000cdb9  nop     dword ptr [rax+rax+00h]
0x18000cdbe  mov     rbx, [rsp+28h+arg_0]
0x18000cdc3  add     rsp, 20h
0x18000cdc7  pop     rdi
0x18000cdc8  retn
```
