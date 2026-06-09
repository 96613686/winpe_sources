# wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x180004968`
- end: `0x180004989`
- name: `??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f7f5`
- `0x18000fac8`

## callees

- `0x180004968`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000497e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000497e`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x180004968  sub     rsp, 28h
0x18000496c  mov     rax, [rcx]
0x18000496f  mov     qword ptr [rcx], 0
0x180004976  test    rax, rax
0x180004979  jz      short loc_180004984
0x18000497b  mov     rcx, rax; pv
0x18000497e  call    cs:__imp_CoTaskMemFree
0x180004984  add     rsp, 28h
0x180004988  retn
```
