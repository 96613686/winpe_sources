# wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)

- ea: `0x180031964`
- end: `0x180031991`
- name: `??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `45`
- prototype: `void **__fastcall(void **, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a48c`
- `0x180047000`

## callees

- `0x180031964`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031982`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031982`

## pseudocode

```c
void **__fastcall wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
        void **a1,
        void **a2)
{
  void *v2; // rax
  void *v4; // rcx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    CoTaskMemFree(v4);
  return a1;
}

```

## disassembly

```asm
0x180031964  push    rbx
0x180031966  sub     rsp, 20h
0x18003196a  mov     rax, [rdx]
0x18003196d  mov     rbx, rcx
0x180031970  mov     qword ptr [rdx], 0
0x180031977  mov     rcx, [rcx]; pv
0x18003197a  mov     [rbx], rax
0x18003197d  test    rcx, rcx
0x180031980  jz      short loc_180031988
0x180031982  call    cs:__imp_CoTaskMemFree
0x180031988  mov     rax, rbx
0x18003198b  add     rsp, 20h
0x18003198f  pop     rbx
0x180031990  retn
```
