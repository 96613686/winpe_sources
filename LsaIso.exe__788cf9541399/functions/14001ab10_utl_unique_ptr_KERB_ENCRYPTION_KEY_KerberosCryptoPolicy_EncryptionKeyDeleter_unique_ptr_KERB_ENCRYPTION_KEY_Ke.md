# utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(void)

- ea: `0x14001ab10`
- end: `0x14001ab2f`
- name: `??1?$unique_ptr@U_KERB_ENCRYPTION_KEY@@UEncryptionKeyDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001ab7c`
- `0x14001ea54`

## callees

- `0x14001ab10`
- `0x14001de00`

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
0x14001ab10  sub     rsp, 28h
0x14001ab14  mov     rax, rcx
0x14001ab17  mov     rcx, [rcx+8]
0x14001ab1b  test    rcx, rcx
0x14001ab1e  jz      short loc_14001AB2A
0x14001ab20  cmp     byte ptr [rax], 0
0x14001ab23  jz      short loc_14001AB2A
0x14001ab25  call    KerbFreeKey
0x14001ab2a  add     rsp, 28h
0x14001ab2e  retn
```
