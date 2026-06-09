# wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x180014b48`
- end: `0x180014b72`
- name: `??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_RELATIVE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018ae2`

## callees

- `0x180014b48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b67`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        __int64 a1)
{
  void *v1; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
      CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x180014b48  sub     rsp, 28h
0x180014b4c  cmp     byte ptr [rcx+10h], 0
0x180014b50  jz      short loc_180014B6D
0x180014b52  mov     rdx, [rcx]
0x180014b55  mov     rax, [rcx+8]
0x180014b59  mov     r8, [rdx]
0x180014b5c  mov     [rdx], rax
0x180014b5f  test    r8, r8
0x180014b62  jz      short loc_180014B6D
0x180014b64  mov     rcx, r8; pv
0x180014b67  call    cs:__imp_CoTaskMemFree
0x180014b6d  add     rsp, 28h
0x180014b71  retn
```
