# wil::com_ptr_t<ipx::mtf::IMtfTransportServerPrivate,wil::err_exception_policy>::~com_ptr_t<ipx::mtf::IMtfTransportServerPrivate,wil::err_exception_policy>(void)

- ea: `0x1800143d0`
- end: `0x1800143ee`
- name: `??1?$com_ptr_t@UIMtfTransportServerPrivate@mtf@ipx@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d533`
- `0x18002d545`
- `0x18002de50`
- `0x18002de62`
- `0x18002de74`

## callees

- `0x1800143d0`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<ipx::mtf::IMtfTransportServerPrivate,wil::err_exception_policy>::~com_ptr_t<ipx::mtf::IMtfTransportServerPrivate,wil::err_exception_policy>(
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
0x1800143d0  sub     rsp, 28h
0x1800143d4  mov     rcx, [rcx]
0x1800143d7  test    rcx, rcx
0x1800143da  jz      short loc_1800143E9
0x1800143dc  mov     rax, [rcx]
0x1800143df  mov     rax, [rax+10h]
0x1800143e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143e8  nop
0x1800143e9  add     rsp, 28h
0x1800143ed  retn
```
