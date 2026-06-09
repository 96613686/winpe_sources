# wil::com_ptr_t<IWICBitmapScaler,wil::err_failfast_policy>::~com_ptr_t<IWICBitmapScaler,wil::err_failfast_policy>(void)

- ea: `0x18000ae78`
- end: `0x18000ae96`
- name: `??1?$com_ptr_t@UIWICBitmapScaler@@Uerr_failfast_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e73d`
- `0x18000e74f`
- `0x18000e761`
- `0x18000e773`
- `0x18000e785`
- `0x18000e797`
- `0x18000e7a9`
- `0x18000e7bb`
- `0x18000e7cd`
- `0x18000e7df`
- `0x18000e7f1`
- `0x18000e803`
- `0x18000e815`
- `0x18000e827`

## callees

- `0x18000ae78`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IWICBitmapScaler,wil::err_failfast_policy>::~com_ptr_t<IWICBitmapScaler,wil::err_failfast_policy>(
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
0x18000ae78  sub     rsp, 28h
0x18000ae7c  mov     rcx, [rcx]
0x18000ae7f  test    rcx, rcx
0x18000ae82  jz      short loc_18000AE91
0x18000ae84  mov     rax, [rcx]
0x18000ae87  mov     rax, [rax+10h]
0x18000ae8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae90  nop
0x18000ae91  add     rsp, 28h
0x18000ae95  retn
```
