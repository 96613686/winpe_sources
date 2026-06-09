# wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x1800151a0`
- end: `0x1800151c8`
- name: `??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007a8bf`
- `0x18007a8e0`
- `0x18007ae40`
- `0x18007ae60`
- `0x18007b65a`
- `0x18007b66c`
- `0x18007bdf2`
- `0x18007be1f`
- `0x18007d2d5`
- `0x18007e28f`
- `0x18007e370`
- `0x18007e414`
- `0x18007e492`
- `0x18007e56a`
- `0x18007e58e`
- `0x18007e5a0`
- `0x18007f829`

## callees

- `0x1800151a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800151b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800151b6`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x1800151a0  sub     rsp, 28h
0x1800151a4  mov     rax, [rcx]
0x1800151a7  mov     qword ptr [rcx], 0
0x1800151ae  test    rax, rax
0x1800151b1  jz      short loc_1800151C2
0x1800151b3  mov     rcx, rax; pv
0x1800151b6  call    cs:__imp_CoTaskMemFree
0x1800151bd  nop     dword ptr [rax+rax+00h]
0x1800151c2  add     rsp, 28h
0x1800151c6  retn
```
