# wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x18002b180`
- end: `0x18002b1aa`
- name: `??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bd64`
- `0x18003b6f0`
- `0x18003b8bc`
- `0x1800585f1`
- `0x18005911b`
- `0x18005912d`

## callees

- `0x18002b180`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b19f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b19f`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
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
0x18002b180  sub     rsp, 28h
0x18002b184  cmp     byte ptr [rcx+10h], 0
0x18002b188  jz      short loc_18002B1A5
0x18002b18a  mov     rdx, [rcx]
0x18002b18d  mov     rax, [rcx+8]
0x18002b191  mov     r8, [rdx]
0x18002b194  mov     [rdx], rax
0x18002b197  test    r8, r8
0x18002b19a  jz      short loc_18002B1A5
0x18002b19c  mov     rcx, r8; pv
0x18002b19f  call    cs:__imp_CoTaskMemFree
0x18002b1a5  add     rsp, 28h
0x18002b1a9  retn
```
