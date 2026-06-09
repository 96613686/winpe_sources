# OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18008f988`
- end: `0x18008fbc0`
- name: `??$?0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@MultiString@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(HSTRING *newString)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180064ae0`

## callees

- `0x180025270`
- `0x180036e58`
- `0x18004c6e0`
- `0x180064a4c`
- `0x180064a88`
- `0x180086228`
- `0x18008f988`
- `0x18008fbc8`
- `0x18009aae0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008fb93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008fb93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18008fa32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18008fa32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008fb71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008fb71`

## string_xrefs

- `0x18008fa49`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`
- `0x18008fb14`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`
- `0x18008fb2c`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`
- `0x18008fb3e`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`
- `0x18008fb59`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`
- `0x18008fbae`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HSTRING *__fastcall OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString(
        HSTRING *newString,
        __int64 *a2)
{
  UINT32 v4; // r15d
  __int64 v5; // rsi
  __int64 v6; // r12
  UINT32 v7; // ebx
  UINT32 v8; // ecx
  UINT32 v9; // eax
  HRESULT v10; // eax
  unsigned int v11; // esi
  __int64 v12; // rbx
  __int64 v13; // r14
  const unsigned __int16 *v14; // r8
  int v15; // eax
  int v16; // r10d
  unsigned int v17; // edx
  unsigned int v18; // ecx
  int v19; // eax
  HRESULT String; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  HSTRING v24; // [rsp+60h] [rbp+40h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+68h] [rbp+48h] BYREF
  WCHAR *charBuffer; // [rsp+70h] [rbp+50h] BYREF
  char v27; // [rsp+78h] [rbp+58h] BYREF

  v24 = (HSTRING)newString;
  *newString = 0;
  v4 = 0;
  v5 = *a2;
  v6 = a2[1];
  if ( *a2 == v6 )
    goto LABEL_26;
  do
  {
    if ( !(unsigned int)OSIntegration::DEH::RegistryCompatibility::Details::GetStringLength(v5) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x142,
        (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
        (const char *)0x80070057LL,
        savedregs);
    v7 = v4;
    v8 = OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<std::wstring>(v5) + v4;
    v9 = -1;
    if ( v8 >= v4 )
      v9 = v8;
    v4 = v9;
    if ( v8 < v7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
        v8 < v7 ? (const char *)0x80070216LL : 0,
        savedregs);
    v5 += 32;
  }
  while ( v5 != v6 );
  if ( !v9 )
  {
LABEL_26:
    WindowsDeleteString(*newString);
    *newString = 0;
    String = WindowsCreateString(
               &`OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString'::`9'::firstNullTerminator,
               1u,
               newString);
    if ( String < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
        (const char *)(unsigned int)String,
        savedregs);
  }
  else
  {
    charBuffer = 0;
    bufferHandle = 0;
    v10 = WindowsPreallocateStringBuffer(v9, &charBuffer, &bufferHandle);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x154,
        (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
        (const char *)(unsigned int)v10,
        savedregs);
    v11 = 0;
    v12 = *a2;
    v13 = a2[1];
    while ( v12 != v13 )
    {
      OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<std::wstring>(v12);
      if ( *(_QWORD *)(v12 + 24) <= 7u )
        v14 = (const unsigned __int16 *)v12;
      else
        v14 = *(const unsigned __int16 **)v12;
      v15 = StringCchCopyW(&charBuffer[v11], v4 - v11, v14);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15C,
          (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
          (const char *)(unsigned int)v15,
          savedregs);
      v17 = v11;
      v18 = v16 + v11;
      v19 = -1;
      if ( v16 + v11 >= v11 )
        v19 = v16 + v11;
      v11 = v19;
      if ( v18 < v17 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15E,
          (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
          v18 < v17 ? (const char *)0x80070216LL : 0,
          savedregs);
      v12 += 32;
    }
    v24 = *(HSTRING *)wil::make_hstring_from_buffer(&v27, &bufferHandle);
    Microsoft::WRL::Wrappers::HString::Set(newString, &v24);
    Windows::Internal::String::~String((Windows::Internal::String *)&v27);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
  }
  return newString;
}

