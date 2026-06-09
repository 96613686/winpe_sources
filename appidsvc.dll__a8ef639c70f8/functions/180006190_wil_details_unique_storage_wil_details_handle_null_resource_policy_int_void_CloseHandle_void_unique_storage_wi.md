# wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)

- ea: `0x180006190`
- end: `0x1800061ad`
- name: `??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c5f3`
- `0x18000c619`
- `0x18000ca2c`

## callees

- `0x180006190`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061a1`

## pseudocode

```c
int __fastcall wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(
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
0x180006190  sub     rsp, 28h
0x180006194  mov     rcx, [rcx]; hObject
0x180006197  lea     rax, [rcx-1]
0x18000619b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000619f  ja      short loc_1800061A8
0x1800061a1  call    cs:__imp_CloseHandle
0x1800061a7  nop
0x1800061a8  add     rsp, 28h
0x1800061ac  retn
```
