# wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x18000e66c`
- end: `0x18000e696`
- name: `??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013274`
- `0x180027d90`
- `0x180036290`
- `0x18003896c`
- `0x180038f94`
- `0x18003a48c`
- `0x18003d740`

## callees

- `0x18000e66c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e68b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e68b`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        __int64 a1)
{
  void *v1; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
      CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x18000e66c  sub     rsp, 28h
0x18000e670  cmp     byte ptr [rcx+10h], 0
0x18000e674  jz      short loc_18000E691
0x18000e676  mov     rdx, [rcx]
0x18000e679  mov     rax, [rcx+8]
0x18000e67d  mov     r8, [rdx]
0x18000e680  mov     [rdx], rax
0x18000e683  test    r8, r8
0x18000e686  jz      short loc_18000E691
0x18000e688  mov     rcx, r8; pv
0x18000e68b  call    cs:__imp_CoTaskMemFree
0x18000e691  add     rsp, 28h
0x18000e695  retn
```
