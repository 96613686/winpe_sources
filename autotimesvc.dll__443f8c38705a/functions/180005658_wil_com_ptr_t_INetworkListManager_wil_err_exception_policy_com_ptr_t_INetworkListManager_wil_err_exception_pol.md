# wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::~com_ptr_t<INetworkListManager,wil::err_exception_policy>(void)

- ea: `0x180005658`
- end: `0x180005676`
- name: `??1?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800081ac`
- `0x180009bb8`

## callees

- `0x180005658`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::~com_ptr_t<INetworkListManager,wil::err_exception_policy>(
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
0x180005658  sub     rsp, 28h
0x18000565c  mov     rcx, [rcx]
0x18000565f  test    rcx, rcx
0x180005662  jz      short loc_180005671
0x180005664  mov     rax, [rcx]
0x180005667  mov     rax, [rax+10h]
0x18000566b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005670  nop
0x180005671  add     rsp, 28h
0x180005675  retn
```
