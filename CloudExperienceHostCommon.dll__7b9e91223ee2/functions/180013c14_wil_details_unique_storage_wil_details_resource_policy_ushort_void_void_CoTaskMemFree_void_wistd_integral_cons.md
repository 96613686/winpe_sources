# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180013c14`
- end: `0x180013c61`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `28`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003af4`
- `0x180004b80`
- `0x180004db0`
- `0x180004edc`
- `0x180011188`
- `0x180012774`
- `0x180013ef4`
- `0x180018568`
- `0x180022c50`
- `0x180023634`
- `0x180023c4c`
- `0x1800240f8`
- `0x180024cbc`
- `0x18002583c`
- `0x180026668`
- `0x180026848`
- `0x18003d0c0`
- `0x18003d190`
- `0x180048cb8`
- `0x18005880c`
- `0x1800588dc`
- `0x1800589e0`
- `0x180058ab8`
- `0x180058b90`
- `0x180058cb8`
- `0x180059108`
- `0x18007b134`
- `0x18009f404`

## callees

- `0x180013c14`
- `0x18001da68`
- `0x18001dd04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c3e`

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
0x180013c14  mov     [rsp+arg_8], rbx
0x180013c19  mov     [rsp+arg_10], rsi
0x180013c1e  push    rdi
0x180013c1f  sub     rsp, 20h
0x180013c23  mov     rdi, [rcx]
0x180013c26  mov     rsi, rdx
0x180013c29  mov     rbx, rcx
0x180013c2c  test    rdi, rdi
0x180013c2f  jz      short loc_180013C4E
0x180013c31  lea     rcx, [rsp+28h+arg_0]; this
0x180013c36  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180013c3b  mov     rcx, rdi; pv
0x180013c3e  call    cs:__imp_CoTaskMemFree
0x180013c44  lea     rcx, [rsp+28h+arg_0]; this
0x180013c49  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180013c4e  mov     [rbx], rsi
0x180013c51  mov     rbx, [rsp+28h+arg_8]
0x180013c56  mov     rsi, [rsp+28h+arg_10]
0x180013c5b  add     rsp, 20h
0x180013c5f  pop     rdi
0x180013c60  retn
```
