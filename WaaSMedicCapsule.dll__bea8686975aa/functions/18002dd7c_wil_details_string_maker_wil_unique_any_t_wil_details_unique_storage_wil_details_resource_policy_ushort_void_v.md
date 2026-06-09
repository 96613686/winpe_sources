# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x18002dd7c`
- end: `0x18002de03`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002c9bc`
- `0x18003ca38`

## callees

- `0x18002a470`
- `0x18002dd7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ddae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ddae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ddc1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ddc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ddb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ddb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dddb`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        void **a1)
{
  void **v2; // rax
  void **v3; // rsi
  void *v4; // rbp
  void *v5; // r14
  DWORD LastError; // ebx
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v2 = (void **)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&pv);
  v3 = v2;
  if ( a1 != v2 )
  {
    v4 = *a1;
    v5 = *v2;
    if ( *a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v4);
      SetLastError(LastError);
    }
    *a1 = v5;
    *v3 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return *a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18002dd7c  mov     [rsp+arg_8], rbx
0x18002dd81  mov     [rsp+arg_10], rbp
0x18002dd86  push    rsi
0x18002dd87  push    rdi
0x18002dd88  push    r14
0x18002dd8a  sub     rsp, 20h
0x18002dd8e  mov     rdi, rcx
0x18002dd91  lea     rcx, [rsp+38h+pv]
0x18002dd96  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002dd9b  mov     rsi, rax
0x18002dd9e  cmp     rdi, rax
0x18002dda1  jz      short loc_18002DDD1
0x18002dda3  mov     rbp, [rdi]
0x18002dda6  mov     r14, [rax]
0x18002dda9  test    rbp, rbp
0x18002ddac  jz      short loc_18002DDC7
0x18002ddae  call    cs:__imp_GetLastError
0x18002ddb4  mov     rcx, rbp; pv
0x18002ddb7  mov     ebx, eax
0x18002ddb9  call    cs:__imp_CoTaskMemFree
0x18002ddbf  mov     ecx, ebx; dwErrCode
0x18002ddc1  call    cs:__imp_SetLastError
0x18002ddc7  mov     [rdi], r14
0x18002ddca  mov     qword ptr [rsi], 0
0x18002ddd1  mov     rcx, [rsp+38h+pv]; pv
0x18002ddd6  test    rcx, rcx
0x18002ddd9  jz      short loc_18002DDE1
0x18002dddb  call    cs:__imp_CoTaskMemFree
0x18002dde1  mov     rax, [rdi]
0x18002dde4  mov     rbx, [rsp+38h+arg_8]
0x18002dde9  neg     rax
0x18002ddec  mov     rbp, [rsp+38h+arg_10]
0x18002ddf1  sbb     eax, eax
0x18002ddf3  not     eax
0x18002ddf5  and     eax, 8007000Eh
0x18002ddfa  add     rsp, 20h
0x18002ddfe  pop     r14
0x18002de00  pop     rdi
0x18002de01  pop     rsi
0x18002de02  retn
```
