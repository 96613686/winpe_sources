# wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18000fbe8`
- end: `0x18000fc09`
- name: `??1?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001167c`

## callees

- `0x18000fbe8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbfe`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x18000fbe8  sub     rsp, 28h
0x18000fbec  mov     rax, [rcx]
0x18000fbef  mov     qword ptr [rcx], 0
0x18000fbf6  test    rax, rax
0x18000fbf9  jz      short loc_18000FC04
0x18000fbfb  mov     rcx, rax; pv
0x18000fbfe  call    cs:__imp_CoTaskMemFree
0x18000fc04  add     rsp, 28h
0x18000fc08  retn
```
