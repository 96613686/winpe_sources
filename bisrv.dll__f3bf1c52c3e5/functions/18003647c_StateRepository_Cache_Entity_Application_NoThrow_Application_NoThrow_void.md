# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x18003647c`
- end: `0x180036543`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800514a0`

## callees

- `0x18003647c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180036496`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800364ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800364c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800364db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800364f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180036509`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180036520`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180036537`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180036496`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800364ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800364c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800364db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800364f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180036509`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180036520`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180036537`

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
0x18003647c  push    rbx
0x18003647e  sub     rsp, 20h
0x180036482  mov     rbx, rcx
0x180036485  mov     rcx, [rcx+58h]
0x180036489  mov     qword ptr [rbx+58h], 0
0x180036491  test    rcx, rcx
0x180036494  jz      short loc_18003649C
0x180036496  call    cs:__imp_SRCache_Free
0x18003649c  mov     rcx, [rbx+50h]
0x1800364a0  mov     qword ptr [rbx+50h], 0
0x1800364a8  test    rcx, rcx
0x1800364ab  jz      short loc_1800364B3
0x1800364ad  call    cs:__imp_SRCache_Free
0x1800364b3  mov     rcx, [rbx+48h]
0x1800364b7  mov     qword ptr [rbx+48h], 0
0x1800364bf  test    rcx, rcx
0x1800364c2  jz      short loc_1800364CA
0x1800364c4  call    cs:__imp_SRCache_Free
0x1800364ca  mov     rcx, [rbx+40h]
0x1800364ce  mov     qword ptr [rbx+40h], 0
0x1800364d6  test    rcx, rcx
0x1800364d9  jz      short loc_1800364E1
0x1800364db  call    cs:__imp_SRCache_Free
0x1800364e1  mov     rcx, [rbx+38h]
0x1800364e5  mov     qword ptr [rbx+38h], 0
0x1800364ed  test    rcx, rcx
0x1800364f0  jz      short loc_1800364F8
0x1800364f2  call    cs:__imp_SRCache_Free
0x1800364f8  mov     rcx, [rbx+30h]
0x1800364fc  mov     qword ptr [rbx+30h], 0
0x180036504  test    rcx, rcx
0x180036507  jz      short loc_18003650F
0x180036509  call    cs:__imp_SRCache_Free
0x18003650f  mov     rcx, [rbx+20h]
0x180036513  mov     qword ptr [rbx+20h], 0
0x18003651b  test    rcx, rcx
0x18003651e  jz      short loc_180036526
0x180036520  call    cs:__imp_SRCache_Free
0x180036526  mov     rcx, [rbx+18h]
0x18003652a  mov     qword ptr [rbx+18h], 0
0x180036532  test    rcx, rcx
0x180036535  jz      short loc_18003653D
0x180036537  call    cs:__imp_SRCache_Free
0x18003653d  add     rsp, 20h
0x180036541  pop     rbx
0x180036542  retn
```
