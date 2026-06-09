# wil::com_ptr_t<ICbsSession7,wil::err_returncode_policy>::~com_ptr_t<ICbsSession7,wil::err_returncode_policy>(void)

- ea: `0x18000689c`
- end: `0x1800068ba`
- name: `??1?$com_ptr_t@UICbsSession7@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b855`
- `0x18000b8cf`
- `0x18000b8f3`
- `0x18000b97b`
- `0x18000b9e3`

## callees

- `0x18000689c`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<ICbsSession7,wil::err_returncode_policy>::~com_ptr_t<ICbsSession7,wil::err_returncode_policy>(
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
0x18000689c  sub     rsp, 28h
0x1800068a0  mov     rcx, [rcx]
0x1800068a3  test    rcx, rcx
0x1800068a6  jz      short loc_1800068B5
0x1800068a8  mov     rax, [rcx]
0x1800068ab  mov     rax, [rax+10h]
0x1800068af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068b4  nop
0x1800068b5  add     rsp, 28h
0x1800068b9  retn
```
