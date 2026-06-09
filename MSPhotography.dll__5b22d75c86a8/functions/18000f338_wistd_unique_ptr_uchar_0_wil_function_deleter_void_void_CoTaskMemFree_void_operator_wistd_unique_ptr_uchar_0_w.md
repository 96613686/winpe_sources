# wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)

- ea: `0x18000f338`
- end: `0x18000f365`
- name: `??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `45`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014858`
- `0x1800151a0`

## callees

- `0x18000f338`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f356`

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
0x18000f338  push    rbx
0x18000f33a  sub     rsp, 20h
0x18000f33e  mov     rax, [rdx]
0x18000f341  mov     rbx, rcx
0x18000f344  mov     qword ptr [rdx], 0
0x18000f34b  mov     rcx, [rcx]; pv
0x18000f34e  mov     [rbx], rax
0x18000f351  test    rcx, rcx
0x18000f354  jz      short loc_18000F35C
0x18000f356  call    cs:__imp_CoTaskMemFree
0x18000f35c  mov     rax, rbx
0x18000f35f  add     rsp, 20h
0x18000f363  pop     rbx
0x18000f364  retn
```
