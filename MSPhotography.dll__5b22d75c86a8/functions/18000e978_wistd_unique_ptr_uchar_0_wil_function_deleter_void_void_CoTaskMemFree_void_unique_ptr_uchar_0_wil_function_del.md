# wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18000e978`
- end: `0x18000e999`
- name: `??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18013f561`
- `0x18013f57a`
- `0x18013f6b7`
- `0x18013f6c9`

## callees

- `0x18000e978`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e98e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e98e`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x18000e978  sub     rsp, 28h
0x18000e97c  mov     rax, [rcx]
0x18000e97f  mov     qword ptr [rcx], 0
0x18000e986  test    rax, rax
0x18000e989  jz      short loc_18000E994
0x18000e98b  mov     rcx, rax; pv
0x18000e98e  call    cs:__imp_CoTaskMemFree
0x18000e994  add     rsp, 28h
0x18000e998  retn
```
