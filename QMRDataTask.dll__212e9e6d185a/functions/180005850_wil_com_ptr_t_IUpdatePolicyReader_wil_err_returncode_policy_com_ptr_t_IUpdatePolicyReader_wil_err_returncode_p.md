# wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>(void)

- ea: `0x180005850`
- end: `0x18000586e`
- name: `??1?$com_ptr_t@UIUpdatePolicyReader@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800148a4`

## callees

- `0x180005850`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>(
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
0x180005850  sub     rsp, 28h
0x180005854  mov     rcx, [rcx]
0x180005857  test    rcx, rcx
0x18000585a  jz      short loc_180005869
0x18000585c  mov     rax, [rcx]
0x18000585f  mov     rax, [rax+10h]
0x180005863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005868  nop
0x180005869  add     rsp, 28h
0x18000586d  retn
```
