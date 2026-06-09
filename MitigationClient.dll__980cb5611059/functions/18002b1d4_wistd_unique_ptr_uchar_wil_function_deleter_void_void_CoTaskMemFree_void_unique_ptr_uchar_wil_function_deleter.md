# wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18002b1d4`
- end: `0x18002b1f5`
- name: `??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800585df`
- `0x180059109`
- `0x180059550`

## callees

- `0x18002b1d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b1ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b1ea`

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
0x18002b1d4  sub     rsp, 28h
0x18002b1d8  mov     rax, [rcx]
0x18002b1db  mov     qword ptr [rcx], 0
0x18002b1e2  test    rax, rax
0x18002b1e5  jz      short loc_18002B1F0
0x18002b1e7  mov     rcx, rax; pv
0x18002b1ea  call    cs:__imp_CoTaskMemFree
0x18002b1f0  add     rsp, 28h
0x18002b1f4  retn
```
