# wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)

- ea: `0x18001106c`
- end: `0x18001108a`
- name: `??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `24`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d9e8`
- `0x18000df9c`
- `0x18000e24c`
- `0x18000ef9c`
- `0x180011044`
- `0x180011618`
- `0x180012038`
- `0x180012b50`
- `0x180014160`
- `0x18001e11c`
- `0x18001e580`
- `0x18002307d`
- `0x180023093`
- `0x18002322b`
- `0x180023508`
- `0x180023574`
- `0x1800235a0`
- `0x1800235b2`
- `0x1800237ad`
- `0x1800237d1`
- `0x180023c61`
- `0x180023c73`
- `0x18002423b`
- `0x180024377`

## callees

- `0x18001106c`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18001106c  sub     rsp, 28h
0x180011070  mov     rcx, [rcx]
0x180011073  test    rcx, rcx
0x180011076  jz      short loc_180011085
0x180011078  mov     rax, [rcx]
0x18001107b  mov     rax, [rax+10h]
0x18001107f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011084  nop
0x180011085  add     rsp, 28h
0x180011089  retn
```
