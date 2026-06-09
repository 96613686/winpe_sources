# wil::com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>(void)

- ea: `0x1400082e4`
- end: `0x140008302`
- name: `??1?$com_ptr_t@UITpmVirtualSmartCardManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011cd7`
- `0x140011ce9`
- `0x140011cfb`
- `0x140011d43`
- `0x140011d55`
- `0x140011d79`

## callees

- `0x1400082e4`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>(
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
0x1400082e4  sub     rsp, 28h
0x1400082e8  mov     rcx, [rcx]
0x1400082eb  test    rcx, rcx
0x1400082ee  jz      short loc_1400082FD
0x1400082f0  mov     rax, [rcx]
0x1400082f3  mov     rax, [rax+10h]
0x1400082f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400082fc  nop
0x1400082fd  add     rsp, 28h
0x140008301  retn
```
