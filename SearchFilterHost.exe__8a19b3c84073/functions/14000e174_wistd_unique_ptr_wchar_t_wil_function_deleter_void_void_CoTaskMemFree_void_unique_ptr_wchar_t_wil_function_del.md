# wistd::unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x14000e174`
- end: `0x14000e195`
- name: `??1?$unique_ptr@PEA_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004b980`
- `0x14004bf7d`

## callees

- `0x14000e174`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000e18a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000e18a`

## pseudocode

```c
void __fastcall wistd::unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x14000e174  sub     rsp, 28h
0x14000e178  mov     rax, [rcx]
0x14000e17b  mov     qword ptr [rcx], 0
0x14000e182  test    rax, rax
0x14000e185  jz      short loc_14000E190
0x14000e187  mov     rcx, rax; pv
0x14000e18a  call    cs:__imp_CoTaskMemFree
0x14000e190  add     rsp, 28h
0x14000e194  retn
```
