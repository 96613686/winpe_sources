# utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)

- ea: `0x1800060d0`
- end: `0x18000612c`
- name: `??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ`
- size: `92`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `21`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800060d0`
- `0x180009c50`
- `0x180009d60`
- `0x180009fa0`
- `0x18000a1b0`
- `0x18000a3d0`
- `0x18000a650`
- `0x18000a920`
- `0x18000aed0`
- `0x18000b5b0`
- `0x18000b790`
- `0x18000bc8c`
- `0x18000bcf4`
- `0x18000c00c`
- `0x18000c074`
- `0x18000c2d0`
- `0x18000c498`
- `0x18000c8c0`
- `0x18000cf30`
- `0x180015010`
- `0x180016190`

## callees

- `0x1800060d0`
- `0x180006140`
- `0x18000d514`
- `0x18000d53c`
- `0x18000ef40`

## pseudocode

```c
HLOCAL __fastcall utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  HLOCAL result; // rax

  v1 = *a1;
  if ( *a1 )
  {
    utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(v1 + 104);
    utl::unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>::~unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>(v1 + 88);
    utl::unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>::~unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>(v1 + 64);
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v1 + 48);
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)(v1 + 32));
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)(v1 + 16));
    return operator delete((HLOCAL)v1);
  }
  return result;
}

```

## disassembly

```asm
0x1800060d0  push    rbx
0x1800060d2  sub     rsp, 20h
0x1800060d6  mov     rbx, [rcx]
0x1800060d9  test    rbx, rbx
0x1800060dc  jz      short loc_180006126
0x1800060de  lea     rcx, [rbx+68h]
0x1800060e2  call    ??1?$unique_ptr@U_KERB_ENCRYPTION_KEY@@UEncryptionKeyDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ; utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(void)
0x1800060e7  lea     rcx, [rbx+58h]
0x1800060eb  call    ??1?$unique_ptr@U_KERB_STORED_CREDENTIAL@@UStoredCredDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ; utl::unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>::~unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>(void)
0x1800060f0  lea     rcx, [rbx+40h]
0x1800060f4  call    ??1?$unique_ptr@U_KERB_STORED_CREDENTIAL@@UStoredCredDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ; utl::unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>::~unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>(void)
0x1800060f9  lea     rcx, [rbx+30h]
0x1800060fd  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180006102  lea     rcx, [rbx+20h]; this
0x180006106  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x18000610b  lea     rcx, [rbx+10h]; this
0x18000610f  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x180006114  mov     edx, 80h
0x180006119  mov     rcx, rbx; hMem
0x18000611c  add     rsp, 20h
0x180006120  pop     rbx
0x180006121  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006126  add     rsp, 20h
0x18000612a  pop     rbx
0x18000612b  retn
```
