# wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(std::nullptr_t)

- ea: `0x180025578`
- end: `0x180025599`
- name: `?reset@?$unique_ptr@$$BY0A@U_DEVPROPERTY@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAX$$T@Z`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020a0c`
- `0x180023b24`
- `0x180047360`

## callees

- `0x180025578`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002558e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002558e`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
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
0x180025578  sub     rsp, 28h
0x18002557c  mov     rax, [rcx]
0x18002557f  mov     qword ptr [rcx], 0
0x180025586  test    rax, rax
0x180025589  jz      short loc_180025594
0x18002558b  mov     rcx, rax; pv
0x18002558e  call    cs:__imp_CoTaskMemFree
0x180025594  add     rsp, 28h
0x180025598  retn
```
