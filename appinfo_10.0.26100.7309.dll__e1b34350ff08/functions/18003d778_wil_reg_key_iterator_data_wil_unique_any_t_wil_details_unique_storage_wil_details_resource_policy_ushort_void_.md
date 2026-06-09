# wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)

- ea: `0x18003d778`
- end: `0x18003d91f`
- name: `?enumerate_current_index@?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003ccb0`

## callees

- `0x180007c78`
- `0x180018530`
- `0x18001ef78`
- `0x18003c688`
- `0x18003d778`
- `0x18003da6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003d810`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003d810`

## string_xrefs

- `0x18003d869`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18003d89a`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18003d8e1`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18003d90d`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::enumerate_current_index(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  DWORD v5; // eax
  unsigned __int64 v6; // rdi
  DWORD v7; // esi
  WCHAR *v8; // r8
  unsigned int v9; // eax
  int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD cchName; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 16) == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5EC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      a4);
  v5 = 32;
  if ( *(_DWORD *)(a1 + 24) )
    v5 = *(_DWORD *)(a1 + 24);
  while ( 1 )
  {
    v6 = *(_QWORD *)(a1 + 24);
    v7 = v5;
    cchName = v5;
    if ( v5 > v6 )
    {
      if ( (int)wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a1, 2 * v5) < 0 )
      {
        *(_QWORD *)(a1 + 24) = 0;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F5,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
          (const char *)0x8007000ELL,
          v13);
        return 2147942414LL;
      }
      v6 = v7;
    }
    wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      a1,
      v6);
    *(_QWORD *)(a1 + 24) = v6;
    if ( !v6 )
      goto LABEL_19;
    v8 = cchName ? *(WCHAR **)a1 : 0LL;
    v9 = RegEnumKeyExW(*(HKEY *)(a1 + 8), *(_DWORD *)(a1 + 16), v8, &cchName, 0, 0, 0, 0);
    if ( !v9 )
      break;
    if ( v9 == 259 )
    {
      wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        a1,
        *(_QWORD *)(a1 + 24));
      *(_DWORD *)(a1 + 16) = -1;
      return 0;
    }
    if ( v9 != 234 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x62C,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
               (const char *)v9,
               v13);
    if ( cchName >= 0x7F )
    {
      if ( cchName >= 0x100 )
        return 0;
      v5 = 256;
    }
    else
    {
      v5 = 127;
    }
  }
  ++cchName;
  v11 = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a1, 2 * cchName);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      (const char *)(unsigned int)v11,
      v13);
    return v12;
  }
  *(_QWORD *)(a1 + 24) = cchName;
  return 0;
}

