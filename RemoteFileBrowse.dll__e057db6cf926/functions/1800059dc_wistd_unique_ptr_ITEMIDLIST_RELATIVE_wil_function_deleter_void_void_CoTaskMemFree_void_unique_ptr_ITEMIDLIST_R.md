# wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x1800059dc`
- end: `0x1800059fd`
- name: `??1?$unique_ptr@U_ITEMIDLIST_RELATIVE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001814b`
- `0x180018661`
- `0x18001880f`
- `0x180018821`
- `0x1800189dd`
- `0x180018abe`
- `0x180018ad0`

## callees

- `0x1800059dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall wistd::unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<_ITEMIDLIST_RELATIVE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x1800059dc  sub     rsp, 28h
0x1800059e0  mov     rax, [rcx]
0x1800059e3  mov     qword ptr [rcx], 0
0x1800059ea  test    rax, rax
0x1800059ed  jz      short loc_1800059F8
0x1800059ef  mov     rcx, rax; pv
0x1800059f2  call    cs:__imp_CoTaskMemFree
0x1800059f8  add     rsp, 28h
0x1800059fc  retn
```
