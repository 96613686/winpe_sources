# wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(void)

- ea: `0x14000a04c`
- end: `0x14000a06a`
- name: `??1?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `16`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400083ac`
- `0x140008450`
- `0x14000b114`
- `0x14000c33c`
- `0x14000c3ec`
- `0x14000c848`
- `0x14000ed9c`
- `0x140011318`
- `0x14001133c`
- `0x14001159c`
- `0x1400115ae`
- `0x1400116aa`
- `0x14001195d`
- `0x14001196f`
- `0x140011b7b`
- `0x140011b8d`

## callees

- `0x14000a04c`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(
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
0x14000a04c  sub     rsp, 28h
0x14000a050  mov     rcx, [rcx]
0x14000a053  test    rcx, rcx
0x14000a056  jz      short loc_14000A065
0x14000a058  mov     rax, [rcx]
0x14000a05b  mov     rax, [rax+10h]
0x14000a05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a064  nop
0x14000a065  add     rsp, 28h
0x14000a069  retn
```
