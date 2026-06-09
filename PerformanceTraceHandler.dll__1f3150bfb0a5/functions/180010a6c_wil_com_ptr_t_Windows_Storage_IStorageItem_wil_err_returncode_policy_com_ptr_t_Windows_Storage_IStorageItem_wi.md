# wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)

- ea: `0x180010a6c`
- end: `0x180010a8a`
- name: `??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800118d4`
- `0x180012334`
- `0x1800161f8`
- `0x18001ae0e`
- `0x18001ae20`
- `0x18001affd`
- `0x18001b00f`
- `0x18001b033`
- `0x18001b045`

## callees

- `0x180010a6c`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(
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
0x180010a6c  sub     rsp, 28h
0x180010a70  mov     rcx, [rcx]
0x180010a73  test    rcx, rcx
0x180010a76  jz      short loc_180010A85
0x180010a78  mov     rax, [rcx]
0x180010a7b  mov     rax, [rax+10h]
0x180010a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a84  nop
0x180010a85  add     rsp, 28h
0x180010a89  retn
```
