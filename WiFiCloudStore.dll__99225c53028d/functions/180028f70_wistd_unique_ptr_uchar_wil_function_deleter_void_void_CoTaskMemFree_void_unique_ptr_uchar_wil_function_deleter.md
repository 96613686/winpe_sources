# wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x180028f70`
- end: `0x180028f91`
- name: `??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f0e4`

## callees

- `0x180028f70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028f86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028f86`

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
0x180028f70  sub     rsp, 28h
0x180028f74  mov     rax, [rcx]
0x180028f77  mov     qword ptr [rcx], 0
0x180028f7e  test    rax, rax
0x180028f81  jz      short loc_180028F8C
0x180028f83  mov     rcx, rax; pv
0x180028f86  call    cs:__imp_CoTaskMemFree
0x180028f8c  add     rsp, 28h
0x180028f90  retn
```