```

## disassembly

```asm
0x18003d778  mov     [rsp+arg_8], rbx
0x18003d77d  mov     [rsp+arg_10], rsi
0x18003d782  push    rdi
0x18003d783  sub     rsp, 40h
0x18003d787  cmp     dword ptr [rcx+10h], 0FFFFFFFFh
0x18003d78b  mov     rbx, rcx
0x18003d78e  jz      loc_18003D908
0x18003d794  cmp     dword ptr [rcx+18h], 0
0x18003d798  mov     eax, 20h ; ' '
0x18003d79d  cmova   eax, [rcx+18h]
0x18003d7a1  mov     rdi, [rbx+18h]
0x18003d7a5  mov     esi, eax
0x18003d7a7  mov     [rsp+48h+cchName], eax
0x18003d7ab  cmp     rsi, rdi
0x18003d7ae  jbe     short loc_18003D7C5
0x18003d7b0  lea     edx, [rsi+rsi]
0x18003d7b3  mov     rcx, rbx
0x18003d7b6  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003d7bb  test    eax, eax
0x18003d7bd  js      loc_18003D85F
0x18003d7c3  mov     edi, esi
0x18003d7c5  mov     rdx, rdi
0x18003d7c8  mov     rcx, rbx
0x18003d7cb  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x18003d7d0  mov     [rbx+18h], rdi
0x18003d7d4  test    rdi, rdi
0x18003d7d7  jz      loc_18003D864
0x18003d7dd  cmp     [rsp+48h+cchName], 0
0x18003d7e2  jnz     short loc_18003D7E9
0x18003d7e4  xor     r8d, r8d
0x18003d7e7  jmp     short loc_18003D7EC
0x18003d7e9  mov     r8, [rbx]; lpName
0x18003d7ec  and     [rsp+48h+var_10], 0
0x18003d7f2  lea     r9, [rsp+48h+cchName]; lpcchName
0x18003d7f7  and     [rsp+48h+var_18], 0
0x18003d7fd  and     [rsp+48h+var_20], 0
0x18003d803  mov     edx, [rbx+10h]; dwIndex
0x18003d806  mov     rcx, [rbx+8]; hKey
0x18003d80a  and     [rsp+48h+var_28], 0
0x18003d810  call    cs:__imp_RegEnumKeyExW
0x18003d817  nop     dword ptr [rax+rax+00h]
0x18003d81c  test    eax, eax
0x18003d81e  jz      loc_18003D8C2
0x18003d824  cmp     eax, 103h
0x18003d829  jz      loc_18003D8B0
0x18003d82f  cmp     eax, 0EAh
0x18003d834  jnz     short loc_18003D895
0x18003d836  cmp     [rsp+48h+cchName], 7Fh
0x18003d83b  jnb     short loc_18003D847
0x18003d83d  mov     eax, 7Fh
0x18003d842  jmp     loc_18003D7A1
0x18003d847  cmp     [rsp+48h+cchName], 100h
0x18003d84f  jnb     loc_18003D901
0x18003d855  mov     eax, 100h
0x18003d85a  jmp     loc_18003D7A1
0x18003d85f  and     qword ptr [rbx+18h], 0
0x18003d864  mov     rcx, [rsp+48h]; this
0x18003d869  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003d870  mov     ebx, 8007000Eh
0x18003d875  mov     edx, 5F5h; void *
0x18003d87a  mov     r9d, ebx; char *
0x18003d87d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d882  mov     eax, ebx
0x18003d884  mov     rbx, [rsp+48h+arg_8]
0x18003d889  mov     rsi, [rsp+48h+arg_10]
0x18003d88e  add     rsp, 40h
0x18003d892  pop     rdi
0x18003d893  retn
0x18003d895  mov     rcx, [rsp+48h]; this
0x18003d89a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003d8a1  mov     r9d, eax; char *
0x18003d8a4  mov     edx, 62Ch; void *
0x18003d8a9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003d8ae  jmp     short loc_18003D884
0x18003d8b0  mov     rdx, [rbx+18h]
0x18003d8b4  mov     rcx, rbx
0x18003d8b7  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x18003d8bc  or      dword ptr [rbx+10h], 0FFFFFFFFh
0x18003d8c0  jmp     short loc_18003D901
0x18003d8c2  mov     edx, [rsp+48h+cchName]
0x18003d8c6  mov     rcx, rbx
0x18003d8c9  inc     edx
0x18003d8cb  mov     [rsp+48h+cchName], edx
0x18003d8cf  add     edx, edx
0x18003d8d1  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003d8d6  mov     edi, eax
0x18003d8d8  test    eax, eax
0x18003d8da  jns     short loc_18003D8F9
0x18003d8dc  mov     rcx, [rsp+48h]; this
0x18003d8e1  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003d8e8  mov     r9d, eax; char *
0x18003d8eb  mov     edx, 60Bh; void *
0x18003d8f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d8f5  mov     eax, edi
0x18003d8f7  jmp     short loc_18003D884
0x18003d8f9  mov     eax, [rsp+48h+cchName]
0x18003d8fd  mov     [rbx+18h], rax
0x18003d901  xor     eax, eax
0x18003d903  jmp     loc_18003D884
0x18003d908  mov     rcx, [rsp+48h]; this
0x18003d90d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003d914  mov     edx, 5ECh; void *
0x18003d919  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
