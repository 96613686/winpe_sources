# Streaming::Context::StreamingBitMap::~StreamingBitMap(void)

- ea: `0x14000f770`
- end: `0x14000f7c3`
- name: `??1StreamingBitMap@Context@Streaming@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(Streaming::Context::StreamingBitMap *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400086a8`
- `0x14000b6d0`
- `0x14000f7cc`

## callees

- `0x14000f770`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14000f782`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000f782`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f799`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f7b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f799`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f7b0`

## pseudocode

```c
void __fastcall Streaming::Context::StreamingBitMap::~StreamingBitMap(Streaming::Context::StreamingBitMap *this)
{
  struct _ERESOURCE *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = (struct _ERESOURCE *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    ExDeleteResourceLite(v2);
    v3 = (void *)*((_QWORD *)this + 6);
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
}

```

## disassembly

```asm
0x14000f770  push    rbx
0x14000f772  sub     rsp, 20h
0x14000f776  mov     rbx, rcx
0x14000f779  mov     rcx, [rcx+30h]; Resource
0x14000f77d  test    rcx, rcx
0x14000f780  jz      short loc_14000F7A5
0x14000f782  call    cs:__imp_ExDeleteResourceLite
0x14000f789  nop     dword ptr [rax+rax+00h]
0x14000f78e  mov     rcx, [rbx+30h]; P
0x14000f792  test    rcx, rcx
0x14000f795  jz      short loc_14000F7A5
0x14000f797  xor     edx, edx; Tag
0x14000f799  call    cs:__imp_ExFreePoolWithTag
0x14000f7a0  nop     dword ptr [rax+rax+00h]
0x14000f7a5  mov     rcx, [rbx+18h]; P
0x14000f7a9  test    rcx, rcx
0x14000f7ac  jz      short loc_14000F7BC
0x14000f7ae  xor     edx, edx; Tag
0x14000f7b0  call    cs:__imp_ExFreePoolWithTag
0x14000f7b7  nop     dword ptr [rax+rax+00h]
0x14000f7bc  add     rsp, 20h
0x14000f7c0  pop     rbx
0x14000f7c1  retn
```
