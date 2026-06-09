# OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString(MultiString const &)

- ea: `0x18009fdb4`
- end: `0x1800a00c4`
- name: `??$?0VMultiString@@@MultiString@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBV0@@Z`
- size: `784`
- prototype: `HSTRING *__fastcall(HSTRING *newString, const struct MultiString *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009f950`

## callees

- `0x180025270`
- `0x180036e58`
- `0x18004c6e0`
- `0x180078818`
- `0x180086228`
- `0x18009aae0`
- `0x18009f920`
- `0x18009fdb4`
- `0x1800a0370`
- `0x1800a03c0`
- `0x1800a0400`
- `0x180101090`
- `0x1801011f8`
- `0x180101528`
- `0x18010158c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a0083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a0083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18009fe89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18009fe89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0061`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0061`

## string_xrefs

- `0x18009feb4`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x18009ffc4`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x18009fff0`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800a0019`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800a0049`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800a00b2`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800a009f`: `WindowsCreateString(firstNullTerminator, 1, GetAddressOf())`
- `0x18009fead`: `OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString`
- `0x18009ffbd`: `OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString`
- `0x18009ffe9`: `OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString`
- `0x1800a0012`: `OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString`
- `0x1800a0042`: `OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString`
- `0x1800a00ab`: `OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString`
- `0x18009ffdd`: `StringCchCopy(collectedCharacters + collectedCharacterOffset, collectedCharacterCount - collectedCharacterOffset, GetStringPointer(string))`

## pseudocode

```c
HSTRING *__fastcall OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString(
        HSTRING *newString,
        const struct MultiString *a2)
{
  UINT32 v4; // esi
  OSIntegration::DEH::RegistryCompatibility::Details **v5; // r14
  const unsigned __int16 *v6; // rdx
  UINT32 v7; // ebx
  UINT32 v8; // ecx
  int v9; // eax
  HRESULT v10; // eax
  unsigned int v11; // r14d
  OSIntegration::DEH::RegistryCompatibility::Details **v12; // rbx
  int StringLengthIncluding; // r15d
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *StringPointer; // rax
  int v16; // eax
  unsigned int v17; // edx
  unsigned int v18; // ecx
  int v19; // eax
  HRESULT String; // eax
  char *v22; // [rsp+28h] [rbp-30h]
  int v23[4]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v24[24]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+88h] [rbp+30h]
  HSTRING v26; // [rsp+90h] [rbp+38h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+98h] [rbp+40h] BYREF
  WCHAR *charBuffer; // [rsp+A0h] [rbp+48h] BYREF
  char v29; // [rsp+A8h] [rbp+50h] BYREF

  v26 = (HSTRING)newString;
  *newString = 0;
  v4 = 0;
  begin(v23);
  end(v24, a2);
  if ( !(unsigned __int8)MultiStringIterator::operator!=(v23, v24) )
    goto LABEL_23;
  do
  {
    v5 = (OSIntegration::DEH::RegistryCompatibility::Details **)MultiStringIterator::operator*(v23);
    if ( !OSIntegration::DEH::RegistryCompatibility::Details::GetStringLength(*v5, v6) )
    {
      LODWORD(v22) = -2147024809;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x142,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString",
        "GetStringLength(string) == 0",
        v22,
        v23[0]);
    }
    v7 = v4;
    v8 = OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<unsigned short const *>(v5)
       + v4;
    v9 = -1;
    if ( v8 >= v4 )
      v9 = v8;
    v4 = v9;
    if ( v8 < v7 )
    {
      LODWORD(v22) = v8 < v7 ? 0x80070216 : 0;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString",
        "UInt32Add(collectedCharacterCount, GetStringLengthIncludingTerminator(string), &collectedCharacterCount)",
        v22,
        v23[0]);
    }
    MultiStringIterator::operator++(v23);
  }
  while ( (unsigned __int8)MultiStringIterator::operator!=(v23, v24) );
  if ( v4 )
  {
    charBuffer = 0;
    bufferHandle = 0;
    v10 = WindowsPreallocateStringBuffer(v4, &charBuffer, &bufferHandle);
    if ( v10 < 0 )
    {
      LODWORD(v22) = v10;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x154,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString",
        "WindowsPreallocateStringBuffer(collectedCharacterCount, &collectedCharacters, &multiStringBuffer)",
        v22,
        v23[0]);
    }
    v11 = 0;
    begin(v23);
    end(v24, a2);
    while ( (unsigned __int8)MultiStringIterator::operator!=(v23, v24) )
    {
      v12 = (OSIntegration::DEH::RegistryCompatibility::Details **)MultiStringIterator::operator*(v23);
      StringLengthIncluding = OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<unsigned short const *>(v12);
      StringPointer = OSIntegration::DEH::RegistryCompatibility::Details::GetStringPointer(*v12, v14);
      v16 = StringCchCopyW(&charBuffer[v11], v4 - v11, StringPointer);
      if ( v16 < 0 )
      {
        LODWORD(v22) = v16;
        wil::details::in1diag5::Throw_Hr(
          retaddr,
          (void *)0x15C,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
          "OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString",
          "StringCchCopy(collectedCharacters + collectedCharacterOffset, collectedCharacterCount - collectedCharacterOffs"
          "et, GetStringPointer(string))",
          v22,
          v23[0]);
      }
      v17 = v11;
      v18 = StringLengthIncluding + v11;
      v19 = -1;
      if ( StringLengthIncluding + v11 >= v11 )
        v19 = StringLengthIncluding + v11;
      v11 = v19;
      if ( v18 < v17 )
      {
        LODWORD(v22) = v18 < v17 ? 0x80070216 : 0;
        wil::details::in1diag5::Throw_Hr(
          retaddr,
          (void *)0x15E,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
          "OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString",
          "UInt32Add(collectedCharacterOffset, sourceLength, &collectedCharacterOffset)",
          v22,
          v23[0]);
      }
      MultiStringIterator::operator++(v23);
    }
    v26 = *(HSTRING *)wil::make_hstring_from_buffer(&v29, &bufferHandle);
    Microsoft::WRL::Wrappers::HString::Set(newString, &v26);
    Windows::Internal::String::~String((Windows::Internal::String *)&v29);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
  }
  else
  {
LABEL_23:
    WindowsDeleteString(*newString);
    *newString = 0;
    String = WindowsCreateString(
               &`OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString'::`9'::firstNullTerminator,
               1u,
               newString);
    if ( String < 0 )
    {
      LODWORD(v22) = String;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString",
        "WindowsCreateString(firstNullTerminator, 1, GetAddressOf())",
        v22,
        v23[0]);
    }
  }
  return newString;
}

