# utl::unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>::~unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>(void)

- ea: `0x18000d514`
- end: `0x18000d533`
- name: `??1?$unique_ptr@U_KERB_STORED_CREDENTIAL@@UStoredCredDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800060d0`

## callees

- `0x180007e10`
- `0x18000d514`

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
      MIDL_user_free(v2);
  }
}

```

## disassembly

```asm
0x18000d514  sub     rsp, 28h
0x18000d518  mov     rax, rcx
0x18000d51b  mov     rcx, [rcx+8]; void *
0x18000d51f  test    rcx, rcx
0x18000d522  jz      short loc_18000D52E
0x18000d524  cmp     byte ptr [rax], 0
0x18000d527  jz      short loc_18000D52E
0x18000d529  call    MIDL_user_free
0x18000d52e  add     rsp, 28h
0x18000d532  retn
```
