# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x18000dd68`
- end: `0x18000de48`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `224`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180012b9c`
- `0x18002b2a4`
- `0x1800320a8`
- `0x180038740`

## callees

- `0x18000dd68`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddcd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dde7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de01`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ddcd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dde7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de01`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000de35`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(
        StateRepository::Cache::Entity::Application_NoThrow *this,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx

  v3 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v3 )
    SRCache_Free(v3, a2);
  v4 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v4 )
    SRCache_Free(v4, a2);
  v5 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v5 )
    SRCache_Free(v5, a2);
  v6 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v6 )
    SRCache_Free(v6, a2);
  v7 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v7 )
    SRCache_Free(v7, a2);
  v8 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v8 )
    SRCache_Free(v8, a2);
  v9 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v9 )
    SRCache_Free(v9, a2);
  v10 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v10 )
    SRCache_Free(v10, a2);
}

```

## disassembly

```asm
0x18000dd68  push    rbx
0x18000dd6a  sub     rsp, 20h
0x18000dd6e  mov     rbx, rcx
0x18000dd71  mov     rcx, [rcx+58h]
0x18000dd75  and     qword ptr [rbx+58h], 0
0x18000dd7a  test    rcx, rcx
0x18000dd7d  jz      short loc_18000DD8B
0x18000dd7f  call    cs:__imp_SRCache_Free
0x18000dd86  nop     dword ptr [rax+rax+00h]
0x18000dd8b  mov     rcx, [rbx+50h]
0x18000dd8f  and     qword ptr [rbx+50h], 0
0x18000dd94  test    rcx, rcx
0x18000dd97  jz      short loc_18000DDA5
0x18000dd99  call    cs:__imp_SRCache_Free
0x18000dda0  nop     dword ptr [rax+rax+00h]
0x18000dda5  mov     rcx, [rbx+48h]
0x18000dda9  and     qword ptr [rbx+48h], 0
0x18000ddae  test    rcx, rcx
0x18000ddb1  jz      short loc_18000DDBF
0x18000ddb3  call    cs:__imp_SRCache_Free
0x18000ddba  nop     dword ptr [rax+rax+00h]
0x18000ddbf  mov     rcx, [rbx+40h]
0x18000ddc3  and     qword ptr [rbx+40h], 0
0x18000ddc8  test    rcx, rcx
0x18000ddcb  jz      short loc_18000DDD9
0x18000ddcd  call    cs:__imp_SRCache_Free
0x18000ddd4  nop     dword ptr [rax+rax+00h]
0x18000ddd9  mov     rcx, [rbx+38h]
0x18000dddd  and     qword ptr [rbx+38h], 0
0x18000dde2  test    rcx, rcx
0x18000dde5  jz      short loc_18000DDF3
0x18000dde7  call    cs:__imp_SRCache_Free
0x18000ddee  nop     dword ptr [rax+rax+00h]
0x18000ddf3  mov     rcx, [rbx+30h]
0x18000ddf7  and     qword ptr [rbx+30h], 0
0x18000ddfc  test    rcx, rcx
0x18000ddff  jz      short loc_18000DE0D
0x18000de01  call    cs:__imp_SRCache_Free
0x18000de08  nop     dword ptr [rax+rax+00h]
0x18000de0d  mov     rcx, [rbx+20h]
0x18000de11  and     qword ptr [rbx+20h], 0
0x18000de16  test    rcx, rcx
0x18000de19  jz      short loc_18000DE27
0x18000de1b  call    cs:__imp_SRCache_Free
0x18000de22  nop     dword ptr [rax+rax+00h]
0x18000de27  mov     rcx, [rbx+18h]
0x18000de2b  and     qword ptr [rbx+18h], 0
0x18000de30  test    rcx, rcx
0x18000de33  jz      short loc_18000DE41
0x18000de35  call    cs:__imp_SRCache_Free
0x18000de3c  nop     dword ptr [rax+rax+00h]
0x18000de41  add     rsp, 20h
0x18000de45  pop     rbx
0x18000de46  retn
```
