# Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::`scalar deleting destructor'(uint)

- ea: `0x18001ecc0`
- end: `0x18001ed12`
- name: `??_GThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@UEAAPEAXI@Z`
- size: `82`
- prototype: `Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *__fastcall(Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001b60`
- `0x18001ecc0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001ecd8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001ecd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *__fastcall Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::`scalar deleting destructor'(
        Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *this,
        char a2)
{
  struct _TP_CLEANUP_GROUP *v4; // rcx
  void *v5; // rcx

  v4 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 2);
  if ( v4 )
    CloseThreadpoolCleanupGroup(v4);
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
    operator delete(v5, (const struct std::nothrow_t *)0x48);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x18);
  return this;
}

```

## disassembly

```asm
0x18001ecc0  mov     [rsp+arg_0], rbx
0x18001ecc5  push    rdi
0x18001ecc6  sub     rsp, 20h
0x18001ecca  mov     rbx, rcx
0x18001eccd  mov     edi, edx
0x18001eccf  mov     rcx, [rcx+10h]; ptpcg
0x18001ecd3  test    rcx, rcx
0x18001ecd6  jz      short loc_18001ECDE
0x18001ecd8  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001ecde  mov     rcx, [rbx+8]; void *
0x18001ece2  test    rcx, rcx
0x18001ece5  jz      short loc_18001ECF1
0x18001ece7  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x18001ecec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ecf1  test    dil, 1
0x18001ecf5  jz      short loc_18001ED04
0x18001ecf7  mov     edx, 18h; struct std::nothrow_t *
0x18001ecfc  mov     rcx, rbx; void *
0x18001ecff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ed04  mov     rax, rbx
0x18001ed07  mov     rbx, [rsp+28h+arg_0]
0x18001ed0c  add     rsp, 20h
0x18001ed10  pop     rdi
0x18001ed11  retn
```
