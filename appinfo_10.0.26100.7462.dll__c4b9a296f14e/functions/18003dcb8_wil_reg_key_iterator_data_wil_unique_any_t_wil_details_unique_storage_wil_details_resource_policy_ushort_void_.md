# wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)

- ea: `0x18003dcb8`
- end: `0x18003de5f`
- name: `?enumerate_current_index@?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003d1f0`

## callees

- `0x180007c78`
- `0x180018530`
- `0x18001ef78`
- `0x18003cbc8`
- `0x18003dcb8`
- `0x18003dfac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003dd50`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003dd50`

## string_xrefs

- `0x18003dda9`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18003ddda`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18003de21`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18003de4d`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

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
0x18003dcb8  mov     [rsp+arg_8], rbx
0x18003dcbd  mov     [rsp+arg_10], rsi
0x18003dcc2  push    rdi
0x18003dcc3  sub     rsp, 40h
0x18003dcc7  cmp     dword ptr [rcx+10h], 0FFFFFFFFh
0x18003dccb  mov     rbx, rcx
0x18003dcce  jz      loc_18003DE48
0x18003dcd4  cmp     dword ptr [rcx+18h], 0
0x18003dcd8  mov     eax, 20h ; ' '
0x18003dcdd  cmova   eax, [rcx+18h]
0x18003dce1  mov     rdi, [rbx+18h]
0x18003dce5  mov     esi, eax
0x18003dce7  mov     [rsp+48h+cchName], eax
0x18003dceb  cmp     rsi, rdi
0x18003dcee  jbe     short loc_18003DD05
0x18003dcf0  lea     edx, [rsi+rsi]
0x18003dcf3  mov     rcx, rbx
0x18003dcf6  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003dcfb  test    eax, eax
0x18003dcfd  js      loc_18003DD9F
0x18003dd03  mov     edi, esi
0x18003dd05  mov     rdx, rdi
0x18003dd08  mov     rcx, rbx
0x18003dd0b  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x18003dd10  mov     [rbx+18h], rdi
0x18003dd14  test    rdi, rdi
0x18003dd17  jz      loc_18003DDA4
0x18003dd1d  cmp     [rsp+48h+cchName], 0
0x18003dd22  jnz     short loc_18003DD29
0x18003dd24  xor     r8d, r8d
0x18003dd27  jmp     short loc_18003DD2C
0x18003dd29  mov     r8, [rbx]; lpName
0x18003dd2c  and     [rsp+48h+var_10], 0
0x18003dd32  lea     r9, [rsp+48h+cchName]; lpcchName
0x18003dd37  and     [rsp+48h+var_18], 0
0x18003dd3d  and     [rsp+48h+var_20], 0
0x18003dd43  mov     edx, [rbx+10h]; dwIndex
0x18003dd46  mov     rcx, [rbx+8]; hKey
0x18003dd4a  and     [rsp+48h+var_28], 0
0x18003dd50  call    cs:__imp_RegEnumKeyExW
0x18003dd57  nop     dword ptr [rax+rax+00h]
0x18003dd5c  test    eax, eax
0x18003dd5e  jz      loc_18003DE02
0x18003dd64  cmp     eax, 103h
0x18003dd69  jz      loc_18003DDF0
0x18003dd6f  cmp     eax, 0EAh
0x18003dd74  jnz     short loc_18003DDD5
0x18003dd76  cmp     [rsp+48h+cchName], 7Fh
0x18003dd7b  jnb     short loc_18003DD87
0x18003dd7d  mov     eax, 7Fh
0x18003dd82  jmp     loc_18003DCE1
0x18003dd87  cmp     [rsp+48h+cchName], 100h
0x18003dd8f  jnb     loc_18003DE41
0x18003dd95  mov     eax, 100h
0x18003dd9a  jmp     loc_18003DCE1
0x18003dd9f  and     qword ptr [rbx+18h], 0
0x18003dda4  mov     rcx, [rsp+48h]; this
0x18003dda9  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003ddb0  mov     ebx, 8007000Eh
0x18003ddb5  mov     edx, 5F5h; void *
0x18003ddba  mov     r9d, ebx; char *
0x18003ddbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ddc2  mov     eax, ebx
0x18003ddc4  mov     rbx, [rsp+48h+arg_8]
0x18003ddc9  mov     rsi, [rsp+48h+arg_10]
0x18003ddce  add     rsp, 40h
0x18003ddd2  pop     rdi
0x18003ddd3  retn
0x18003ddd5  mov     rcx, [rsp+48h]; this
0x18003ddda  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003dde1  mov     r9d, eax; char *
0x18003dde4  mov     edx, 62Ch; void *
0x18003dde9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003ddee  jmp     short loc_18003DDC4
0x18003ddf0  mov     rdx, [rbx+18h]
0x18003ddf4  mov     rcx, rbx
0x18003ddf7  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x18003ddfc  or      dword ptr [rbx+10h], 0FFFFFFFFh
0x18003de00  jmp     short loc_18003DE41
0x18003de02  mov     edx, [rsp+48h+cchName]
0x18003de06  mov     rcx, rbx
0x18003de09  inc     edx
0x18003de0b  mov     [rsp+48h+cchName], edx
0x18003de0f  add     edx, edx
0x18003de11  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003de16  mov     edi, eax
0x18003de18  test    eax, eax
0x18003de1a  jns     short loc_18003DE39
0x18003de1c  mov     rcx, [rsp+48h]; this
0x18003de21  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003de28  mov     r9d, eax; char *
0x18003de2b  mov     edx, 60Bh; void *
0x18003de30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003de35  mov     eax, edi
0x18003de37  jmp     short loc_18003DDC4
0x18003de39  mov     eax, [rsp+48h+cchName]
0x18003de3d  mov     [rbx+18h], rax
0x18003de41  xor     eax, eax
0x18003de43  jmp     loc_18003DDC4
0x18003de48  mov     rcx, [rsp+48h]; this
0x18003de4d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003de54  mov     edx, 5ECh; void *
0x18003de59  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
