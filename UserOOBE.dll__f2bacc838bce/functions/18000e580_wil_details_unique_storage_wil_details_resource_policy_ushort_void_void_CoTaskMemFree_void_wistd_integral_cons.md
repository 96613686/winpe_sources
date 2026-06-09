# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18000e580`
- end: `0x18000e5cd`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `33`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000aab8`
- `0x18000ad04`
- `0x180012ab8`
- `0x180015a90`
- `0x1800218b8`
- `0x18002197c`
- `0x180021a84`
- `0x180021b8c`
- `0x180021c8c`
- `0x180022690`
- `0x1800227c8`
- `0x180022900`
- `0x180022f2c`
- `0x1800233ec`
- `0x180023b4c`
- `0x180023c30`
- `0x180023e38`
- `0x180024144`
- `0x18002586c`
- `0x180025ca0`
- `0x1800261ac`
- `0x180026ab0`
- `0x180026c00`
- `0x180028684`
- `0x180028adc`
- `0x18002a480`
- `0x18002ba90`
- `0x18002bd20`
- `0x1800331a8`
- `0x1800332ac`
- `0x180033374`
- `0x180035420`
- `0x1800354c0`

## callees

- `0x1800054ac`
- `0x180005768`
- `0x18000e580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5aa`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CoTaskMemFree(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000e580  mov     [rsp+arg_8], rbx
0x18000e585  mov     [rsp+arg_10], rsi
0x18000e58a  push    rdi
0x18000e58b  sub     rsp, 20h
0x18000e58f  mov     rdi, [rcx]
0x18000e592  mov     rsi, rdx
0x18000e595  mov     rbx, rcx
0x18000e598  test    rdi, rdi
0x18000e59b  jz      short loc_18000E5BA
0x18000e59d  lea     rcx, [rsp+28h+arg_0]; this
0x18000e5a2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e5a7  mov     rcx, rdi; pv
0x18000e5aa  call    cs:__imp_CoTaskMemFree
0x18000e5b0  lea     rcx, [rsp+28h+arg_0]; this
0x18000e5b5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e5ba  mov     [rbx], rsi
0x18000e5bd  mov     rbx, [rsp+28h+arg_8]
0x18000e5c2  mov     rsi, [rsp+28h+arg_10]
0x18000e5c7  add     rsp, 20h
0x18000e5cb  pop     rdi
0x18000e5cc  retn
```