```

## disassembly

```asm
0x18008f988  mov     [rsp-38h+arg_0], rcx
0x18008f98d  push    rbp
0x18008f98e  push    rbx
0x18008f98f  push    rsi
0x18008f990  push    rdi
0x18008f991  push    r12
0x18008f993  push    r14
0x18008f995  push    r15; int
0x18008f997  mov     rbp, rsp
0x18008f99a  sub     rsp, 20h
0x18008f99e  mov     r14, rdx
0x18008f9a1  mov     rdi, rcx
0x18008f9a4  mov     qword ptr [rcx], 0
0x18008f9ab  xor     r15d, r15d
0x18008f9ae  mov     rsi, [rdx]
0x18008f9b1  mov     r12, [rdx+8]
0x18008f9b5  cmp     rsi, r12
0x18008f9b8  jz      loc_18008FB6E
0x18008f9be  mov     rbx, [rbp+38h]
0x18008f9c2  mov     rcx, rsi
0x18008f9c5  call    ?GetStringLength@Details@RegistryCompatibility@DEH@OSIntegration@@YAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringLength(std::wstring const &)
0x18008f9ca  test    eax, eax
0x18008f9cc  jz      loc_18008FB53
0x18008f9d2  mov     ebx, r15d
0x18008f9d5  mov     rcx, rsi
0x18008f9d8  call    ??$GetStringLengthIncludingTerminator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@RegistryCompatibility@DEH@OSIntegration@@YAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<std::wstring>(std::wstring const &)
0x18008f9dd  lea     ecx, [rax+r15]
0x18008f9e1  or      eax, 0FFFFFFFFh
0x18008f9e4  cmp     ecx, r15d
0x18008f9e7  cmovnb  eax, ecx
0x18008f9ea  mov     r15d, eax
0x18008f9ed  cmp     ecx, ebx
0x18008f9ef  sbb     r9d, r9d
0x18008f9f2  and     r9d, 80070216h; char *
0x18008f9f9  mov     rax, [rbp+38h]
0x18008f9fd  cmp     ecx, ebx
0x18008f9ff  jb      loc_18008FB3E
0x18008fa05  add     rsi, 20h ; ' '
0x18008fa09  cmp     rsi, r12
0x18008fa0c  jnz     short loc_18008F9BE
0x18008fa0e  test    r15d, r15d
0x18008fa11  jz      loc_18008FB6E
0x18008fa17  mov     [rbp+charBuffer], 0
0x18008fa1f  mov     [rbp+bufferHandle], 0
0x18008fa27  lea     r8, [rbp+bufferHandle]; bufferHandle
0x18008fa2b  lea     rdx, [rbp+charBuffer]; charBuffer
0x18008fa2f  mov     ecx, r15d; length
0x18008fa32  call    cs:__imp_WindowsPreallocateStringBuffer
0x18008fa39  nop     dword ptr [rax+rax+00h]
0x18008fa3e  mov     rcx, [rbp+38h]; this
0x18008fa42  test    eax, eax
0x18008fa44  jns     short loc_18008FA5B
0x18008fa46  mov     r9d, eax; char *
0x18008fa49  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x18008fa50  mov     edx, 154h; void *
0x18008fa55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008fa5b  xor     esi, esi
0x18008fa5d  mov     rbx, [r14]
0x18008fa60  mov     r14, [r14+8]
0x18008fa64  jmp     short loc_18008FAC8
0x18008fa66  mov     rcx, rbx
0x18008fa69  call    ??$GetStringLengthIncludingTerminator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@RegistryCompatibility@DEH@OSIntegration@@YAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<std::wstring>(std::wstring const &)
0x18008fa6e  mov     r10d, eax
0x18008fa71  cmp     qword ptr [rbx+18h], 7
0x18008fa76  jbe     short loc_18008FA7D
0x18008fa78  mov     r8, [rbx]
0x18008fa7b  jmp     short loc_18008FA80
0x18008fa7d  mov     r8, rbx; unsigned __int16 *
0x18008fa80  mov     edx, r15d
0x18008fa83  sub     edx, esi; unsigned __int64
0x18008fa85  mov     ecx, esi
0x18008fa87  mov     rax, [rbp+charBuffer]
0x18008fa8b  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x18008fa8f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008fa94  mov     rcx, [rbp+38h]; this
0x18008fa98  test    eax, eax
0x18008fa9a  js      loc_18008FB29
0x18008faa0  mov     edx, esi
0x18008faa2  lea     ecx, [r10+rsi]
0x18008faa6  or      eax, 0FFFFFFFFh
0x18008faa9  cmp     ecx, esi
0x18008faab  cmovnb  eax, ecx
0x18008faae  mov     esi, eax
0x18008fab0  cmp     ecx, edx
0x18008fab2  sbb     r9d, r9d
0x18008fab5  and     r9d, 80070216h; char *
0x18008fabc  mov     rax, [rbp+38h]
0x18008fac0  cmp     ecx, edx
0x18008fac2  jb      short loc_18008FB14
0x18008fac4  add     rbx, 20h ; ' '
0x18008fac8  cmp     rbx, r14
0x18008facb  jnz     short loc_18008FA66
0x18008facd  lea     rdx, [rbp+bufferHandle]
0x18008fad1  lea     rcx, [rbp+arg_18]
0x18008fad5  call    ?make_hstring_from_buffer@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@@Z; wil::make_hstring_from_buffer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&)
0x18008fada  mov     rcx, [rax]
0x18008fadd  mov     [rbp+arg_0], rcx
0x18008fae1  lea     rdx, [rbp+arg_0]; HSTRING *
0x18008fae5  mov     rcx, rdi; newString
0x18008fae8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18008faed  lea     rcx, [rbp+arg_18]; this
0x18008faf1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18008faf6  nop
0x18008faf7  lea     rcx, [rbp+bufferHandle]
0x18008fafb  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x18008fb00  nop
0x18008fb01  mov     rax, rdi
0x18008fb04  add     rsp, 20h
0x18008fb08  pop     r15
0x18008fb0a  pop     r14
0x18008fb0c  pop     r12
0x18008fb0e  pop     rdi
0x18008fb0f  pop     rsi
0x18008fb10  pop     rbx
0x18008fb11  pop     rbp
0x18008fb12  retn
0x18008fb14  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x18008fb1b  mov     edx, 15Eh; void *
0x18008fb20  mov     rcx, rax; this
0x18008fb23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008fb29  mov     r9d, eax; char *
0x18008fb2c  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x18008fb33  mov     edx, 15Ch; void *
0x18008fb38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008fb3e  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x18008fb45  mov     edx, 145h; void *
0x18008fb4a  mov     rcx, rax; this
0x18008fb4d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008fb53  mov     r9d, 80070057h; char *
0x18008fb59  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x18008fb60  mov     edx, 142h; void *
0x18008fb65  mov     rcx, rbx; this
0x18008fb68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008fb6e  mov     rcx, [rdi]; string
0x18008fb71  call    cs:__imp_WindowsDeleteString
0x18008fb78  nop     dword ptr [rax+rax+00h]
0x18008fb7d  mov     qword ptr [rdi], 0
0x18008fb84  mov     r8, rdi; string
0x18008fb87  mov     edx, 1; length
0x18008fb8c  lea     rcx, ?firstNullTerminator@?8???$?0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@MultiString@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z@4QBGB; sourceString
0x18008fb93  call    cs:__imp_WindowsCreateString
0x18008fb9a  nop     dword ptr [rax+rax+00h]
0x18008fb9f  mov     rcx, [rbp+38h]; this
0x18008fba3  test    eax, eax
0x18008fba5  jns     loc_18008FB01
0x18008fbab  mov     r9d, eax; char *
0x18008fbae  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x18008fbb5  mov     edx, 14Dh; void *
0x18008fbba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
