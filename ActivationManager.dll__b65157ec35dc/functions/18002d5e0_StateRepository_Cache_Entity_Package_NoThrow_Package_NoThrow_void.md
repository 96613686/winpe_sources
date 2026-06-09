# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x18002d5e0`
- end: `0x18002d670`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180009d60`
- `0x18002c930`
- `0x18002ce50`
- `0x180045be4`
- `0x18006ea40`
- `0x18006f2f4`
- `0x18008e300`
- `0x18008e690`
- `0x180090cd0`
- `0x18009b3e0`
- `0x18009ef30`

## callees

- `0x18002d5e0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d644`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d64c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d654`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d65c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d644`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d64c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d654`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d65c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d669`

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
0x18002d5e0  push    rbx
0x18002d5e2  sub     rsp, 20h
0x18002d5e6  mov     rbx, rcx
0x18002d5e9  mov     rcx, [rcx+58h]
0x18002d5ed  mov     qword ptr [rbx+58h], 0
0x18002d5f5  test    rcx, rcx
0x18002d5f8  jnz     short loc_18002D644
0x18002d5fa  mov     rcx, [rbx+48h]
0x18002d5fe  mov     qword ptr [rbx+48h], 0
0x18002d606  test    rcx, rcx
0x18002d609  jnz     short loc_18002D64C
0x18002d60b  mov     rcx, [rbx+40h]
0x18002d60f  mov     qword ptr [rbx+40h], 0
0x18002d617  test    rcx, rcx
0x18002d61a  jnz     short loc_18002D654
0x18002d61c  mov     rcx, [rbx+38h]
0x18002d620  mov     qword ptr [rbx+38h], 0
0x18002d628  test    rcx, rcx
0x18002d62b  jnz     short loc_18002D65C
0x18002d62d  mov     rcx, [rbx+8]
0x18002d631  mov     qword ptr [rbx+8], 0
0x18002d639  test    rcx, rcx
0x18002d63c  jnz     short loc_18002D664
0x18002d63e  add     rsp, 20h
0x18002d642  pop     rbx
0x18002d643  retn
0x18002d644  call    cs:__imp_SRCache_Free
0x18002d64a  jmp     short loc_18002D5FA
0x18002d64c  call    cs:__imp_SRCache_Free
0x18002d652  jmp     short loc_18002D60B
0x18002d654  call    cs:__imp_SRCache_Free
0x18002d65a  jmp     short loc_18002D61C
0x18002d65c  call    cs:__imp_SRCache_Free
0x18002d662  jmp     short loc_18002D62D
0x18002d664  add     rsp, 20h
0x18002d668  pop     rbx
0x18002d669  jmp     cs:__imp_SRCache_Free
```
