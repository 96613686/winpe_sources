# wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::enumerate_current_index(void)

- ea: `0x1800405b4`
- end: `0x18004074d`
- name: `?enumerate_current_index@?$key_iterator_data@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg@wil@@AEAAJXZ`
- size: `409`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003fa00`

## callees

- `0x18000720c`
- `0x180018dbc`
- `0x180021fa4`
- `0x18003f35c`
- `0x1800405b4`
- `0x180040888`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004067d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004067d`

## string_xrefs

- `0x180040600`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x1800406bf`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18004070c`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18004073b`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::reg::key_iterator_data<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::enumerate_current_index(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  DWORD v5; // eax
  __int64 v6; // rdi
  WCHAR *v8; // r8
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // edi
  unsigned int lpReserved; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD cchName; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 16) == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x606,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      a4);
  v5 = 32;
  if ( *(_DWORD *)(a1 + 24) )
    v5 = *(_DWORD *)(a1 + 24);
  while ( 1 )
  {
    v6 = v5;
    cchName = v5;
    if ( (unsigned __int64)v5 <= *(_QWORD *)(a1 + 24) )
    {
      v6 = *(_QWORD *)(a1 + 24);
    }
    else if ( (int)wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a1, 2 * v5) < 0 )
    {
      *(_QWORD *)(a1 + 24) = 0;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        (const char *)0x8007000ELL,
        lpReserved);
      return 2147942414LL;
    }
    wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      a1,
      v6);
    *(_QWORD *)(a1 + 24) = v6;
    if ( !v6 )
      goto LABEL_7;
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
               (void *)0x646,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
               (const char *)v9,
               lpReserved);
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
  v10 = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a1, 2 * cchName);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x625,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      (const char *)(unsigned int)v10,
      lpReserved);
    return v11;
  }
  *(_QWORD *)(a1 + 24) = cchName;
  return 0;
}

```

## disassembly

```asm
0x1800405b4  mov     [rsp+arg_8], rbx
0x1800405b9  push    rdi
0x1800405ba  sub     rsp, 40h
0x1800405be  cmp     dword ptr [rcx+10h], 0FFFFFFFFh
0x1800405c2  mov     rbx, rcx
0x1800405c5  jz      loc_180040736
0x1800405cb  cmp     dword ptr [rcx+18h], 0
0x1800405cf  mov     eax, 20h ; ' '
0x1800405d4  cmova   eax, [rcx+18h]
0x1800405d8  mov     edi, eax
0x1800405da  mov     [rsp+48h+cchName], eax
0x1800405de  cmp     rdi, [rbx+18h]
0x1800405e2  jbe     short loc_180040626
0x1800405e4  lea     edx, [rax+rax]
0x1800405e7  mov     rcx, rbx
0x1800405ea  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x1800405ef  test    eax, eax
0x1800405f1  jns     short loc_18004062A
0x1800405f3  mov     qword ptr [rbx+18h], 0
0x1800405fb  mov     rcx, [rsp+48h]; this
0x180040600  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180040607  mov     ebx, 8007000Eh
0x18004060c  mov     edx, 60Fh; void *
0x180040611  mov     r9d, ebx; char *
0x180040614  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040619  mov     eax, ebx
0x18004061b  mov     rbx, [rsp+48h+arg_8]
0x180040620  add     rsp, 40h
0x180040624  pop     rdi
0x180040625  retn
0x180040626  mov     rdi, [rbx+18h]
0x18004062a  mov     rdx, rdi
0x18004062d  mov     rcx, rbx
0x180040630  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x180040635  mov     [rbx+18h], rdi
0x180040639  test    rdi, rdi
0x18004063c  jz      short loc_1800405FB
0x18004063e  cmp     [rsp+48h+cchName], 0
0x180040643  jnz     short loc_18004064A
0x180040645  xor     r8d, r8d
0x180040648  jmp     short loc_18004064D
0x18004064a  mov     r8, [rbx]; lpName
0x18004064d  mov     edx, [rbx+10h]; dwIndex
0x180040650  lea     r9, [rsp+48h+cchName]; lpcchName
0x180040655  mov     rcx, [rbx+8]; hKey
0x180040659  mov     [rsp+48h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180040662  mov     [rsp+48h+lpcchClass], 0; lpcchClass
0x18004066b  mov     [rsp+48h+lpClass], 0; lpClass
0x180040674  mov     [rsp+48h+lpReserved], 0; int
0x18004067d  call    cs:__imp_RegEnumKeyExW
0x180040683  test    eax, eax
0x180040685  jz      short loc_1800406ED
0x180040687  cmp     eax, 103h
0x18004068c  jz      short loc_1800406D8
0x18004068e  cmp     eax, 0EAh
0x180040693  jnz     short loc_1800406BA
0x180040695  cmp     [rsp+48h+cchName], 7Fh
0x18004069a  jnb     short loc_1800406A6
0x18004069c  mov     eax, 7Fh
0x1800406a1  jmp     loc_1800405D8
0x1800406a6  cmp     [rsp+48h+cchName], 100h
0x1800406ae  jnb     short loc_18004072F
0x1800406b0  mov     eax, 100h
0x1800406b5  jmp     loc_1800405D8
0x1800406ba  mov     rcx, [rsp+48h]; this
0x1800406bf  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800406c6  mov     r9d, eax; char *
0x1800406c9  mov     edx, 646h; void *
0x1800406ce  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800406d3  jmp     loc_18004061B
0x1800406d8  mov     rdx, [rbx+18h]
0x1800406dc  mov     rcx, rbx
0x1800406df  call    ??$clear_name@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@reg_iterator_details@reg@wil@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@_K@Z; wil::reg::reg_iterator_details::clear_name<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,unsigned __int64)
0x1800406e4  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x1800406eb  jmp     short loc_18004072F
0x1800406ed  mov     edx, [rsp+48h+cchName]
0x1800406f1  mov     rcx, rbx
0x1800406f4  inc     edx
0x1800406f6  mov     [rsp+48h+cchName], edx
0x1800406fa  add     edx, edx
0x1800406fc  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x180040701  mov     edi, eax
0x180040703  test    eax, eax
0x180040705  jns     short loc_180040727
0x180040707  mov     rcx, [rsp+48h]; this
0x18004070c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180040713  mov     r9d, eax; char *
0x180040716  mov     edx, 625h; void *
0x18004071b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040720  mov     eax, edi
0x180040722  jmp     loc_18004061B
0x180040727  mov     eax, [rsp+48h+cchName]
0x18004072b  mov     [rbx+18h], rax
0x18004072f  xor     eax, eax
0x180040731  jmp     loc_18004061B
0x180040736  mov     rcx, [rsp+48h]; this
0x18004073b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180040742  mov     edx, 606h; void *
0x180040747  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
