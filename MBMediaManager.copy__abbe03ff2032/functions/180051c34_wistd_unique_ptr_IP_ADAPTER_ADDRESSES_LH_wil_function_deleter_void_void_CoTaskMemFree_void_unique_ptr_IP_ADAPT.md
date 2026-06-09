# wistd::unique_ptr<_IP_ADAPTER_ADDRESSES_LH,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<_IP_ADAPTER_ADDRESSES_LH,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x180051c34`
- end: `0x180051c55`
- name: `??1?$unique_ptr@U_IP_ADAPTER_ADDRESSES_LH@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180058bc7`

## callees

- `0x180051c34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051c4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051c4a`

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
0x180051c34  sub     rsp, 28h
0x180051c38  mov     rax, [rcx]
0x180051c3b  mov     qword ptr [rcx], 0
0x180051c42  test    rax, rax
0x180051c45  jz      short loc_180051C50
0x180051c47  mov     rcx, rax; pv
0x180051c4a  call    cs:__imp_CoTaskMemFree
0x180051c50  add     rsp, 28h
0x180051c54  retn
```
