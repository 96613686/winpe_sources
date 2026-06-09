# wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x18001870c`
- end: `0x180018736`
- name: `??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001de80`
- `0x18002b428`
- `0x18003c7f6`

## callees

- `0x18001870c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001872b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001872b`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
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
0x18001870c  sub     rsp, 28h
0x180018710  cmp     byte ptr [rcx+10h], 0
0x180018714  jz      short loc_180018731
0x180018716  mov     rdx, [rcx]
0x180018719  mov     rax, [rcx+8]
0x18001871d  mov     r8, [rdx]
0x180018720  mov     [rdx], rax
0x180018723  test    r8, r8
0x180018726  jz      short loc_180018731
0x180018728  mov     rcx, r8; pv
0x18001872b  call    cs:__imp_CoTaskMemFree
0x180018731  add     rsp, 28h
0x180018735  retn
```
