# wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::~com_ptr_t<IAccPropServices,wil::err_returncode_policy>(void)

- ea: `0x180007358`
- end: `0x180007375`
- name: `??1?$com_ptr_t@UIAccPropServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800073c8`
- `0x180008100`

## callees

- `0x180007358`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::~com_ptr_t<IAccPropServices,wil::err_returncode_policy>(
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
0x180007358  sub     rsp, 28h
0x18000735c  mov     rcx, [rcx]
0x18000735f  test    rcx, rcx
0x180007362  jz      short loc_180007370
0x180007364  mov     rax, [rcx]
0x180007367  mov     rax, [rax+10h]
0x18000736b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007370  add     rsp, 28h
0x180007374  retn
```
