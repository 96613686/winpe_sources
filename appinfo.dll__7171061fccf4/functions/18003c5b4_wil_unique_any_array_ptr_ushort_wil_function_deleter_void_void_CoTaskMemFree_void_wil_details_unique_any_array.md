# wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)

- ea: `0x18003c5b4`
- end: `0x18003c611`
- name: `?reset@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ`
- size: `93`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002e8bc`

## callees

- `0x18003c198`
- `0x18003c5b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c5ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c5ec`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::reset(
        __int64 a1)
{
  LPVOID *v1; // rbx
  LPVOID *v3; // rsi

  v1 = *(LPVOID **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = &v1[*(_QWORD *)(a1 + 8)];
    while ( v1 != v3 )
      wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(*v1++);
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18003c5b4  mov     [rsp+arg_0], rbx
0x18003c5b9  mov     [rsp+arg_8], rsi
0x18003c5be  push    rdi
0x18003c5bf  sub     rsp, 20h
0x18003c5c3  mov     rbx, [rcx]
0x18003c5c6  mov     rdi, rcx
0x18003c5c9  test    rbx, rbx
0x18003c5cc  jz      short loc_18003C601
0x18003c5ce  mov     rax, [rcx+8]
0x18003c5d2  lea     rsi, [rbx+rax*8]
0x18003c5d6  jmp     short loc_18003C5E4
0x18003c5d8  mov     rcx, [rbx]; pv
0x18003c5db  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZPEAG@details@wil@@SAXPEAG@Z; wil::details::close_invoke_helper<1,void (*)(void *),&CoTaskMemFree(void *),ushort *>::close_reset(ushort *)
0x18003c5e0  add     rbx, 8
0x18003c5e4  cmp     rbx, rsi
0x18003c5e7  jnz     short loc_18003C5D8
0x18003c5e9  mov     rcx, [rdi]; pv
0x18003c5ec  call    cs:__imp_CoTaskMemFree
0x18003c5f2  mov     qword ptr [rdi], 0
0x18003c5f9  mov     qword ptr [rdi+8], 0
0x18003c601  mov     rbx, [rsp+28h+arg_0]
0x18003c606  mov     rsi, [rsp+28h+arg_8]
0x18003c60b  add     rsp, 20h
0x18003c60f  pop     rdi
0x18003c610  retn
```
