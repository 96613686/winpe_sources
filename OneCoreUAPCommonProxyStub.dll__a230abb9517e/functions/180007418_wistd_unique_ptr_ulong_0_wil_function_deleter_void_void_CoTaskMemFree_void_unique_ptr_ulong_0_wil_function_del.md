# wistd::unique_ptr<ulong [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<ulong [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x180007418`
- end: `0x18000743a`
- name: `??1?$unique_ptr@$$BY0A@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b2f8`
- `0x18000b30a`
- `0x18000b401`
- `0x18000b6c7`
- `0x18000b6d9`

## callees

- `0x180007418`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000742e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000742e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wistd::unique_ptr<unsigned long [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned long [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x180007418  sub     rsp, 28h
0x18000741c  mov     rax, [rcx]
0x18000741f  mov     qword ptr [rcx], 0
0x180007426  test    rax, rax
0x180007429  jz      short loc_180007435
0x18000742b  mov     rcx, rax; pv
0x18000742e  call    cs:__imp_CoTaskMemFree
0x180007434  nop
0x180007435  add     rsp, 28h
0x180007439  retn
```
