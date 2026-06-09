# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x18000de50`
- end: `0x18000dee8`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `152`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b2a4`
- `0x1800320a8`
- `0x1800334c8`
- `0x180038740`

## callees

- `0x18000de50`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000deb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ded0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000deb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ded0`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(
        StateRepository::Cache::Entity::Package_NoThrow *this,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v3 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v3 )
    SRCache_Free(v3, a2);
  v4 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v4 )
    SRCache_Free(v4, a2);
  v5 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v5 )
    SRCache_Free(v5, a2);
  v6 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v6 )
    SRCache_Free(v6, a2);
  v7 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v7 )
    SRCache_Free(v7, a2);
}

```

## disassembly

```asm
0x18000de50  mov     [rsp+arg_0], rbx
0x18000de55  push    rdi
0x18000de56  sub     rsp, 20h
0x18000de5a  mov     rbx, rcx
0x18000de5d  xor     edi, edi
0x18000de5f  mov     rcx, [rcx+58h]
0x18000de63  mov     [rbx+58h], rdi
0x18000de67  test    rcx, rcx
0x18000de6a  jz      short loc_18000DE78
0x18000de6c  call    cs:__imp_SRCache_Free
0x18000de73  nop     dword ptr [rax+rax+00h]
0x18000de78  mov     rcx, [rbx+48h]
0x18000de7c  mov     [rbx+48h], rdi
0x18000de80  test    rcx, rcx
0x18000de83  jz      short loc_18000DE91
0x18000de85  call    cs:__imp_SRCache_Free
0x18000de8c  nop     dword ptr [rax+rax+00h]
0x18000de91  mov     rcx, [rbx+40h]
0x18000de95  mov     [rbx+40h], rdi
0x18000de99  test    rcx, rcx
0x18000de9c  jz      short loc_18000DEAA
0x18000de9e  call    cs:__imp_SRCache_Free
0x18000dea5  nop     dword ptr [rax+rax+00h]
0x18000deaa  mov     rcx, [rbx+38h]
0x18000deae  mov     [rbx+38h], rdi
0x18000deb2  test    rcx, rcx
0x18000deb5  jz      short loc_18000DEC3
0x18000deb7  call    cs:__imp_SRCache_Free
0x18000debe  nop     dword ptr [rax+rax+00h]
0x18000dec3  mov     rcx, [rbx+8]
0x18000dec7  mov     [rbx+8], rdi
0x18000decb  test    rcx, rcx
0x18000dece  jz      short loc_18000DEDC
0x18000ded0  call    cs:__imp_SRCache_Free
0x18000ded7  nop     dword ptr [rax+rax+00h]
0x18000dedc  mov     rbx, [rsp+28h+arg_0]
0x18000dee1  add     rsp, 20h
0x18000dee5  pop     rdi
0x18000dee6  retn
```
