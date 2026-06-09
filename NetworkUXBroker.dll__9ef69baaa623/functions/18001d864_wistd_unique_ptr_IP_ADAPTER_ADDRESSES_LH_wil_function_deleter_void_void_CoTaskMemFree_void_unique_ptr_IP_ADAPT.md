# wistd::unique_ptr<_IP_ADAPTER_ADDRESSES_LH,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<_IP_ADAPTER_ADDRESSES_LH,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18001d864`
- end: `0x18001d885`
- name: `??1?$unique_ptr@U_IP_ADAPTER_ADDRESSES_LH@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004578e`
- `0x18004688d`

## callees

- `0x18001d864`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d87a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d87a`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_IP_ADAPTER_ADDRESSES_LH,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<_IP_ADAPTER_ADDRESSES_LH,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18001d864  sub     rsp, 28h
0x18001d868  mov     rax, [rcx]
0x18001d86b  mov     qword ptr [rcx], 0
0x18001d872  test    rax, rax
0x18001d875  jz      short loc_18001D880
0x18001d877  mov     rcx, rax; pv
0x18001d87a  call    cs:__imp_CoTaskMemFree
0x18001d880  add     rsp, 28h
0x18001d884  retn
```
