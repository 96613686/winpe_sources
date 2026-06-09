# wil::com_ptr_t<CMidi2VirtualMidiEndpointManager,wil::err_exception_policy>::~com_ptr_t<CMidi2VirtualMidiEndpointManager,wil::err_exception_policy>(void)

- ea: `0x18000bfd8`
- end: `0x18000bff6`
- name: `??1?$com_ptr_t@VCMidi2VirtualMidiEndpointManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002055f`
- `0x1800205df`

## callees

- `0x18000bfd8`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<CMidi2VirtualMidiEndpointManager,wil::err_exception_policy>::~com_ptr_t<CMidi2VirtualMidiEndpointManager,wil::err_exception_policy>(
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
0x18000bfd8  sub     rsp, 28h
0x18000bfdc  mov     rcx, [rcx]
0x18000bfdf  test    rcx, rcx
0x18000bfe2  jz      short loc_18000BFF1
0x18000bfe4  mov     rax, [rcx]
0x18000bfe7  mov     rax, [rax+10h]
0x18000bfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bff0  nop
0x18000bff1  add     rsp, 28h
0x18000bff5  retn
```
