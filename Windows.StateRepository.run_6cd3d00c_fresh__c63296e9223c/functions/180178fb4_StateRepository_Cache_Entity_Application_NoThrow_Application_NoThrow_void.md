# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x180178fb4`
- end: `0x18017907b`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180178a70`

## callees

- `0x180178fb4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180178fce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180178fe5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180178ffc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180179013`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18017902a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180179041`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180179058`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18017906f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180178fce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180178fe5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180178ffc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180179013`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18017902a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180179041`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180179058`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18017906f`

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
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v6 )
    SRCache_Free(v6);
  v7 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v7 )
    SRCache_Free(v7);
  v8 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v8 )
    SRCache_Free(v8);
  v9 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v9 )
    SRCache_Free(v9);
}

```

## disassembly

```asm
0x180178fb4  push    rbx
0x180178fb6  sub     rsp, 20h
0x180178fba  mov     rbx, rcx
0x180178fbd  mov     rcx, [rcx+58h]
0x180178fc1  mov     qword ptr [rbx+58h], 0
0x180178fc9  test    rcx, rcx
0x180178fcc  jz      short loc_180178FD4
0x180178fce  call    cs:__imp_SRCache_Free
0x180178fd4  mov     rcx, [rbx+50h]
0x180178fd8  mov     qword ptr [rbx+50h], 0
0x180178fe0  test    rcx, rcx
0x180178fe3  jz      short loc_180178FEB
0x180178fe5  call    cs:__imp_SRCache_Free
0x180178feb  mov     rcx, [rbx+48h]
0x180178fef  mov     qword ptr [rbx+48h], 0
0x180178ff7  test    rcx, rcx
0x180178ffa  jz      short loc_180179002
0x180178ffc  call    cs:__imp_SRCache_Free
0x180179002  mov     rcx, [rbx+40h]
0x180179006  mov     qword ptr [rbx+40h], 0
0x18017900e  test    rcx, rcx
0x180179011  jz      short loc_180179019
0x180179013  call    cs:__imp_SRCache_Free
0x180179019  mov     rcx, [rbx+38h]
0x18017901d  mov     qword ptr [rbx+38h], 0
0x180179025  test    rcx, rcx
0x180179028  jz      short loc_180179030
0x18017902a  call    cs:__imp_SRCache_Free
0x180179030  mov     rcx, [rbx+30h]
0x180179034  mov     qword ptr [rbx+30h], 0
0x18017903c  test    rcx, rcx
0x18017903f  jz      short loc_180179047
0x180179041  call    cs:__imp_SRCache_Free
0x180179047  mov     rcx, [rbx+20h]
0x18017904b  mov     qword ptr [rbx+20h], 0
0x180179053  test    rcx, rcx
0x180179056  jz      short loc_18017905E
0x180179058  call    cs:__imp_SRCache_Free
0x18017905e  mov     rcx, [rbx+18h]
0x180179062  mov     qword ptr [rbx+18h], 0
0x18017906a  test    rcx, rcx
0x18017906d  jz      short loc_180179075
0x18017906f  call    cs:__imp_SRCache_Free
0x180179075  add     rsp, 20h
0x180179079  pop     rbx
0x18017907a  retn
```
