# wistd::unique_ptr<uint,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uint *)

- ea: `0x180021d10`
- end: `0x180021d34`
- name: `?reset@?$unique_ptr@IU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAI@Z`
- size: `36`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001085c`
- `0x1800108b4`
- `0x18001314c`
- `0x180013ca0`
- `0x1800258e0`

## callees

- `0x180021d10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d22`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned int,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x180021d10  sub     rsp, 28h
0x180021d14  mov     rax, [rcx]
0x180021d17  mov     [rcx], rdx
0x180021d1a  test    rax, rax
0x180021d1d  jz      short loc_180021D2E
0x180021d1f  mov     rcx, rax; pv
0x180021d22  call    cs:__imp_CoTaskMemFree
0x180021d29  nop     dword ptr [rax+rax+00h]
0x180021d2e  add     rsp, 28h
0x180021d32  retn
```
