# StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)

- ea: `0x18002895c`
- end: `0x1800289a0`
- name: `??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PackageFamily_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800334c8`

## callees

- `0x18002895c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180028973`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002898d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180028973`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002898d`

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
0x18002895c  push    rbx
0x18002895e  sub     rsp, 20h
0x180028962  mov     rbx, rcx
0x180028965  mov     rcx, [rcx+60h]
0x180028969  and     qword ptr [rbx+60h], 0
0x18002896e  test    rcx, rcx
0x180028971  jz      short loc_18002897F
0x180028973  call    cs:__imp_SRCache_Free
0x18002897a  nop     dword ptr [rax+rax+00h]
0x18002897f  mov     rcx, [rbx+8]
0x180028983  and     qword ptr [rbx+8], 0
0x180028988  test    rcx, rcx
0x18002898b  jz      short loc_180028999
0x18002898d  call    cs:__imp_SRCache_Free
0x180028994  nop     dword ptr [rax+rax+00h]
0x180028999  add     rsp, 20h
0x18002899d  pop     rbx
0x18002899e  retn
```
