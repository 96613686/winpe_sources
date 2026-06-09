# wil::details::functor_wrapper_void__lambda_c16bf91101c9118b5e2e61d840e8728a___::Run

- ea: `0x18000fd20`
- end: `0x18000fdb8`
- name: `wil::details::functor_wrapper_void__lambda_c16bf91101c9118b5e2e61d840e8728a___::Run`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a3e4`

## callees

- `0x18000fd20`
- `0x180010cac`
- `0x180029674`
- `0x180037010`

## string_xrefs

- `0x18000fda6`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\bthserv.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_c16bf91101c9118b5e2e61d840e8728a___::Run(__int64 a1)
{
  _DWORD **v1; // rbx
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *v2; // rcx
  const char *v3; // r9
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *v5; // [rsp+28h] [rbp-20h] BYREF
  char v6; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController **v8; // [rsp+50h] [rbp+8h] BYREF
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController ***v9; // [rsp+58h] [rbp+10h] BYREF

  v1 = *(_DWORD ***)(a1 + 8);
  v5 = 0;
  v8 = &v5;
  v9 = &v8;
  v6 = 1;
  **v1 = wil::ResultFromException__lambda_6a80e4881cb77c2cccaf9dde37a13450___(&v9);
  if ( v6 )
  {
    v2 = qword_180044BA8;
    qword_180044BA8 = v5;
    if ( v2 )
      (**(void (__fastcall ***)(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *, __int64))v2)(
        v2,
        1);
  }
  v3 = (const char *)(unsigned int)**v1;
  if ( (int)v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA7,
      (int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\bthserv.cpp",
      v3,
      (int)&qword_180044BA8);
  return 0;
}

```

## disassembly

```asm
0x18000fd20  mov     r11, rsp
0x18000fd23  push    rbx
0x18000fd24  sub     rsp, 40h
0x18000fd28  mov     rbx, [rcx+8]
0x18000fd2c  lea     rax, qword_180044BA8
0x18000fd33  mov     [r11-28h], rax
0x18000fd37  lea     rcx, [r11+10h]
0x18000fd3b  lea     rax, [r11-20h]
0x18000fd3f  mov     qword ptr [r11-20h], 0
0x18000fd47  mov     [r11+8], rax
0x18000fd4b  lea     rax, [r11+8]
0x18000fd4f  mov     [r11+10h], rax
0x18000fd53  mov     [rsp+48h+var_18], 1
0x18000fd58  call    wil__ResultFromException__lambda_6a80e4881cb77c2cccaf9dde37a13450___
0x18000fd5d  mov     rcx, [rbx]
0x18000fd60  mov     [rcx], eax
0x18000fd62  cmp     [rsp+48h+var_18], 0
0x18000fd67  jz      short loc_18000FD8E
0x18000fd69  mov     r8, [rsp+48h+var_28]
0x18000fd6e  mov     rax, [rsp+48h+var_20]
0x18000fd73  mov     rcx, [r8]
0x18000fd76  mov     [r8], rax
0x18000fd79  test    rcx, rcx
0x18000fd7c  jz      short loc_18000FD8E
0x18000fd7e  mov     rax, [rcx]
0x18000fd81  mov     edx, 1
0x18000fd86  mov     rax, [rax]
0x18000fd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8e  mov     rax, [rbx]
0x18000fd91  mov     r9d, [rax]; char *
0x18000fd94  test    r9d, r9d
0x18000fd97  js      short loc_18000FDA1
0x18000fd99  xor     eax, eax
0x18000fd9b  add     rsp, 40h
0x18000fd9f  pop     rbx
0x18000fda0  retn
0x18000fda1  mov     rcx, [rsp+48h]; this
0x18000fda6  lea     r8, aOnecoreDrivers_9; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x18000fdad  mov     edx, 0A7h; void *
0x18000fdb2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
