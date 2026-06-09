# wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)

- ea: `0x140005cac`
- end: `0x140005cca`
- name: `??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `30`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005ec8`
- `0x140006150`
- `0x140007ad8`
- `0x14000b0cc`
- `0x14000fa90`
- `0x1400100e0`
- `0x140010ac0`
- `0x140010ce8`
- `0x140011674`
- `0x1400120b0`
- `0x14001225c`
- `0x1400122f8`
- `0x14001376c`
- `0x140013d10`
- `0x140018ba3`
- `0x140018bc7`
- `0x140018bfd`
- `0x140018c21`
- `0x140018c8d`
- `0x140018cd5`
- `0x140018d1d`
- `0x140018d2f`
- `0x140018d65`
- `0x140018dfd`
- `0x140018e57`
- `0x140018e69`
- `0x140018f1c`
- `0x140018f2e`
- `0x140018f40`
- `0x140018f64`

## callees

- `0x140005cac`
- `0x14001a010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(
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
0x140005cac  sub     rsp, 28h
0x140005cb0  mov     rcx, [rcx]
0x140005cb3  test    rcx, rcx
0x140005cb6  jz      short loc_140005CC5
0x140005cb8  mov     rax, [rcx]
0x140005cbb  mov     rax, [rax+10h]
0x140005cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cc4  nop
0x140005cc5  add     rsp, 28h
0x140005cc9  retn
```
