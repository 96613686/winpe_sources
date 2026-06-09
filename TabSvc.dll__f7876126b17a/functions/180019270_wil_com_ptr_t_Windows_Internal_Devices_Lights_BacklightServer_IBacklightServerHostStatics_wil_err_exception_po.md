# wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>(void)

- ea: `0x180019270`
- end: `0x18001928e`
- name: `??1?$com_ptr_t@UIBacklightServerHostStatics@BacklightServer@Lights@Devices@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800191b4`
- `0x1800194b0`
- `0x18002feec`
- `0x18003004c`

## callees

- `0x180019270`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>(
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
0x180019270  sub     rsp, 28h
0x180019274  mov     rcx, [rcx]
0x180019277  test    rcx, rcx
0x18001927a  jz      short loc_180019289
0x18001927c  mov     rax, [rcx]
0x18001927f  mov     rax, [rax+10h]
0x180019283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019288  nop
0x180019289  add     rsp, 28h
0x18001928d  retn
```
