# CModelDownloadComponent::~CModelDownloadComponent(void)

- ea: `0x14000b274`
- end: `0x14000b2e3`
- name: `??1CModelDownloadComponent@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(CModelDownloadComponent *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009698`

## callees

- `0x14000b274`
- `0x14000cc9c`
- `0x14001d010`

## pseudocode

```c
void __fastcall CModelDownloadComponent::~CModelDownloadComponent(CModelDownloadComponent *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  CModelDownloadComponent::CleanupFilesList(this);
  v2 = *((_QWORD *)this + 3073);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *(_QWORD *)this )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
}

```

## disassembly

```asm
0x14000b274  push    rbx
0x14000b276  sub     rsp, 20h
0x14000b27a  mov     rbx, rcx
0x14000b27d  call    ?CleanupFilesList@CModelDownloadComponent@@AEAAXXZ; CModelDownloadComponent::CleanupFilesList(void)
0x14000b282  nop
0x14000b283  mov     rcx, [rbx+6008h]
0x14000b28a  test    rcx, rcx
0x14000b28d  jz      short loc_14000B29C
0x14000b28f  mov     rax, [rcx]
0x14000b292  mov     rax, [rax+10h]
0x14000b296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b29b  nop
0x14000b29c  mov     rcx, [rbx+10h]
0x14000b2a0  test    rcx, rcx
0x14000b2a3  jz      short loc_14000B2B2
0x14000b2a5  mov     rax, [rcx]
0x14000b2a8  mov     rax, [rax+10h]
0x14000b2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2b1  nop
0x14000b2b2  mov     rcx, [rbx+8]
0x14000b2b6  test    rcx, rcx
0x14000b2b9  jz      short loc_14000B2C8
0x14000b2bb  mov     rax, [rcx]
0x14000b2be  mov     rax, [rax+10h]
0x14000b2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2c7  nop
0x14000b2c8  mov     rcx, [rbx]
0x14000b2cb  test    rcx, rcx
0x14000b2ce  jz      short loc_14000B2DD
0x14000b2d0  mov     rax, [rcx]
0x14000b2d3  mov     rax, [rax+10h]
0x14000b2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2dc  nop
0x14000b2dd  add     rsp, 20h
0x14000b2e1  pop     rbx
0x14000b2e2  retn
```
