# wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::reset(HSTRING_BUFFER__ *)

- ea: `0x180011398`
- end: `0x1800113e5`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING_BUFFER__@@@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010c08`

## callees

- `0x1800047c4`
- `0x180004e40`
- `0x180011398`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800113c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800113c2`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::reset(
        HSTRING_BUFFER *a1,
        HSTRING_BUFFER a2)
{
  HSTRING_BUFFER v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    WindowsDeleteStringBuffer(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180011398  mov     [rsp+arg_8], rbx
0x18001139d  mov     [rsp+arg_10], rsi
0x1800113a2  push    rdi
0x1800113a3  sub     rsp, 20h
0x1800113a7  mov     rdi, [rcx]
0x1800113aa  mov     rsi, rdx
0x1800113ad  mov     rbx, rcx
0x1800113b0  test    rdi, rdi
0x1800113b3  jz      short loc_1800113D2
0x1800113b5  lea     rcx, [rsp+28h+arg_0]; this
0x1800113ba  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800113bf  mov     rcx, rdi; bufferHandle
0x1800113c2  call    cs:__imp_WindowsDeleteStringBuffer
0x1800113c8  lea     rcx, [rsp+28h+arg_0]; this
0x1800113cd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800113d2  mov     [rbx], rsi
0x1800113d5  mov     rbx, [rsp+28h+arg_8]
0x1800113da  mov     rsi, [rsp+28h+arg_10]
0x1800113df  add     rsp, 20h
0x1800113e3  pop     rdi
0x1800113e4  retn
```
