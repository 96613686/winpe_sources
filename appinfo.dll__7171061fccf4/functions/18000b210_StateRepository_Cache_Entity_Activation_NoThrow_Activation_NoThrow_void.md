# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x18000b210`
- end: `0x18000b2af`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a938`

## callees

- `0x18000b210`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b22c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b23f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b252`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b265`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b278`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b28b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b29e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b22c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b23f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b252`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b265`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b278`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b28b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b29e`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(
        StateRepository::Cache::Entity::Activation_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

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
  v6 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v6 )
    SRCache_Free(v6);
  v7 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v7 )
    SRCache_Free(v7);
  v8 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v8 )
    SRCache_Free(v8);
}

```

## disassembly

```asm
0x18000b210  mov     [rsp+arg_0], rbx
0x18000b215  push    rdi
0x18000b216  sub     rsp, 20h
0x18000b21a  mov     rbx, rcx
0x18000b21d  xor     edi, edi
0x18000b21f  mov     rcx, [rcx+40h]
0x18000b223  mov     [rbx+40h], rdi
0x18000b227  test    rcx, rcx
0x18000b22a  jz      short loc_18000B232
0x18000b22c  call    cs:__imp_SRCache_Free
0x18000b232  mov     rcx, [rbx+38h]
0x18000b236  mov     [rbx+38h], rdi
0x18000b23a  test    rcx, rcx
0x18000b23d  jz      short loc_18000B245
0x18000b23f  call    cs:__imp_SRCache_Free
0x18000b245  mov     rcx, [rbx+30h]
0x18000b249  mov     [rbx+30h], rdi
0x18000b24d  test    rcx, rcx
0x18000b250  jz      short loc_18000B258
0x18000b252  call    cs:__imp_SRCache_Free
0x18000b258  mov     rcx, [rbx+28h]
0x18000b25c  mov     [rbx+28h], rdi
0x18000b260  test    rcx, rcx
0x18000b263  jz      short loc_18000B26B
0x18000b265  call    cs:__imp_SRCache_Free
0x18000b26b  mov     rcx, [rbx+20h]
0x18000b26f  mov     [rbx+20h], rdi
0x18000b273  test    rcx, rcx
0x18000b276  jz      short loc_18000B27E
0x18000b278  call    cs:__imp_SRCache_Free
0x18000b27e  mov     rcx, [rbx+18h]
0x18000b282  mov     [rbx+18h], rdi
0x18000b286  test    rcx, rcx
0x18000b289  jz      short loc_18000B291
0x18000b28b  call    cs:__imp_SRCache_Free
0x18000b291  mov     rcx, [rbx+8]
0x18000b295  mov     [rbx+8], rdi
0x18000b299  test    rcx, rcx
0x18000b29c  jz      short loc_18000B2A4
0x18000b29e  call    cs:__imp_SRCache_Free
0x18000b2a4  mov     rbx, [rsp+28h+arg_0]
0x18000b2a9  add     rsp, 20h
0x18000b2ad  pop     rdi
0x18000b2ae  retn
```
