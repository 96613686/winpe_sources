# wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x18000fb94`
- end: `0x18000fbbe`
- name: `??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800102c4`

## callees

- `0x18000fb94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbb3`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
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
0x18000fb94  sub     rsp, 28h
0x18000fb98  cmp     byte ptr [rcx+10h], 0
0x18000fb9c  jz      short loc_18000FBB9
0x18000fb9e  mov     rdx, [rcx]
0x18000fba1  mov     rax, [rcx+8]
0x18000fba5  mov     r8, [rdx]
0x18000fba8  mov     [rdx], rax
0x18000fbab  test    r8, r8
0x18000fbae  jz      short loc_18000FBB9
0x18000fbb0  mov     rcx, r8; pv
0x18000fbb3  call    cs:__imp_CoTaskMemFree
0x18000fbb9  add     rsp, 28h
0x18000fbbd  retn
```
