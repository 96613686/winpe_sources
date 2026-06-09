# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x18000e370`
- end: `0x18000e40a`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `154`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012cdc`

## callees

- `0x18000e370`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e399`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e3b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e3cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e3e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e3fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e399`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e3b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e3cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e3e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e3fc`

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
0x18000e370  mov     [rsp+arg_0], rbx
0x18000e375  push    rdi
0x18000e376  sub     rsp, 20h
0x18000e37a  mov     rbx, rcx
0x18000e37d  xor     edi, edi
0x18000e37f  mov     rcx, [rcx+40h]
0x18000e383  mov     [rbx+40h], rdi
0x18000e387  test    rcx, rcx
0x18000e38a  jnz     short loc_18000E3FC
0x18000e38c  mov     rcx, [rbx+38h]
0x18000e390  mov     [rbx+38h], rdi
0x18000e394  test    rcx, rcx
0x18000e397  jz      short loc_18000E3A5
0x18000e399  call    cs:__imp_SRCache_Free
0x18000e3a0  nop     dword ptr [rax+rax+00h]
0x18000e3a5  mov     rcx, [rbx+30h]
0x18000e3a9  mov     [rbx+30h], rdi
0x18000e3ad  test    rcx, rcx
0x18000e3b0  jz      short loc_18000E3BE
0x18000e3b2  call    cs:__imp_SRCache_Free
0x18000e3b9  nop     dword ptr [rax+rax+00h]
0x18000e3be  mov     rcx, [rbx+28h]
0x18000e3c2  mov     [rbx+28h], rdi
0x18000e3c6  test    rcx, rcx
0x18000e3c9  jz      short loc_18000E3D7
0x18000e3cb  call    cs:__imp_SRCache_Free
0x18000e3d2  nop     dword ptr [rax+rax+00h]
0x18000e3d7  mov     rcx, [rbx+18h]
0x18000e3db  mov     [rbx+18h], rdi
0x18000e3df  test    rcx, rcx
0x18000e3e2  jz      short loc_18000E3F0
0x18000e3e4  call    cs:__imp_SRCache_Free
0x18000e3eb  nop     dword ptr [rax+rax+00h]
0x18000e3f0  mov     rbx, [rsp+28h+arg_0]
0x18000e3f5  add     rsp, 20h
0x18000e3f9  pop     rdi
0x18000e3fa  retn
0x18000e3fc  call    cs:__imp_SRCache_Free
0x18000e403  nop     dword ptr [rax+rax+00h]
0x18000e408  jmp     short loc_18000E38C
```
