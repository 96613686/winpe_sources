# wil::details::out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x1800073e8`
- end: `0x180007410`
- name: `??1?$out_param_t@V?$unique_ptr@$$BY0A@PEAXU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a500`
- `0x18000b6fd`
- `0x18000b70f`

## callees

- `0x1800073e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007404`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<void * [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        void ***a1)
{
  void **v1; // rdx
  void **v2; // rax
  void *v3; // rcx

  if ( *((_BYTE *)a1 + 16) )
  {
    v1 = a1[1];
    v2 = *a1;
    v3 = **a1;
    *v2 = v1;
    if ( v3 )
      CoTaskMemFree(v3);
  }
}

```

## disassembly

```asm
0x1800073e8  sub     rsp, 28h
0x1800073ec  cmp     byte ptr [rcx+10h], 0
0x1800073f0  jz      short loc_18000740B
0x1800073f2  mov     rdx, [rcx+8]
0x1800073f6  mov     rax, [rcx]
0x1800073f9  mov     rcx, [rax]; pv
0x1800073fc  mov     [rax], rdx
0x1800073ff  test    rcx, rcx
0x180007402  jz      short loc_18000740B
0x180007404  call    cs:__imp_CoTaskMemFree
0x18000740a  nop
0x18000740b  add     rsp, 28h
0x18000740f  retn
```
