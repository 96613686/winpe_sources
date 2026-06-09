# wil::com_ptr_t<CMidi2LoopbackMidiConfigurationManager,wil::err_exception_policy>::~com_ptr_t<CMidi2LoopbackMidiConfigurationManager,wil::err_exception_policy>(void)

- ea: `0x18000b7ac`
- end: `0x18000b7ca`
- name: `??1?$com_ptr_t@VCMidi2LoopbackMidiConfigurationManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003042e`
- `0x180030440`
- `0x180031270`
- `0x1800312a2`
- `0x180031367`

## callees

- `0x18000b7ac`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<CMidi2LoopbackMidiConfigurationManager,wil::err_exception_policy>::~com_ptr_t<CMidi2LoopbackMidiConfigurationManager,wil::err_exception_policy>(
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
0x18000b7ac  sub     rsp, 28h
0x18000b7b0  mov     rcx, [rcx]
0x18000b7b3  test    rcx, rcx
0x18000b7b6  jz      short loc_18000B7C5
0x18000b7b8  mov     rax, [rcx]
0x18000b7bb  mov     rax, [rax+10h]
0x18000b7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7c4  nop
0x18000b7c5  add     rsp, 28h
0x18000b7c9  retn
```
