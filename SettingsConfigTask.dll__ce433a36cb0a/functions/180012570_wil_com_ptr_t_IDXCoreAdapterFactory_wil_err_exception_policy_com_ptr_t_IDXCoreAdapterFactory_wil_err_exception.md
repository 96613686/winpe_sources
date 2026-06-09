# wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)

- ea: `0x180012570`
- end: `0x18001258e`
- name: `??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cc8c`
- `0x18000d074`
- `0x1800223a5`
- `0x1800223b7`
- `0x1800223c9`
- `0x18002241c`

## callees

- `0x180012570`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(
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
0x180012570  sub     rsp, 28h
0x180012574  mov     rcx, [rcx]
0x180012577  test    rcx, rcx
0x18001257a  jz      short loc_180012589
0x18001257c  mov     rax, [rcx]
0x18001257f  mov     rax, [rax+10h]
0x180012583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012588  nop
0x180012589  add     rsp, 28h
0x18001258d  retn
```
