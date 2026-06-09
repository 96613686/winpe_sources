# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x18001a8bc`
- end: `0x18001a943`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `135`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015284`
- `0x180015608`

## callees

- `0x18001550c`
- `0x18001a8bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a8f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a91b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a8f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a91b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8ee`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        void **a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  void **v5; // rax
  void **v6; // rsi
  void *v7; // rbp
  void *v8; // r14
  DWORD LastError; // ebx
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v5 = (void **)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &pv,
                  a2,
                  a3,
                  a4);
  v6 = v5;
  if ( a1 != v5 )
  {
    v7 = *a1;
    v8 = *v5;
    if ( *a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v7);
      SetLastError(LastError);
    }
    *a1 = v8;
    *v6 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return *a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18001a8bc  mov     [rsp+arg_8], rbx
0x18001a8c1  mov     [rsp+arg_10], rbp
0x18001a8c6  push    rsi
0x18001a8c7  push    rdi
0x18001a8c8  push    r14
0x18001a8ca  sub     rsp, 20h
0x18001a8ce  mov     rdi, rcx
0x18001a8d1  lea     rcx, [rsp+38h+pv]
0x18001a8d6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001a8db  mov     rsi, rax
0x18001a8de  cmp     rdi, rax
0x18001a8e1  jz      short loc_18001A911
0x18001a8e3  mov     rbp, [rdi]
0x18001a8e6  mov     r14, [rax]
0x18001a8e9  test    rbp, rbp
0x18001a8ec  jz      short loc_18001A907
0x18001a8ee  call    cs:__imp_GetLastError
0x18001a8f4  mov     rcx, rbp; pv
0x18001a8f7  mov     ebx, eax
0x18001a8f9  call    cs:__imp_CoTaskMemFree
0x18001a8ff  mov     ecx, ebx; dwErrCode
0x18001a901  call    cs:__imp_SetLastError
0x18001a907  mov     [rdi], r14
0x18001a90a  mov     qword ptr [rsi], 0
0x18001a911  mov     rcx, [rsp+38h+pv]; pv
0x18001a916  test    rcx, rcx
0x18001a919  jz      short loc_18001A921
0x18001a91b  call    cs:__imp_CoTaskMemFree
0x18001a921  mov     rax, [rdi]
0x18001a924  mov     rbx, [rsp+38h+arg_8]
0x18001a929  neg     rax
0x18001a92c  mov     rbp, [rsp+38h+arg_10]
0x18001a931  sbb     eax, eax
0x18001a933  not     eax
0x18001a935  and     eax, 8007000Eh
0x18001a93a  add     rsp, 20h
0x18001a93e  pop     r14
0x18001a940  pop     rdi
0x18001a941  pop     rsi
0x18001a942  retn
```
