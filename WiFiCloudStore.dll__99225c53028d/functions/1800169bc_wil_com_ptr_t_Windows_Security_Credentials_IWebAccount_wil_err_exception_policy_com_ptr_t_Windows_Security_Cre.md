# wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)

- ea: `0x1800169bc`
- end: `0x1800169da`
- name: `??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `27`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012594`
- `0x1800144c0`
- `0x180015624`
- `0x180016ba4`
- `0x1800190ac`
- `0x18001bce8`
- `0x18002547c`
- `0x180025df4`
- `0x18002607c`
- `0x18002c160`
- `0x18002c5c0`
- `0x18002d124`
- `0x18003d9a0`
- `0x18003d9e0`
- `0x18003dc80`
- `0x18003e3b7`
- `0x18003e4f0`
- `0x18003ec26`
- `0x18003ec3c`
- `0x18003f70d`
- `0x18003f739`
- `0x18003f74b`
- `0x18003fa8d`
- `0x18003fb25`
- `0x18003fd1f`
- `0x18004012e`
- `0x180040140`

## callees

- `0x1800169bc`
- `0x180041010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800169bc  sub     rsp, 28h
0x1800169c0  mov     rcx, [rcx]
0x1800169c3  test    rcx, rcx
0x1800169c6  jz      short loc_1800169D5
0x1800169c8  mov     rax, [rcx]
0x1800169cb  mov     rax, [rax+10h]
0x1800169cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169d4  nop
0x1800169d5  add     rsp, 28h
0x1800169d9  retn
```
