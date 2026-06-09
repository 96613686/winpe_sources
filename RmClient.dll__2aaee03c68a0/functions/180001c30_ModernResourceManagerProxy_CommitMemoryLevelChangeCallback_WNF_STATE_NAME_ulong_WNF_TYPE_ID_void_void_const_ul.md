# ModernResourceManagerProxy::CommitMemoryLevelChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180001c30`
- end: `0x180001c86`
- name: `?CommitMemoryLevelChangeCallback@ModernResourceManagerProxy@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `86`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, __int64, struct _WNF_TYPE_ID *, _QWORD *, const void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c30`
- `0x180001d14`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001c6c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001c6c`

## pseudocode

```c
__int64 __fastcall ModernResourceManagerProxy::CommitMemoryLevelChangeCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        _QWORD *a4,
        const void *a5)
{
  char *v7; // rbx
  void (__fastcall *v8)(const void *); // rdi

  if ( a5 )
  {
    v7 = (char *)(a4 + 12);
    CempLockAcquireExclusive(a4 + 12, a2, a3);
    v8 = (void (__fastcall *)(const void *))a4[3];
    *((_DWORD *)v7 + 2) = 0;
    RtlReleaseSRWLockExclusive(v7);
    if ( v8 )
      v8(a5);
  }
  return 0;
}

```

## disassembly

```asm
0x180001c30  mov     [rsp+arg_0], rbx
0x180001c35  push    rdi
0x180001c36  sub     rsp, 20h
0x180001c3a  cmp     [rsp+28h+arg_20], 0
0x180001c40  mov     rdi, r9
0x180001c43  jnz     short loc_180001C52
0x180001c45  mov     rbx, [rsp+28h+arg_0]
0x180001c4a  xor     eax, eax
0x180001c4c  add     rsp, 20h
0x180001c50  pop     rdi
0x180001c51  retn
0x180001c52  lea     rbx, [r9+60h]
0x180001c56  mov     rcx, rbx
0x180001c59  call    CempLockAcquireExclusive
0x180001c5e  mov     rdi, [rdi+18h]
0x180001c62  mov     rcx, rbx
0x180001c65  mov     dword ptr [rbx+8], 0
0x180001c6c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001c72  test    rdi, rdi
0x180001c75  jz      short loc_180001C45
0x180001c77  mov     rcx, [rsp+28h+arg_20]
0x180001c7c  mov     rax, rdi
0x180001c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c84  jmp     short loc_180001C45
```
