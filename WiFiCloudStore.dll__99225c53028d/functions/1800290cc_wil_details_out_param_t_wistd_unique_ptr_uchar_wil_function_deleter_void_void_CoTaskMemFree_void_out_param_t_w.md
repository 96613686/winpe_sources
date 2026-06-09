# wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x1800290cc`
- end: `0x1800290f6`
- name: `??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800144c0`
- `0x18003f0f6`
- `0x18003f38d`

## callees

- `0x1800290cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800290eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800290eb`

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
0x1800290cc  sub     rsp, 28h
0x1800290d0  cmp     byte ptr [rcx+10h], 0
0x1800290d4  jz      short loc_1800290F1
0x1800290d6  mov     rdx, [rcx]
0x1800290d9  mov     rax, [rcx+8]
0x1800290dd  mov     r8, [rdx]
0x1800290e0  mov     [rdx], rax
0x1800290e3  test    r8, r8
0x1800290e6  jz      short loc_1800290F1
0x1800290e8  mov     rcx, r8; pv
0x1800290eb  call    cs:__imp_CoTaskMemFree
0x1800290f1  add     rsp, 28h
0x1800290f5  retn
```
