# wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18001873c`
- end: `0x18001875d`
- name: `??1?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003c7e4`
- `0x18003cb2b`
- `0x18003cb61`

## callees

- `0x18001873c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018752`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018752`

## pseudocode

```c
void __fastcall wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x18001873c  sub     rsp, 28h
0x180018740  mov     rax, [rcx]
0x180018743  mov     qword ptr [rcx], 0
0x18001874a  test    rax, rax
0x18001874d  jz      short loc_180018758
0x18001874f  mov     rcx, rax; pv
0x180018752  call    cs:__imp_CoTaskMemFree
0x180018758  add     rsp, 28h
0x18001875c  retn
```
