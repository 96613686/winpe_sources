# wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>::~cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>(void)

- ea: `0x18001b118`
- end: `0x18001b121`
- name: `??1?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@QEAA@XZ`
- size: `9`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ed12`
- `0x18002f1f7`
- `0x18002f2b5`
- `0x18002f48f`
- `0x18002f4d7`
- `0x18002f79c`

## callees

- `0x18001b128`

## pseudocode

```c
__int64 __fastcall wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>::~cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>(
        __int64 a1)
{
  return wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>((__int64 *)(a1 + 32));
}

```

## disassembly

```asm
0x18001b118  add     rcx, 20h ; ' '
0x18001b11c  jmp     ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
```
