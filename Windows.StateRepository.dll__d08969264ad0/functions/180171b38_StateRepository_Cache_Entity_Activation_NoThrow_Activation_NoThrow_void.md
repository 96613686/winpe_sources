# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x180171b38`
- end: `0x180171be8`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1801715b0`

## callees

- `0x180171b38`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171b52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171b69`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171b80`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171b97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171bae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171bc5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171bdc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171b52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171b69`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171b80`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171b97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171bae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171bc5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180171bdc`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(
        StateRepository::Cache::Entity::Activation_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

  v2 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v2 )
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v6 )
    SRCache_Free(v6);
  v7 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v7 )
    SRCache_Free(v7);
  v8 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v8 )
    SRCache_Free(v8);
}

```

## disassembly

```asm
0x180171b38  push    rbx
0x180171b3a  sub     rsp, 20h
0x180171b3e  mov     rbx, rcx
0x180171b41  mov     rcx, [rcx+40h]
0x180171b45  mov     qword ptr [rbx+40h], 0
0x180171b4d  test    rcx, rcx
0x180171b50  jz      short loc_180171B58
0x180171b52  call    cs:__imp_SRCache_Free
0x180171b58  mov     rcx, [rbx+38h]
0x180171b5c  mov     qword ptr [rbx+38h], 0
0x180171b64  test    rcx, rcx
0x180171b67  jz      short loc_180171B6F
0x180171b69  call    cs:__imp_SRCache_Free
0x180171b6f  mov     rcx, [rbx+30h]
0x180171b73  mov     qword ptr [rbx+30h], 0
0x180171b7b  test    rcx, rcx
0x180171b7e  jz      short loc_180171B86
0x180171b80  call    cs:__imp_SRCache_Free
0x180171b86  mov     rcx, [rbx+28h]
0x180171b8a  mov     qword ptr [rbx+28h], 0
0x180171b92  test    rcx, rcx
0x180171b95  jz      short loc_180171B9D
0x180171b97  call    cs:__imp_SRCache_Free
0x180171b9d  mov     rcx, [rbx+20h]
0x180171ba1  mov     qword ptr [rbx+20h], 0
0x180171ba9  test    rcx, rcx
0x180171bac  jz      short loc_180171BB4
0x180171bae  call    cs:__imp_SRCache_Free
0x180171bb4  mov     rcx, [rbx+18h]
0x180171bb8  mov     qword ptr [rbx+18h], 0
0x180171bc0  test    rcx, rcx
0x180171bc3  jz      short loc_180171BCB
0x180171bc5  call    cs:__imp_SRCache_Free
0x180171bcb  mov     rcx, [rbx+8]
0x180171bcf  mov     qword ptr [rbx+8], 0
0x180171bd7  test    rcx, rcx
0x180171bda  jz      short loc_180171BE2
0x180171bdc  call    cs:__imp_SRCache_Free
0x180171be2  add     rsp, 20h
0x180171be6  pop     rbx
0x180171be7  retn
```
