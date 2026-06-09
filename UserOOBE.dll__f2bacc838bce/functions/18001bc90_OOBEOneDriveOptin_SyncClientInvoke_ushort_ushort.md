# OOBEOneDriveOptin::SyncClientInvoke(ushort *,ushort * *)

- ea: `0x18001bc90`
- end: `0x18001bd75`
- name: `?SyncClientInvoke@OOBEOneDriveOptin@@UEAAJPEAGPEAPEAG@Z`
- size: `229`
- prototype: `__int64 __fastcall(OOBEOneDriveOptin *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019840`

## callees

- `0x18000a5c8`
- `0x18000e2bc`
- `0x180010dc8`
- `0x18001136c`
- `0x180018c78`
- `0x18001bc90`
- `0x18001cf00`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bccd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bccd`

## string_xrefs

- `0x18001bd54`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OOBEOneDriveOptin::SyncClientInvoke(
        OOBEOneDriveOptin *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HRESULT v5; // eax
  unsigned __int16 *v6; // rax
  const char *v7; // r9
  __int64 result; // rax
  int v9; // eax
  int v10; // [rsp+20h] [rbp-28h]
  void *v11[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int16 *v13; // [rsp+60h] [rbp+18h] BYREF
  LPVOID v14; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  v14 = 0;
  v5 = CoCreateInstance(
         &GUID_94269c4e_071a_4116_90e6_52e557067e4e,
         0,
         4u,
         &GUID_6a821279_ab49_48f8_9a27_f6c59b4ff024,
         &v14);
  try
  {
    if ( v5 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v14 + 24LL))(
             v14,
             a2,
             a3);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9E,
          (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
          (const char *)(unsigned int)v9,
          v10);
    }
    else
    {
      wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        v11,
        L"{\"syncClientInvokeError\":%d}",
        (unsigned int)v5);
      wil::make_bstr(&v13, v11[0]);
      v6 = v13;
      v13 = 0;
      *a3 = v6;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v11);
    }
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v14);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA1,
                           (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18001bc90  mov     r11, rsp
0x18001bc93  mov     [r11+8], rbx
0x18001bc97  push    rdi
0x18001bc98  sub     rsp, 40h
0x18001bc9c  mov     rbx, r8
0x18001bc9f  mov     rdi, rdx
0x18001bca2  mov     qword ptr [r8], 0
0x18001bca9  mov     qword ptr [r11+20h], 0
0x18001bcb1  lea     rax, [r11+20h]
0x18001bcb5  mov     [r11-28h], rax
0x18001bcb9  lea     r9, _GUID_6a821279_ab49_48f8_9a27_f6c59b4ff024; riid
0x18001bcc0  xor     edx, edx; pUnkOuter
0x18001bcc2  lea     r8d, [rdx+4]; dwClsContext
0x18001bcc6  lea     rcx, _GUID_94269c4e_071a_4116_90e6_52e557067e4e; rclsid
0x18001bccd  call    cs:__imp_CoCreateInstance
0x18001bcd3  test    eax, eax
0x18001bcd5  jns     short loc_18001BD31
0x18001bcd7  mov     r8d, eax
0x18001bcda  lea     rdx, aSyncclientinvo; "{\"syncClientInvokeError\":%d}"
0x18001bce1  lea     rcx, [rsp+48h+var_18]
0x18001bce6  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x18001bceb  nop
0x18001bcec  mov     rdx, [rsp+48h+var_18]
0x18001bcf1  lea     rcx, [rsp+48h+arg_10]
0x18001bcf6  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18001bcfb  mov     rax, [rsp+48h+arg_10]
0x18001bd00  mov     [rsp+48h+arg_10], 0
0x18001bd09  mov     [rbx], rax
0x18001bd0c  lea     rcx, [rsp+48h+arg_10]
0x18001bd11  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001bd16  nop
0x18001bd17  lea     rcx, [rsp+48h+var_18]
0x18001bd1c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001bd21  nop
0x18001bd22  lea     rcx, [rsp+48h+arg_18]
0x18001bd27  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001bd2c  nop
0x18001bd2d  xor     eax, eax
0x18001bd2f  jmp     short loc_18001BD6A
0x18001bd31  mov     rcx, [rsp+48h+arg_18]
0x18001bd36  mov     rax, [rcx]
0x18001bd39  mov     r8, rbx
0x18001bd3c  mov     rdx, rdi
0x18001bd3f  mov     rax, [rax+18h]
0x18001bd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd48  mov     rcx, [rsp+48h]; this
0x18001bd4d  test    eax, eax
0x18001bd4f  jns     short loc_18001BD22
0x18001bd51  mov     r9d, eax; char *
0x18001bd54  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001bd5b  mov     edx, 9Eh; void *
0x18001bd60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001bd66  mov     eax, dword ptr [rsp+48h+arg_10]
0x18001bd6a  mov     rbx, [rsp+48h+arg_0]
0x18001bd6f  add     rsp, 40h
0x18001bd73  pop     rdi
0x18001bd74  retn
```