```

## disassembly

```asm
0x18009fdb4  mov     [rsp-30h+arg_0], rcx
0x18009fdb9  push    rbp
0x18009fdba  push    rbx
0x18009fdbb  push    rsi
0x18009fdbc  push    rdi
0x18009fdbd  push    r14
0x18009fdbf  push    r15
0x18009fdc1  mov     rbp, rsp
0x18009fdc4  sub     rsp, 58h
0x18009fdc8  mov     r15, rdx
0x18009fdcb  mov     rdi, rcx
0x18009fdce  mov     qword ptr [rcx], 0
0x18009fdd5  xor     esi, esi
0x18009fdd7  lea     rcx, [rbp+var_28]
0x18009fddb  call    ?begin@@YA?AVMultiStringIterator@@AEBVMultiString@@@Z; begin(MultiString const &)
0x18009fde0  mov     rdx, r15
0x18009fde3  lea     rcx, [rbp+var_18]
0x18009fde7  call    ?end@@YA?AVMultiStringIterator@@AEBVMultiString@@@Z; end(MultiString const &)
0x18009fdec  lea     rdx, [rbp+var_18]
0x18009fdf0  lea     rcx, [rbp+var_28]
0x18009fdf4  call    ??9MultiStringIterator@@QEBA_NAEBV0@@Z; MultiStringIterator::operator!=(MultiStringIterator const &)
0x18009fdf9  test    al, al
0x18009fdfb  jz      loc_1800A005E
0x18009fe01  lea     rcx, [rbp+var_28]
0x18009fe05  call    ??DMultiStringIterator@@QEBAAEBQEBGXZ; MultiStringIterator::operator*(void)
0x18009fe0a  mov     r14, rax
0x18009fe0d  mov     rbx, [rbp+30h]
0x18009fe11  mov     rcx, [rax]; this
0x18009fe14  call    ?GetStringLength@Details@RegistryCompatibility@DEH@OSIntegration@@YAIPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringLength(ushort const *)
0x18009fe19  test    eax, eax
0x18009fe1b  jz      loc_1800A002E
0x18009fe21  mov     ebx, esi
0x18009fe23  mov     rcx, r14
0x18009fe26  call    ??$GetStringLengthIncludingTerminator@PEBG@Details@RegistryCompatibility@DEH@OSIntegration@@YAIAEBQEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<ushort const *>(ushort const * const &)
0x18009fe2b  lea     ecx, [rax+rsi]
0x18009fe2e  or      eax, 0FFFFFFFFh
0x18009fe31  cmp     ecx, esi
0x18009fe33  cmovnb  eax, ecx
0x18009fe36  mov     esi, eax
0x18009fe38  cmp     ecx, ebx
0x18009fe3a  sbb     eax, eax
0x18009fe3c  and     eax, 80070216h
0x18009fe41  mov     r10, [rbp+30h]
0x18009fe45  cmp     ecx, ebx
0x18009fe47  jb      loc_1800A0002
0x18009fe4d  lea     rcx, [rbp+var_28]
0x18009fe51  call    ??EMultiStringIterator@@QEAAAEAV0@XZ; MultiStringIterator::operator++(void)
0x18009fe56  lea     rdx, [rbp+var_18]
0x18009fe5a  lea     rcx, [rbp+var_28]
0x18009fe5e  call    ??9MultiStringIterator@@QEBA_NAEBV0@@Z; MultiStringIterator::operator!=(MultiStringIterator const &)
0x18009fe63  test    al, al
0x18009fe65  jnz     short loc_18009FE01
0x18009fe67  test    esi, esi
0x18009fe69  jz      loc_1800A005E
0x18009fe6f  mov     [rbp+charBuffer], 0
0x18009fe77  mov     [rbp+bufferHandle], 0
0x18009fe7f  lea     r8, [rbp+bufferHandle]; bufferHandle
0x18009fe83  lea     rdx, [rbp+charBuffer]; charBuffer
0x18009fe87  mov     ecx, esi; length
0x18009fe89  call    cs:__imp_WindowsPreallocateStringBuffer
0x18009fe90  nop     dword ptr [rax+rax+00h]
0x18009fe95  mov     rcx, [rbp+30h]; this
0x18009fe99  test    eax, eax
0x18009fe9b  jns     short loc_18009FEC6
0x18009fe9d  mov     dword ptr [rsp+58h+var_30], eax; char *
0x18009fea1  lea     rax, aWindowspreallo; "WindowsPreallocateStringBuffer(collecte"...
0x18009fea8  mov     [rsp+58h+var_38], rax; char *
0x18009fead  lea     r9, aOsintegrationD_134; "OSIntegration::DEH::RegistryCompatibili"...
0x18009feb4  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009febb  mov     edx, 154h; void *
0x18009fec0  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009fec6  xor     r14d, r14d
0x18009fec9  mov     rdx, r15
0x18009fecc  lea     rcx, [rbp+var_28]
0x18009fed0  call    ?begin@@YA?AVMultiStringIterator@@AEBVMultiString@@@Z; begin(MultiString const &)
0x18009fed5  mov     rdx, r15
0x18009fed8  lea     rcx, [rbp+var_18]
0x18009fedc  call    ?end@@YA?AVMultiStringIterator@@AEBVMultiString@@@Z; end(MultiString const &)
0x18009fee1  jmp     short loc_18009FF53
0x18009fee3  lea     rcx, [rbp+var_28]
0x18009fee7  call    ??DMultiStringIterator@@QEBAAEBQEBGXZ; MultiStringIterator::operator*(void)
0x18009feec  mov     rbx, rax
0x18009feef  mov     rcx, rax
0x18009fef2  call    ??$GetStringLengthIncludingTerminator@PEBG@Details@RegistryCompatibility@DEH@OSIntegration@@YAIAEBQEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<ushort const *>(ushort const * const &)
0x18009fef7  mov     r15d, eax
0x18009fefa  mov     rcx, [rbx]; this
0x18009fefd  call    ?GetStringPointer@Details@RegistryCompatibility@DEH@OSIntegration@@YAPEBGPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringPointer(ushort const *)
0x18009ff02  mov     edx, esi
0x18009ff04  sub     edx, r14d; unsigned __int64
0x18009ff07  mov     r8d, r14d
0x18009ff0a  mov     rcx, [rbp+charBuffer]
0x18009ff0e  lea     rcx, [rcx+r8*2]; unsigned __int16 *
0x18009ff12  mov     r8, rax; unsigned __int16 *
0x18009ff15  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009ff1a  mov     rcx, [rbp+30h]; this
0x18009ff1e  test    eax, eax
0x18009ff20  js      loc_18009FFD9
0x18009ff26  mov     edx, r14d
0x18009ff29  lea     ecx, [r15+r14]
0x18009ff2d  or      eax, 0FFFFFFFFh
0x18009ff30  cmp     ecx, r14d
0x18009ff33  cmovnb  eax, ecx
0x18009ff36  mov     r14d, eax
0x18009ff39  cmp     ecx, edx
0x18009ff3b  sbb     eax, eax
0x18009ff3d  and     eax, 80070216h
0x18009ff42  mov     r10, [rbp+30h]
0x18009ff46  cmp     ecx, edx
0x18009ff48  jb      short loc_18009FFAD
0x18009ff4a  lea     rcx, [rbp+var_28]
0x18009ff4e  call    ??EMultiStringIterator@@QEAAAEAV0@XZ; MultiStringIterator::operator++(void)
0x18009ff53  lea     rdx, [rbp+var_18]
0x18009ff57  lea     rcx, [rbp+var_28]
0x18009ff5b  call    ??9MultiStringIterator@@QEBA_NAEBV0@@Z; MultiStringIterator::operator!=(MultiStringIterator const &)
0x18009ff60  test    al, al
0x18009ff62  jnz     loc_18009FEE3
0x18009ff68  lea     rdx, [rbp+bufferHandle]
0x18009ff6c  lea     rcx, [rbp+arg_18]
0x18009ff70  call    ?make_hstring_from_buffer@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@@Z; wil::make_hstring_from_buffer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&)
0x18009ff75  mov     rcx, [rax]
0x18009ff78  mov     [rbp+arg_0], rcx
0x18009ff7c  lea     rdx, [rbp+arg_0]; HSTRING *
0x18009ff80  mov     rcx, rdi; newString
0x18009ff83  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18009ff88  lea     rcx, [rbp+arg_18]; this
0x18009ff8c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18009ff91  nop
0x18009ff92  lea     rcx, [rbp+bufferHandle]
0x18009ff96  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x18009ff9b  nop
0x18009ff9c  mov     rax, rdi
0x18009ff9f  add     rsp, 58h
0x18009ffa3  pop     r15
0x18009ffa5  pop     r14
0x18009ffa7  pop     rdi
0x18009ffa8  pop     rsi
0x18009ffa9  pop     rbx
0x18009ffaa  pop     rbp
0x18009ffab  retn
0x18009ffad  mov     dword ptr [rsp+58h+var_30], eax; char *
0x18009ffb1  lea     rax, aUint32addColle_1; "UInt32Add(collectedCharacterOffset, sou"...
0x18009ffb8  mov     [rsp+58h+var_38], rax; char *
0x18009ffbd  lea     r9, aOsintegrationD_134; "OSIntegration::DEH::RegistryCompatibili"...
0x18009ffc4  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009ffcb  mov     edx, 15Eh; void *
0x18009ffd0  mov     rcx, r10; this
0x18009ffd3  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009ffd9  mov     dword ptr [rsp+58h+var_30], eax; char *
0x18009ffdd  lea     rax, aStringcchcopyC; "StringCchCopy(collectedCharacters + col"...
0x18009ffe4  mov     [rsp+58h+var_38], rax; char *
0x18009ffe9  lea     r9, aOsintegrationD_134; "OSIntegration::DEH::RegistryCompatibili"...
0x18009fff0  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009fff7  mov     edx, 15Ch; void *
0x18009fffc  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800a0002  mov     dword ptr [rsp+58h+var_30], eax; char *
0x1800a0006  lea     rax, aUint32addColle_2; "UInt32Add(collectedCharacterCount, GetS"...
0x1800a000d  mov     [rsp+58h+var_38], rax; char *
0x1800a0012  lea     r9, aOsintegrationD_134; "OSIntegration::DEH::RegistryCompatibili"...
0x1800a0019  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a0020  mov     edx, 145h; void *
0x1800a0025  mov     rcx, r10; this
0x1800a0028  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800a002e  mov     dword ptr [rsp+58h+var_30], 80070057h; char *
0x1800a0036  lea     rax, aGetstringlengt; "GetStringLength(string) == 0"
0x1800a003d  mov     [rsp+58h+var_38], rax; char *
0x1800a0042  lea     r9, aOsintegrationD_134; "OSIntegration::DEH::RegistryCompatibili"...
0x1800a0049  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a0050  mov     edx, 142h; void *
0x1800a0055  mov     rcx, rbx; this
0x1800a0058  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800a005e  mov     rcx, [rdi]; string
0x1800a0061  call    cs:__imp_WindowsDeleteString
0x1800a0068  nop     dword ptr [rax+rax+00h]
0x1800a006d  mov     qword ptr [rdi], 0
0x1800a0074  mov     r8, rdi; string
0x1800a0077  mov     edx, 1; length
0x1800a007c  lea     rcx, ?firstNullTerminator@?8???$?0VMultiString@@@MultiString@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBV1@@Z@4QBGB; sourceString
0x1800a0083  call    cs:__imp_WindowsCreateString
0x1800a008a  nop     dword ptr [rax+rax+00h]
0x1800a008f  mov     rcx, [rbp+30h]; this
0x1800a0093  test    eax, eax
0x1800a0095  jns     loc_18009FF9C
0x1800a009b  mov     dword ptr [rsp+58h+var_30], eax; char *
0x1800a009f  lea     rax, aWindowscreates; "WindowsCreateString(firstNullTerminator"...
0x1800a00a6  mov     [rsp+58h+var_38], rax; char *
0x1800a00ab  lea     r9, aOsintegrationD_134; "OSIntegration::DEH::RegistryCompatibili"...
0x1800a00b2  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a00b9  mov     edx, 14Dh; void *
0x1800a00be  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
```
