# NgcUtils::CaptureAndRelease(CREDUI_ADDITIONAL_INFO *)

- ea: `0x18005d4b4`
- end: `0x18005d51b`
- name: `?CaptureAndRelease@NgcUtils@@YAXPEAUCREDUI_ADDITIONAL_INFO@@@Z`
- size: `103`
- prototype: `void __fastcall(NgcUtils *__hidden this, struct CREDUI_ADDITIONAL_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005d8fc`

## callees

- `0x18001a77c`
- `0x18005d4b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d4f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d4f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d508`

## pseudocode

```c
void __fastcall NgcUtils::CaptureAndRelease(NgcUtils *this, struct CREDUI_ADDITIONAL_INFO *a2)
{
  void *v3; // rcx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  if ( this )
  {
    if ( *(_QWORD *)this )
    {
      v4 = *(_QWORD *)this;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v4);
    }
    if ( *((_QWORD *)this + 1) )
    {
      v4 = *((_QWORD *)this + 1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v4);
    }
    v3 = (void *)*((_QWORD *)this + 2);
    if ( v3 )
      CoTaskMemFree(v3);
    CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x18005d4b4  test    rcx, rcx
0x18005d4b7  jz      short locret_18005D519
0x18005d4b9  push    rbx
0x18005d4ba  sub     rsp, 20h
0x18005d4be  mov     rax, [rcx]
0x18005d4c1  mov     rbx, rcx
0x18005d4c4  test    rax, rax
0x18005d4c7  jz      short loc_18005D4D8
0x18005d4c9  lea     rcx, [rsp+28h+arg_0]
0x18005d4ce  mov     [rsp+28h+arg_0], rax
0x18005d4d3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005d4d8  mov     rax, [rbx+8]
0x18005d4dc  test    rax, rax
0x18005d4df  jz      short loc_18005D4F0
0x18005d4e1  lea     rcx, [rsp+28h+arg_0]
0x18005d4e6  mov     [rsp+28h+arg_0], rax
0x18005d4eb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005d4f0  mov     rcx, [rbx+10h]; pv
0x18005d4f4  test    rcx, rcx
0x18005d4f7  jz      short loc_18005D505
0x18005d4f9  call    cs:__imp_CoTaskMemFree
0x18005d500  nop     dword ptr [rax+rax+00h]
0x18005d505  mov     rcx, rbx; pv
0x18005d508  call    cs:__imp_CoTaskMemFree
0x18005d50f  nop     dword ptr [rax+rax+00h]
0x18005d514  add     rsp, 20h
0x18005d518  pop     rbx
0x18005d519  retn
```
