# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x18000dd90`
- end: `0x18000de28`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `152`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180029d24`
- `0x1800323d8`
- `0x1800337f8`
- `0x180039120`

## callees

- `0x18000dd90`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddc5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddde`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de10`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddc5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddde`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de10`

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
0x18000dd90  mov     [rsp+arg_0], rbx
0x18000dd95  push    rdi
0x18000dd96  sub     rsp, 20h
0x18000dd9a  mov     rbx, rcx
0x18000dd9d  xor     edi, edi
0x18000dd9f  mov     rcx, [rcx+58h]
0x18000dda3  mov     [rbx+58h], rdi
0x18000dda7  test    rcx, rcx
0x18000ddaa  jz      short loc_18000DDB8
0x18000ddac  call    cs:__imp_SRCache_Free
0x18000ddb3  nop     dword ptr [rax+rax+00h]
0x18000ddb8  mov     rcx, [rbx+48h]
0x18000ddbc  mov     [rbx+48h], rdi
0x18000ddc0  test    rcx, rcx
0x18000ddc3  jz      short loc_18000DDD1
0x18000ddc5  call    cs:__imp_SRCache_Free
0x18000ddcc  nop     dword ptr [rax+rax+00h]
0x18000ddd1  mov     rcx, [rbx+40h]
0x18000ddd5  mov     [rbx+40h], rdi
0x18000ddd9  test    rcx, rcx
0x18000dddc  jz      short loc_18000DDEA
0x18000ddde  call    cs:__imp_SRCache_Free
0x18000dde5  nop     dword ptr [rax+rax+00h]
0x18000ddea  mov     rcx, [rbx+38h]
0x18000ddee  mov     [rbx+38h], rdi
0x18000ddf2  test    rcx, rcx
0x18000ddf5  jz      short loc_18000DE03
0x18000ddf7  call    cs:__imp_SRCache_Free
0x18000ddfe  nop     dword ptr [rax+rax+00h]
0x18000de03  mov     rcx, [rbx+8]
0x18000de07  mov     [rbx+8], rdi
0x18000de0b  test    rcx, rcx
0x18000de0e  jz      short loc_18000DE1C
0x18000de10  call    cs:__imp_SRCache_Free
0x18000de17  nop     dword ptr [rax+rax+00h]
0x18000de1c  mov     rbx, [rsp+28h+arg_0]
0x18000de21  add     rsp, 20h
0x18000de25  pop     rdi
0x18000de26  retn
```
