# StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)

- ea: `0x18002731c`
- end: `0x180027360`
- name: `??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PackageFamily_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180033538`

## callees

- `0x18002731c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180027333`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002734d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180027333`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002734d`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(
        StateRepository::Cache::Entity::PackageFamily_NoThrow *this,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx

  v3 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  if ( v3 )
    SRCache_Free(v3, a2);
  v4 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v4 )
    SRCache_Free(v4, a2);
}

```

## disassembly

```asm
0x18002731c  push    rbx
0x18002731e  sub     rsp, 20h
0x180027322  mov     rbx, rcx
0x180027325  mov     rcx, [rcx+60h]
0x180027329  and     qword ptr [rbx+60h], 0
0x18002732e  test    rcx, rcx
0x180027331  jz      short loc_18002733F
0x180027333  call    cs:__imp_SRCache_Free
0x18002733a  nop     dword ptr [rax+rax+00h]
0x18002733f  mov     rcx, [rbx+8]
0x180027343  and     qword ptr [rbx+8], 0
0x180027348  test    rcx, rcx
0x18002734b  jz      short loc_180027359
0x18002734d  call    cs:__imp_SRCache_Free
0x180027354  nop     dword ptr [rax+rax+00h]
0x180027359  add     rsp, 20h
0x18002735d  pop     rbx
0x18002735e  retn
```
