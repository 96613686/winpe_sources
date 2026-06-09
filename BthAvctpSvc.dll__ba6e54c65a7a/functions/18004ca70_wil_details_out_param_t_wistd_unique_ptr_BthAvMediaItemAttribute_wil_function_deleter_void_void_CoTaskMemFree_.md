# wil::details::out_param_t<wistd::unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x18004ca70`
- end: `0x18004ca9a`
- name: `??1?$out_param_t@V?$unique_ptr@UBthAvMediaItemAttribute@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004e244`
- `0x18005aff4`

## callees

- `0x18004ca70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ca8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ca8f`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
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
0x18004ca70  sub     rsp, 28h
0x18004ca74  cmp     byte ptr [rcx+10h], 0
0x18004ca78  jz      short loc_18004CA95
0x18004ca7a  mov     rdx, [rcx]
0x18004ca7d  mov     rax, [rcx+8]
0x18004ca81  mov     r8, [rdx]
0x18004ca84  mov     [rdx], rax
0x18004ca87  test    r8, r8
0x18004ca8a  jz      short loc_18004CA95
0x18004ca8c  mov     rcx, r8; pv
0x18004ca8f  call    cs:__imp_CoTaskMemFree
0x18004ca95  add     rsp, 28h
0x18004ca99  retn
```
