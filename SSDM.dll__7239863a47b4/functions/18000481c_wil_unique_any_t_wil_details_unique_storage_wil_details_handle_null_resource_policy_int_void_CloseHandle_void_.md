# wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)

- ea: `0x18000481c`
- end: `0x180004838`
- name: `??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `28`
- prototype: `int __fastcall(void **)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000efa3`
- `0x18000f8ec`
- `0x18000f902`
- `0x18000f926`
- `0x18000f9f0`
- `0x18000fa8e`
- `0x18000fada`
- `0x18000fafe`

## callees

- `0x18000481c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000482d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000482d`

## pseudocode

```c
int __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(
        void **a1)
{
  char *v1; // rcx
  int result; // eax

  v1 = (char *)*a1;
  result = (_DWORD)v1 - 1;
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return CloseHandle(v1);
  return result;
}

```

## disassembly

```asm
0x18000481c  sub     rsp, 28h
0x180004820  mov     rcx, [rcx]; hObject
0x180004823  lea     rax, [rcx-1]
0x180004827  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000482b  ja      short loc_180004833
0x18000482d  call    cs:__imp_CloseHandle
0x180004833  add     rsp, 28h
0x180004837  retn
```
