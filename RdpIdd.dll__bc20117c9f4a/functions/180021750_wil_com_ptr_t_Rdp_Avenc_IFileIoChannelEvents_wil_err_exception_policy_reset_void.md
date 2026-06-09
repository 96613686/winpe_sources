# wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(void)

- ea: `0x180021750`
- end: `0x180021779`
- name: `?reset@?$com_ptr_t@UIFileIoChannelEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ`
- size: `41`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014f74`
- `0x18001818c`
- `0x18001b1a0`
- `0x18001d938`
- `0x180023a90`
- `0x180023b6c`
- `0x180027168`
- `0x180030a28`
- `0x1800353a0`

## callees

- `0x180021750`
- `0x18003f010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180021750  sub     rsp, 28h
0x180021754  mov     rdx, [rcx]
0x180021757  mov     qword ptr [rcx], 0
0x18002175e  test    rdx, rdx
0x180021761  jz      short loc_180021773
0x180021763  mov     rax, [rdx]
0x180021766  mov     rcx, rdx
0x180021769  mov     rax, [rax+10h]
0x18002176d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021772  nop
0x180021773  add     rsp, 28h
0x180021777  retn
```
