# wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)

- ea: `0x18000eb00`
- end: `0x18000eb1e`
- name: `??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `25`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e674`
- `0x180011a60`
- `0x180011c30`
- `0x18001317c`
- `0x1800131a8`
- `0x180014a48`
- `0x180016834`
- `0x180017b74`
- `0x18001818c`
- `0x1800185bc`
- `0x1800329e0`
- `0x180032a10`
- `0x180032b00`
- `0x180032c90`
- `0x180032ec0`
- `0x180034180`
- `0x1800346e4`
- `0x180035760`
- `0x18003c328`
- `0x18003c3c3`
- `0x18003c40b`
- `0x18003de43`
- `0x18003ded4`
- `0x18003dfa9`
- `0x18003e16c`

## callees

- `0x18000eb00`
- `0x18003f010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(
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
0x18000eb00  sub     rsp, 28h
0x18000eb04  mov     rcx, [rcx]
0x18000eb07  test    rcx, rcx
0x18000eb0a  jz      short loc_18000EB18
0x18000eb0c  mov     rax, [rcx]
0x18000eb0f  mov     rax, [rax+10h]
0x18000eb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb18  add     rsp, 28h
0x18000eb1c  retn
```
