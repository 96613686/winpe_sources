# wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)

- ea: `0x1800060fc`
- end: `0x18000611e`
- name: `??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c558`
- `0x18000c62b`
- `0x18000c9e2`

## callees

- `0x1800060fc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006112`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006112`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800060fc  mov     [rsp+arg_0], rcx
0x180006101  sub     rsp, 28h
0x180006105  mov     rcx, [rcx]; hObject
0x180006108  lea     rax, [rcx-1]
0x18000610c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006110  ja      short loc_180006119
0x180006112  call    cs:__imp_CloseHandle
0x180006118  nop
0x180006119  add     rsp, 28h
0x18000611d  retn
```
