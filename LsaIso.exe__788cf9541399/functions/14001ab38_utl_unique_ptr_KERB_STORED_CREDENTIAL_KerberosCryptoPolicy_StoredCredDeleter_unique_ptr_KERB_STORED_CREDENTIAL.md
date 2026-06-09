# utl::unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>::~unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>(void)

- ea: `0x14001ab38`
- end: `0x14001ab57`
- name: `??1?$unique_ptr@U_KERB_STORED_CREDENTIAL@@UStoredCredDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001ab7c`

## callees

- `0x140006720`
- `0x14001ab38`

## pseudocode

```c
void __fastcall utl::unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>::~unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 8);
  if ( v2 )
  {
    if ( *(_BYTE *)a1 )
      SafeAllocaFreeToHeap(v2);
  }
}

```

## disassembly

```asm
0x14001ab38  sub     rsp, 28h
0x14001ab3c  mov     rax, rcx
0x14001ab3f  mov     rcx, [rcx+8]; void *
0x14001ab43  test    rcx, rcx
0x14001ab46  jz      short loc_14001AB52
0x14001ab48  cmp     byte ptr [rax], 0
0x14001ab4b  jz      short loc_14001AB52
0x14001ab4d  call    SafeAllocaFreeToHeap
0x14001ab52  add     rsp, 28h
0x14001ab56  retn
```
