# wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::reset(HBITMAP__ *)

- ea: `0x180009e40`
- end: `0x180009e8d`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHBITMAP__@@@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002670`

## callees

- `0x180007258`
- `0x18000764c`
- `0x180009e40`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180009e6a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180009e6a`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    DeleteObject(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180009e40  mov     [rsp+arg_8], rbx
0x180009e45  mov     [rsp+arg_10], rsi
0x180009e4a  push    rdi
0x180009e4b  sub     rsp, 20h
0x180009e4f  mov     rdi, [rcx]
0x180009e52  mov     rsi, rdx
0x180009e55  mov     rbx, rcx
0x180009e58  test    rdi, rdi
0x180009e5b  jz      short loc_180009E7A
0x180009e5d  lea     rcx, [rsp+28h+arg_0]; this
0x180009e62  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009e67  mov     rcx, rdi; ho
0x180009e6a  call    cs:__imp_DeleteObject
0x180009e70  lea     rcx, [rsp+28h+arg_0]; this
0x180009e75  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009e7a  mov     [rbx], rsi
0x180009e7d  mov     rbx, [rsp+28h+arg_8]
0x180009e82  mov     rsi, [rsp+28h+arg_10]
0x180009e87  add     rsp, 20h
0x180009e8b  pop     rdi
0x180009e8c  retn
```
