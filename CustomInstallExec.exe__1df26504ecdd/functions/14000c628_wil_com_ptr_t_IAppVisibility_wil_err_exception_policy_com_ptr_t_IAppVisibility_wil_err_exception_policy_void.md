# wil::com_ptr_t<IAppVisibility,wil::err_exception_policy>::~com_ptr_t<IAppVisibility,wil::err_exception_policy>(void)

- ea: `0x14000c628`
- end: `0x14000c646`
- name: `??1?$com_ptr_t@UIAppVisibility@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c9f4`
- `0x14000edd6`
- `0x14000ee02`

## callees

- `0x14000c628`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IAppVisibility,wil::err_exception_policy>::~com_ptr_t<IAppVisibility,wil::err_exception_policy>(
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
0x14000c628  sub     rsp, 28h
0x14000c62c  mov     rcx, [rcx]
0x14000c62f  test    rcx, rcx
0x14000c632  jz      short loc_14000C641
0x14000c634  mov     rax, [rcx]
0x14000c637  mov     rax, [rax+10h]
0x14000c63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c640  nop
0x14000c641  add     rsp, 28h
0x14000c645  retn
```
