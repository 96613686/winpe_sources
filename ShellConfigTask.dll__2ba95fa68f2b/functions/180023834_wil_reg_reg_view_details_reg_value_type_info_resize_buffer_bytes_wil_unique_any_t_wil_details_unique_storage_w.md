# wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)

- ea: `0x180023834`
- end: `0x1800238cf`
- name: `?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023160`

## callees

- `0x18000ab14`
- `0x18001233c`
- `0x180023834`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800238ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800238ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023898`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800238a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800238be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800238a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800238be`

## string_xrefs

- `0x180023869`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(LPVOID *a1, unsigned int a2)
{
  unsigned __int64 v3; // rax
  unsigned __int64 v4; // r8
  void *v5; // rdi
  void *v7; // rbp
  DWORD LastError; // ebx
  LPVOID pv[7]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = (unsigned __int64)a2 >> 1;
  v4 = v3 - 1;
  if ( !v3 )
    v4 = 0;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    pv,
    *a1,
    v4);
  v5 = pv[0];
  if ( pv[0] )
  {
    if ( a1 != pv )
    {
      v7 = *a1;
      if ( *a1 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v7);
        SetLastError(LastError);
      }
      *a1 = v5;
      v5 = 0;
    }
    if ( v5 )
      CoTaskMemFree(v5);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32C,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      (const char *)0x8007000ELL,
      0);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180023834  push    rbx
0x180023836  push    rbp
0x180023837  push    rsi
0x180023838  push    rdi
0x180023839  sub     rsp, 38h
0x18002383d  mov     eax, edx
0x18002383f  mov     rsi, rcx
0x180023842  mov     rdx, [rcx]
0x180023845  lea     rcx, [rsp+58h+pv]
0x18002384a  shr     rax, 1
0x18002384d  lea     r8, [rax-1]
0x180023851  cmovz   r8, rax
0x180023855  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002385a  mov     rdi, [rsp+58h+pv]
0x18002385f  test    rdi, rdi
0x180023862  jnz     short loc_180023886
0x180023864  mov     rcx, [rsp+58h]; this
0x180023869  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180023870  mov     ebx, 8007000Eh
0x180023875  mov     edx, 32Ch; void *
0x18002387a  mov     r9d, ebx; char *
0x18002387d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023882  mov     eax, ebx
0x180023884  jmp     short loc_1800238C6
0x180023886  lea     rax, [rsp+58h+pv]
0x18002388b  cmp     rsi, rax
0x18002388e  jz      short loc_1800238B6
0x180023890  mov     rbp, [rsi]
0x180023893  test    rbp, rbp
0x180023896  jz      short loc_1800238B1
0x180023898  call    cs:__imp_GetLastError
0x18002389e  mov     rcx, rbp; pv
0x1800238a1  mov     ebx, eax
0x1800238a3  call    cs:__imp_CoTaskMemFree
0x1800238a9  mov     ecx, ebx; dwErrCode
0x1800238ab  call    cs:__imp_SetLastError
0x1800238b1  mov     [rsi], rdi
0x1800238b4  xor     edi, edi
0x1800238b6  test    rdi, rdi
0x1800238b9  jz      short loc_1800238C4
0x1800238bb  mov     rcx, rdi; pv
0x1800238be  call    cs:__imp_CoTaskMemFree
0x1800238c4  xor     eax, eax
0x1800238c6  add     rsp, 38h
0x1800238ca  pop     rdi
0x1800238cb  pop     rsi
0x1800238cc  pop     rbp
0x1800238cd  pop     rbx
0x1800238ce  retn
```
