# wil::details::out_param_t<wistd::unique_ptr<_NotificationUser,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_NotificationUser,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x1800136a0`
- end: `0x1800136c3`
- name: `??1?$out_param_t@V?$unique_ptr@U_NotificationUser@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034a70`
- `0x180035180`

## callees

- `0x1800136a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800136bb`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<_NotificationUser,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_NotificationUser,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
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
0x1800136a0  cmp     byte ptr [rcx+10h], 0
0x1800136a4  jz      short locret_1800136C2
0x1800136a6  mov     rdx, [rcx]
0x1800136a9  mov     rax, [rcx+8]
0x1800136ad  mov     r8, [rdx]
0x1800136b0  mov     [rdx], rax
0x1800136b3  test    r8, r8
0x1800136b6  jz      short locret_1800136C2
0x1800136b8  mov     rcx, r8
0x1800136bb  jmp     cs:__imp_CoTaskMemFree
0x1800136c2  retn
```
