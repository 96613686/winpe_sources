# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x18001da80`
- end: `0x18001db07`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000db78`
- `0x18000e0fc`

## callees

- `0x18000f580`
- `0x18001da80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dab2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dac5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dabd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dadf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dabd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dadf`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        void **a1,
        __int64 a2,
        __int64 a3)
{
  void **v4; // rax
  void **v5; // rsi
  void *v6; // rbp
  void *v7; // r14
  DWORD LastError; // ebx
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v4 = (void **)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &pv,
                  a2,
                  a3);
  v5 = v4;
  if ( a1 != v4 )
  {
    v6 = *a1;
    v7 = *v4;
    if ( *a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v6);
      SetLastError(LastError);
    }
    *a1 = v7;
    *v5 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return *a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18001da80  mov     [rsp+arg_8], rbx
0x18001da85  mov     [rsp+arg_10], rbp
0x18001da8a  push    rsi
0x18001da8b  push    rdi
0x18001da8c  push    r14
0x18001da8e  sub     rsp, 20h
0x18001da92  mov     rdi, rcx
0x18001da95  lea     rcx, [rsp+38h+pv]
0x18001da9a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001da9f  mov     rsi, rax
0x18001daa2  cmp     rdi, rax
0x18001daa5  jz      short loc_18001DAD5
0x18001daa7  mov     rbp, [rdi]
0x18001daaa  mov     r14, [rax]
0x18001daad  test    rbp, rbp
0x18001dab0  jz      short loc_18001DACB
0x18001dab2  call    cs:__imp_GetLastError
0x18001dab8  mov     rcx, rbp; pv
0x18001dabb  mov     ebx, eax
0x18001dabd  call    cs:__imp_CoTaskMemFree
0x18001dac3  mov     ecx, ebx; dwErrCode
0x18001dac5  call    cs:__imp_SetLastError
0x18001dacb  mov     [rdi], r14
0x18001dace  mov     qword ptr [rsi], 0
0x18001dad5  mov     rcx, [rsp+38h+pv]; pv
0x18001dada  test    rcx, rcx
0x18001dadd  jz      short loc_18001DAE5
0x18001dadf  call    cs:__imp_CoTaskMemFree
0x18001dae5  mov     rax, [rdi]
0x18001dae8  mov     rbx, [rsp+38h+arg_8]
0x18001daed  neg     rax
0x18001daf0  mov     rbp, [rsp+38h+arg_10]
0x18001daf5  sbb     eax, eax
0x18001daf7  not     eax
0x18001daf9  and     eax, 8007000Eh
0x18001dafe  add     rsp, 20h
0x18001db02  pop     r14
0x18001db04  pop     rdi
0x18001db05  pop     rsi
0x18001db06  retn
```
