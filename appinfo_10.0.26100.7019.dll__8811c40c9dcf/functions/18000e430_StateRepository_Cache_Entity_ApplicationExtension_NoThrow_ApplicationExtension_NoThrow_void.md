# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x18000e430`
- end: `0x18000e4ca`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `154`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012b9c`

## callees

- `0x18000e430`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e459`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e472`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e48b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e4a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e4bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e459`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e472`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e48b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e4a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e4bc`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow *this,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

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
  v7 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v7 )
    SRCache_Free(v7, a2);
}

```

## disassembly

```asm
0x18000e430  mov     [rsp+arg_0], rbx
0x18000e435  push    rdi
0x18000e436  sub     rsp, 20h
0x18000e43a  mov     rbx, rcx
0x18000e43d  xor     edi, edi
0x18000e43f  mov     rcx, [rcx+40h]
0x18000e443  mov     [rbx+40h], rdi
0x18000e447  test    rcx, rcx
0x18000e44a  jnz     short loc_18000E4BC
0x18000e44c  mov     rcx, [rbx+38h]
0x18000e450  mov     [rbx+38h], rdi
0x18000e454  test    rcx, rcx
0x18000e457  jz      short loc_18000E465
0x18000e459  call    cs:__imp_SRCache_Free
0x18000e460  nop     dword ptr [rax+rax+00h]
0x18000e465  mov     rcx, [rbx+30h]
0x18000e469  mov     [rbx+30h], rdi
0x18000e46d  test    rcx, rcx
0x18000e470  jz      short loc_18000E47E
0x18000e472  call    cs:__imp_SRCache_Free
0x18000e479  nop     dword ptr [rax+rax+00h]
0x18000e47e  mov     rcx, [rbx+28h]
0x18000e482  mov     [rbx+28h], rdi
0x18000e486  test    rcx, rcx
0x18000e489  jz      short loc_18000E497
0x18000e48b  call    cs:__imp_SRCache_Free
0x18000e492  nop     dword ptr [rax+rax+00h]
0x18000e497  mov     rcx, [rbx+18h]
0x18000e49b  mov     [rbx+18h], rdi
0x18000e49f  test    rcx, rcx
0x18000e4a2  jz      short loc_18000E4B0
0x18000e4a4  call    cs:__imp_SRCache_Free
0x18000e4ab  nop     dword ptr [rax+rax+00h]
0x18000e4b0  mov     rbx, [rsp+28h+arg_0]
0x18000e4b5  add     rsp, 20h
0x18000e4b9  pop     rdi
0x18000e4ba  retn
0x18000e4bc  call    cs:__imp_SRCache_Free
0x18000e4c3  nop     dword ptr [rax+rax+00h]
0x18000e4c8  jmp     short loc_18000E44C
```
