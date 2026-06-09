# wil::com_ptr_t<IActivationFactory,wil::err_returncode_policy>::~com_ptr_t<IActivationFactory,wil::err_returncode_policy>(void)

- ea: `0x140006b10`
- end: `0x140006b25`
- name: `??1?$com_ptr_t@UIActivationFactory@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002260`

## callees

- `0x140006b10`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IActivationFactory,wil::err_returncode_policy>::~com_ptr_t<IActivationFactory,wil::err_returncode_policy>(
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
0x140006b10  mov     rcx, [rcx]
0x140006b13  test    rcx, rcx
0x140006b16  jz      short locret_140006B24
0x140006b18  mov     rax, [rcx]
0x140006b1b  mov     rax, [rax+10h]
0x140006b1f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140006b24  retn
```
