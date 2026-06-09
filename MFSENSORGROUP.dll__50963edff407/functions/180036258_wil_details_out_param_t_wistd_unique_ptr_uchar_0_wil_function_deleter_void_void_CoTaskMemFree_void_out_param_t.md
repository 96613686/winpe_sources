# wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x180036258`
- end: `0x18003627b`
- name: `??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e30c`
- `0x1800444f0`
- `0x1800544c4`
- `0x1800553d8`
- `0x180070948`
- `0x180071070`

## callees

- `0x180036258`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036274`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
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
0x180036258  cmp     byte ptr [rcx+10h], 0
0x18003625c  jz      short locret_180036270
0x18003625e  mov     rdx, [rcx]
0x180036261  mov     rax, [rcx+8]
0x180036265  mov     r8, [rdx]
0x180036268  mov     [rdx], rax
0x18003626b  test    r8, r8
0x18003626e  jnz     short loc_180036271
0x180036270  retn
0x180036271  mov     rcx, r8
0x180036274  jmp     cs:__imp_CoTaskMemFree
```
