# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x180005678`
- end: `0x180005701`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003c7a8`

## callees

- `0x180005678`
- `0x180006a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800056f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800056f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800056be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800056f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800056be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800056f1`

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
0x180005678  mov     [rsp+arg_8], rbx
0x18000567d  mov     [rsp+arg_10], rbp
0x180005682  push    rsi
0x180005683  push    rdi
0x180005684  push    r14
0x180005686  sub     rsp, 20h
0x18000568a  mov     rdi, rcx
0x18000568d  lea     rcx, [rsp+38h+pv]
0x180005692  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180005697  mov     rsi, rax
0x18000569a  cmp     rdi, rax
0x18000569d  jz      short loc_1800056B4
0x18000569f  mov     rbp, [rdi]
0x1800056a2  mov     r14, [rax]
0x1800056a5  test    rbp, rbp
0x1800056a8  jnz     short loc_1800056E6
0x1800056aa  mov     [rdi], r14
0x1800056ad  mov     qword ptr [rsi], 0
0x1800056b4  mov     rcx, [rsp+38h+pv]; pv
0x1800056b9  test    rcx, rcx
0x1800056bc  jz      short loc_1800056C4
0x1800056be  call    cs:__imp_CoTaskMemFree
0x1800056c4  mov     rax, [rdi]
0x1800056c7  mov     rbx, [rsp+38h+arg_8]
0x1800056cc  neg     rax
0x1800056cf  mov     rbp, [rsp+38h+arg_10]
0x1800056d4  sbb     eax, eax
0x1800056d6  not     eax
0x1800056d8  and     eax, 8007000Eh
0x1800056dd  add     rsp, 20h
0x1800056e1  pop     r14
0x1800056e3  pop     rdi
0x1800056e4  pop     rsi
0x1800056e5  retn
0x1800056e6  call    cs:__imp_GetLastError
0x1800056ec  mov     rcx, rbp; pv
0x1800056ef  mov     ebx, eax
0x1800056f1  call    cs:__imp_CoTaskMemFree
0x1800056f7  mov     ecx, ebx; dwErrCode
0x1800056f9  call    cs:__imp_SetLastError
0x1800056ff  jmp     short loc_1800056AA
```
