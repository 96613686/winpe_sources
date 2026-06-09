# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x18000dca8`
- end: `0x18000dd88`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `224`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180012cdc`
- `0x180029c54`
- `0x180032118`
- `0x180038de0`

## callees

- `0x18000dca8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dcbf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dcd9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dcf3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd0d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd41`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dcbf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dcd9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dcf3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd0d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd41`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000dd75`

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
0x18000dca8  push    rbx
0x18000dcaa  sub     rsp, 20h
0x18000dcae  mov     rbx, rcx
0x18000dcb1  mov     rcx, [rcx+58h]
0x18000dcb5  and     qword ptr [rbx+58h], 0
0x18000dcba  test    rcx, rcx
0x18000dcbd  jz      short loc_18000DCCB
0x18000dcbf  call    cs:__imp_SRCache_Free
0x18000dcc6  nop     dword ptr [rax+rax+00h]
0x18000dccb  mov     rcx, [rbx+50h]
0x18000dccf  and     qword ptr [rbx+50h], 0
0x18000dcd4  test    rcx, rcx
0x18000dcd7  jz      short loc_18000DCE5
0x18000dcd9  call    cs:__imp_SRCache_Free
0x18000dce0  nop     dword ptr [rax+rax+00h]
0x18000dce5  mov     rcx, [rbx+48h]
0x18000dce9  and     qword ptr [rbx+48h], 0
0x18000dcee  test    rcx, rcx
0x18000dcf1  jz      short loc_18000DCFF
0x18000dcf3  call    cs:__imp_SRCache_Free
0x18000dcfa  nop     dword ptr [rax+rax+00h]
0x18000dcff  mov     rcx, [rbx+40h]
0x18000dd03  and     qword ptr [rbx+40h], 0
0x18000dd08  test    rcx, rcx
0x18000dd0b  jz      short loc_18000DD19
0x18000dd0d  call    cs:__imp_SRCache_Free
0x18000dd14  nop     dword ptr [rax+rax+00h]
0x18000dd19  mov     rcx, [rbx+38h]
0x18000dd1d  and     qword ptr [rbx+38h], 0
0x18000dd22  test    rcx, rcx
0x18000dd25  jz      short loc_18000DD33
0x18000dd27  call    cs:__imp_SRCache_Free
0x18000dd2e  nop     dword ptr [rax+rax+00h]
0x18000dd33  mov     rcx, [rbx+30h]
0x18000dd37  and     qword ptr [rbx+30h], 0
0x18000dd3c  test    rcx, rcx
0x18000dd3f  jz      short loc_18000DD4D
0x18000dd41  call    cs:__imp_SRCache_Free
0x18000dd48  nop     dword ptr [rax+rax+00h]
0x18000dd4d  mov     rcx, [rbx+20h]
0x18000dd51  and     qword ptr [rbx+20h], 0
0x18000dd56  test    rcx, rcx
0x18000dd59  jz      short loc_18000DD67
0x18000dd5b  call    cs:__imp_SRCache_Free
0x18000dd62  nop     dword ptr [rax+rax+00h]
0x18000dd67  mov     rcx, [rbx+18h]
0x18000dd6b  and     qword ptr [rbx+18h], 0
0x18000dd70  test    rcx, rcx
0x18000dd73  jz      short loc_18000DD81
0x18000dd75  call    cs:__imp_SRCache_Free
0x18000dd7c  nop     dword ptr [rax+rax+00h]
0x18000dd81  add     rsp, 20h
0x18000dd85  pop     rbx
0x18000dd86  retn
```
