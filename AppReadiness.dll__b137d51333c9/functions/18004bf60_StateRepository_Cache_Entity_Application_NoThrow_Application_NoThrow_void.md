# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x18004bf60`
- end: `0x18004c027`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004da98`
- `0x180077edc`

## callees

- `0x18004bf60`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bfa8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bfbf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bfd6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bfed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c004`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c01b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bf91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bfa8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bfbf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bfd6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004bfed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c004`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004c01b`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(
        StateRepository::Cache::Entity::Application_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  v2 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v6 )
    SRCache_Free();
  v7 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v7 )
    SRCache_Free();
  v8 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v8 )
    SRCache_Free();
  v9 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v9 )
    SRCache_Free();
}

```

## disassembly

```asm
0x18004bf60  push    rbx
0x18004bf62  sub     rsp, 20h
0x18004bf66  mov     rbx, rcx
0x18004bf69  mov     rcx, [rcx+58h]
0x18004bf6d  mov     qword ptr [rbx+58h], 0
0x18004bf75  test    rcx, rcx
0x18004bf78  jz      short loc_18004BF80
0x18004bf7a  call    cs:__imp_SRCache_Free
0x18004bf80  mov     rcx, [rbx+50h]
0x18004bf84  mov     qword ptr [rbx+50h], 0
0x18004bf8c  test    rcx, rcx
0x18004bf8f  jz      short loc_18004BF97
0x18004bf91  call    cs:__imp_SRCache_Free
0x18004bf97  mov     rcx, [rbx+48h]
0x18004bf9b  mov     qword ptr [rbx+48h], 0
0x18004bfa3  test    rcx, rcx
0x18004bfa6  jz      short loc_18004BFAE
0x18004bfa8  call    cs:__imp_SRCache_Free
0x18004bfae  mov     rcx, [rbx+40h]
0x18004bfb2  mov     qword ptr [rbx+40h], 0
0x18004bfba  test    rcx, rcx
0x18004bfbd  jz      short loc_18004BFC5
0x18004bfbf  call    cs:__imp_SRCache_Free
0x18004bfc5  mov     rcx, [rbx+38h]
0x18004bfc9  mov     qword ptr [rbx+38h], 0
0x18004bfd1  test    rcx, rcx
0x18004bfd4  jz      short loc_18004BFDC
0x18004bfd6  call    cs:__imp_SRCache_Free
0x18004bfdc  mov     rcx, [rbx+30h]
0x18004bfe0  mov     qword ptr [rbx+30h], 0
0x18004bfe8  test    rcx, rcx
0x18004bfeb  jz      short loc_18004BFF3
0x18004bfed  call    cs:__imp_SRCache_Free
0x18004bff3  mov     rcx, [rbx+20h]
0x18004bff7  mov     qword ptr [rbx+20h], 0
0x18004bfff  test    rcx, rcx
0x18004c002  jz      short loc_18004C00A
0x18004c004  call    cs:__imp_SRCache_Free
0x18004c00a  mov     rcx, [rbx+18h]
0x18004c00e  mov     qword ptr [rbx+18h], 0
0x18004c016  test    rcx, rcx
0x18004c019  jz      short loc_18004C021
0x18004c01b  call    cs:__imp_SRCache_Free
0x18004c021  add     rsp, 20h
0x18004c025  pop     rbx
0x18004c026  retn
```
