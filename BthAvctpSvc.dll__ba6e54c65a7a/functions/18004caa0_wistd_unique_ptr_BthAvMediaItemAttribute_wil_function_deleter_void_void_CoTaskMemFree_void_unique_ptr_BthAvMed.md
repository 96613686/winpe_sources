# wistd::unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18004caa0`
- end: `0x18004cac1`
- name: `??1?$unique_ptr@UBthAvMediaItemAttribute@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005afe2`

## callees

- `0x18004caa0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cab6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cab6`

## pseudocode

```c
void __fastcall wistd::unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18004caa0  sub     rsp, 28h
0x18004caa4  mov     rax, [rcx]
0x18004caa7  mov     qword ptr [rcx], 0
0x18004caae  test    rax, rax
0x18004cab1  jz      short loc_18004CABC
0x18004cab3  mov     rcx, rax; pv
0x18004cab6  call    cs:__imp_CoTaskMemFree
0x18004cabc  add     rsp, 28h
0x18004cac0  retn
```
