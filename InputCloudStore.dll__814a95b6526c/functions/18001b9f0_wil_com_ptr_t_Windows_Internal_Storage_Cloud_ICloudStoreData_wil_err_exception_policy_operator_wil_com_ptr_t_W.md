# wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy> &&)

- ea: `0x18001b9f0`
- end: `0x18001ba24`
- name: `??4?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `52`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021510`
- `0x1800215f0`
- `0x1800216d0`
- `0x1800217f0`
- `0x1800218c0`
- `0x180021a60`
- `0x180021b40`
- `0x180021c50`

## callees

- `0x18001b9f0`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(
        __int64 *a1,
        __int64 *a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx

  v3 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v3;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return a1;
}

```

## disassembly

```asm
0x18001b9f0  push    rbx
0x18001b9f2  sub     rsp, 20h
0x18001b9f6  mov     rbx, rcx
0x18001b9f9  mov     rax, [rdx]
0x18001b9fc  mov     qword ptr [rdx], 0
0x18001ba03  mov     rcx, [rcx]
0x18001ba06  mov     [rbx], rax
0x18001ba09  test    rcx, rcx
0x18001ba0c  jz      short loc_18001BA1B
0x18001ba0e  mov     rax, [rcx]
0x18001ba11  mov     rax, [rax+10h]
0x18001ba15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba1a  nop
0x18001ba1b  mov     rax, rbx
0x18001ba1e  add     rsp, 20h
0x18001ba22  pop     rbx
0x18001ba23  retn
```
