# utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(void)

- ea: `0x18000d53c`
- end: `0x18000d55b`
- name: `??1?$unique_ptr@U_KERB_ENCRYPTION_KEY@@UEncryptionKeyDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800060d0`

## callees

- `0x180007960`
- `0x18000d53c`

## pseudocode

```c
_BYTE *__fastcall utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(
        __int64 a1)
{
  _BYTE *result; // rax
  __int64 v2; // rcx

  result = (_BYTE *)a1;
  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    if ( *result )
      return (_BYTE *)KerbFreeKey(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18000d53c  sub     rsp, 28h
0x18000d540  mov     rax, rcx
0x18000d543  mov     rcx, [rcx+8]
0x18000d547  test    rcx, rcx
0x18000d54a  jz      short loc_18000D556
0x18000d54c  cmp     byte ptr [rax], 0
0x18000d54f  jz      short loc_18000D556
0x18000d551  call    KerbFreeKey
0x18000d556  add     rsp, 28h
0x18000d55a  retn
```
