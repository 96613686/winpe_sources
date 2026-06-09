# wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)

- ea: `0x18001b128`
- end: `0x18001b146`
- name: `??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `62`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800127ac`
- `0x180012abc`
- `0x180012ca4`
- `0x180012e8c`
- `0x180013074`
- `0x18001325c`
- `0x180013454`
- `0x18001363c`
- `0x180013824`
- `0x180013aa4`
- `0x180013d24`
- `0x180013fa4`
- `0x180014224`
- `0x1800144b8`
- `0x180014738`
- `0x1800149b8`
- `0x1800181fc`
- `0x1800184c0`
- `0x180018778`
- `0x180018a50`
- `0x180018d24`
- `0x180018f98`
- `0x180019250`
- `0x18001ae98`
- `0x18001b108`
- `0x18001b118`
- `0x18001b5a0`
- `0x18001b8a0`
- `0x18001d208`
- `0x18001ee60`
- `0x18001f1f0`
- `0x180021510`
- `0x1800215f0`
- `0x1800216d0`
- `0x1800217f0`
- `0x1800218c0`
- `0x180021a60`
- `0x180021b40`
- `0x180021c50`
- `0x180022280`
- `0x180022e18`
- `0x180024000`
- `0x180026db4`
- `0x1800282c0`
- `0x18002eace`
- `0x18002ec1c`
- `0x18002edf5`
- `0x18002ee0b`
- `0x18002ee9f`
- `0x18002ef2f`

## callees

- `0x18001b128`
- `0x180031010`

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
0x18001b128  sub     rsp, 28h
0x18001b12c  mov     rcx, [rcx]
0x18001b12f  test    rcx, rcx
0x18001b132  jz      short loc_18001B141
0x18001b134  mov     rax, [rcx]
0x18001b137  mov     rax, [rax+10h]
0x18001b13b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b140  nop
0x18001b141  add     rsp, 28h
0x18001b145  retn
```
