# wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(Windows::Internal::Storage::Cloud::ICloudStoreData *)

- ea: `0x18001ba2c`
- end: `0x18001ba75`
- name: `??4?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800181fc`
- `0x1800184c0`
- `0x180018778`
- `0x180018a50`
- `0x180018d24`
- `0x180018f98`
- `0x180019250`

## callees

- `0x18001ba2c`
- `0x180031010`

## pseudocode

```c
__int64 *__fastcall wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(
        __int64 *a1,
        __int64 a2)
{
  __int64 v3; // rdi

  v3 = *a1;
  *a1 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  return a1;
}

```

## disassembly

```asm
0x18001ba2c  mov     [rsp+arg_0], rbx
0x18001ba31  push    rdi
0x18001ba32  sub     rsp, 20h
0x18001ba36  mov     rbx, rcx
0x18001ba39  mov     rdi, [rcx]
0x18001ba3c  mov     [rcx], rdx
0x18001ba3f  test    rdx, rdx
0x18001ba42  jz      short loc_18001BA53
0x18001ba44  mov     rax, [rdx]
0x18001ba47  mov     rcx, rdx
0x18001ba4a  mov     rax, [rax+8]
0x18001ba4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba53  test    rdi, rdi
0x18001ba56  jz      short loc_18001BA67
0x18001ba58  mov     rax, [rdi]
0x18001ba5b  mov     rcx, rdi
0x18001ba5e  mov     rax, [rax+10h]
0x18001ba62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba67  mov     rax, rbx
0x18001ba6a  mov     rbx, [rsp+28h+arg_0]
0x18001ba6f  add     rsp, 20h
0x18001ba73  pop     rdi
0x18001ba74  retn
```
