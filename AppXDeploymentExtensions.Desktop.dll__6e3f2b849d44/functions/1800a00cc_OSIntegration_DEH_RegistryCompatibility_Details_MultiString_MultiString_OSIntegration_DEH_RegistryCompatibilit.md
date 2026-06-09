# OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString(OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData const &)

- ea: `0x1800a00cc`
- end: `0x1800a0367`
- name: `??$?0VRegMultiSzValueData@RegistryCompatibility@DEH@OSIntegration@@@MultiString@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVRegMultiSzValueData@234@@Z`
- size: `667`
- prototype: `HSTRING *__fastcall(HSTRING *newString, const struct OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180100cfc`

## callees

- `0x180025270`
- `0x180036e58`
- `0x18004c6e0`
- `0x180064a88`
- `0x180086228`
- `0x18009aae0`
- `0x18009f920`
- `0x1800a00cc`
- `0x1800a0370`
- `0x1800a03c0`
- `0x1800a0400`
- `0x180101090`
- `0x1801011f8`
- `0x180101528`
- `0x18010158c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a033a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a033a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800a01a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800a01a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0318`

## string_xrefs

- `0x1800a01bf`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`
- `0x1800a02bb`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`
- `0x1800a02d3`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`
- `0x1800a02e5`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`
- `0x1800a0300`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`
- `0x1800a0355`: `onecore\admin\appmodel\OSIM\src\deh\WinRT\Collector\RegistryCompatibilityTypes.hpp`

## pseudocode

```c
HSTRING *__fastcall OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString(
        HSTRING *newString,
        const struct OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData *a2)
{
  UINT32 v3; // esi
  char *v4; // r15
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
  int v22[4]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v23[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  HSTRING v25; // [rsp+80h] [rbp+38h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+88h] [rbp+40h] BYREF
  WCHAR *charBuffer; // [rsp+90h] [rbp+48h] BYREF
  char v28; // [rsp+98h] [rbp+50h] BYREF

  v25 = (HSTRING)newString;
  *newString = 0;
  v3 = 0;
  v4 = (char *)a2 + 16;
  begin(v22);
  end(v23, v4);
  if ( !(unsigned __int8)MultiStringIterator::operator!=(v22, v23) )
    goto LABEL_23;
  do
  {
    v5 = (OSIntegration::DEH::RegistryCompatibility::Details **)MultiStringIterator::operator*(v22);
    if ( !OSIntegration::DEH::RegistryCompatibility::Details::GetStringLength(*v5, v6) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x142,
        (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
        (const char *)0x80070057LL,
        v22[0]);
    v7 = v3;
    v8 = OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<unsigned short const *>(v5)
       + v3;
    v9 = -1;
    if ( v8 >= v3 )
      v9 = v8;
    v3 = v9;
    if ( v8 < v7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
        v8 < v7 ? (const char *)0x80070216LL : 0,
        v22[0]);
    MultiStringIterator::operator++(v22);
  }
  while ( (unsigned __int8)MultiStringIterator::operator!=(v22, v23) );
  if ( v3 )
  {
    charBuffer = 0;
    bufferHandle = 0;
    v10 = WindowsPreallocateStringBuffer(v3, &charBuffer, &bufferHandle);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x154,
        (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
        (const char *)(unsigned int)v10,
        v22[0]);
    v11 = 0;
    begin(v22);
    end(v23, v4);
    while ( (unsigned __int8)MultiStringIterator::operator!=(v22, v23) )
    {
      v12 = (OSIntegration::DEH::RegistryCompatibility::Details **)MultiStringIterator::operator*(v22);
      StringLengthIncluding = OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<unsigned short const *>(v12);
      StringPointer = OSIntegration::DEH::RegistryCompatibility::Details::GetStringPointer(*v12, v14);
      v16 = StringCchCopyW(&charBuffer[v11], v3 - v11, StringPointer);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15C,
          (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
          (const char *)(unsigned int)v16,
          v22[0]);
      v17 = v11;
      v18 = StringLengthIncluding + v11;
      v19 = -1;
      if ( StringLengthIncluding + v11 >= v11 )
        v19 = StringLengthIncluding + v11;
      v11 = v19;
      if ( v18 < v17 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15E,
          (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
          v18 < v17 ? (const char *)0x80070216LL : 0,
          v22[0]);
      MultiStringIterator::operator++(v22);
    }
    v25 = *(HSTRING *)wil::make_hstring_from_buffer(&v28, &bufferHandle);
    Microsoft::WRL::Wrappers::HString::Set(newString, &v25);
    Windows::Internal::String::~String((Windows::Internal::String *)&v28);
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
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\WinRT\\Collector\\RegistryCompatibilityTypes.hpp",
        (const char *)(unsigned int)String,
        v22[0]);
  }
  return newString;
}

```

## disassembly

```asm
0x1800a00cc  mov     [rsp-30h+arg_0], rcx
0x1800a00d1  push    rbp
0x1800a00d2  push    rbx
0x1800a00d3  push    rsi
0x1800a00d4  push    rdi
0x1800a00d5  push    r14
0x1800a00d7  push    r15
0x1800a00d9  mov     rbp, rsp
0x1800a00dc  sub     rsp, 48h
0x1800a00e0  mov     rdi, rcx
0x1800a00e3  mov     qword ptr [rcx], 0
0x1800a00ea  xor     esi, esi
0x1800a00ec  lea     r15, [rdx+10h]
0x1800a00f0  mov     rdx, r15
0x1800a00f3  lea     rcx, [rbp+var_28]
0x1800a00f7  call    ?begin@@YA?AVMultiStringIterator@@AEBVMultiString@@@Z; begin(MultiString const &)
0x1800a00fc  mov     rdx, r15
0x1800a00ff  lea     rcx, [rbp+var_18]
0x1800a0103  call    ?end@@YA?AVMultiStringIterator@@AEBVMultiString@@@Z; end(MultiString const &)
0x1800a0108  lea     rdx, [rbp+var_18]
0x1800a010c  lea     rcx, [rbp+var_28]
0x1800a0110  call    ??9MultiStringIterator@@QEBA_NAEBV0@@Z; MultiStringIterator::operator!=(MultiStringIterator const &)
0x1800a0115  test    al, al
0x1800a0117  jz      loc_1800A0315
0x1800a011d  lea     rcx, [rbp+var_28]
0x1800a0121  call    ??DMultiStringIterator@@QEBAAEBQEBGXZ; MultiStringIterator::operator*(void)
0x1800a0126  mov     r14, rax
0x1800a0129  mov     rbx, [rbp+30h]
0x1800a012d  mov     rcx, [rax]; this
0x1800a0130  call    ?GetStringLength@Details@RegistryCompatibility@DEH@OSIntegration@@YAIPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringLength(ushort const *)
0x1800a0135  test    eax, eax
0x1800a0137  jz      loc_1800A02FA
0x1800a013d  mov     ebx, esi
0x1800a013f  mov     rcx, r14
0x1800a0142  call    ??$GetStringLengthIncludingTerminator@PEBG@Details@RegistryCompatibility@DEH@OSIntegration@@YAIAEBQEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<ushort const *>(ushort const * const &)
0x1800a0147  lea     ecx, [rax+rsi]
0x1800a014a  or      eax, 0FFFFFFFFh
0x1800a014d  cmp     ecx, esi
0x1800a014f  cmovnb  eax, ecx
0x1800a0152  mov     esi, eax
0x1800a0154  cmp     ecx, ebx
0x1800a0156  sbb     r9d, r9d
0x1800a0159  and     r9d, 80070216h; char *
0x1800a0160  mov     rax, [rbp+30h]
0x1800a0164  cmp     ecx, ebx
0x1800a0166  jb      loc_1800A02E5
0x1800a016c  lea     rcx, [rbp+var_28]
0x1800a0170  call    ??EMultiStringIterator@@QEAAAEAV0@XZ; MultiStringIterator::operator++(void)
0x1800a0175  lea     rdx, [rbp+var_18]
0x1800a0179  lea     rcx, [rbp+var_28]
0x1800a017d  call    ??9MultiStringIterator@@QEBA_NAEBV0@@Z; MultiStringIterator::operator!=(MultiStringIterator const &)
0x1800a0182  test    al, al
0x1800a0184  jnz     short loc_1800A011D
0x1800a0186  test    esi, esi
0x1800a0188  jz      loc_1800A0315
0x1800a018e  mov     [rbp+charBuffer], 0
0x1800a0196  mov     [rbp+bufferHandle], 0
0x1800a019e  lea     r8, [rbp+bufferHandle]; bufferHandle
0x1800a01a2  lea     rdx, [rbp+charBuffer]; charBuffer
0x1800a01a6  mov     ecx, esi; length
0x1800a01a8  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800a01af  nop     dword ptr [rax+rax+00h]
0x1800a01b4  mov     rcx, [rbp+30h]; this
0x1800a01b8  test    eax, eax
0x1800a01ba  jns     short loc_1800A01D1
0x1800a01bc  mov     r9d, eax; char *
0x1800a01bf  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x1800a01c6  mov     edx, 154h; void *
0x1800a01cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a01d1  xor     r14d, r14d
0x1800a01d4  mov     rdx, r15
0x1800a01d7  lea     rcx, [rbp+var_28]
0x1800a01db  call    ?begin@@YA?AVMultiStringIterator@@AEBVMultiString@@@Z; begin(MultiString const &)
0x1800a01e0  mov     rdx, r15
0x1800a01e3  lea     rcx, [rbp+var_18]
0x1800a01e7  call    ?end@@YA?AVMultiStringIterator@@AEBVMultiString@@@Z; end(MultiString const &)
0x1800a01ec  jmp     short loc_1800A0261
0x1800a01ee  lea     rcx, [rbp+var_28]
0x1800a01f2  call    ??DMultiStringIterator@@QEBAAEBQEBGXZ; MultiStringIterator::operator*(void)
0x1800a01f7  mov     rbx, rax
0x1800a01fa  mov     rcx, rax
0x1800a01fd  call    ??$GetStringLengthIncludingTerminator@PEBG@Details@RegistryCompatibility@DEH@OSIntegration@@YAIAEBQEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringLengthIncludingTerminator<ushort const *>(ushort const * const &)
0x1800a0202  mov     r15d, eax
0x1800a0205  mov     rcx, [rbx]; this
0x1800a0208  call    ?GetStringPointer@Details@RegistryCompatibility@DEH@OSIntegration@@YAPEBGPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringPointer(ushort const *)
0x1800a020d  mov     edx, esi
0x1800a020f  sub     edx, r14d; unsigned __int64
0x1800a0212  mov     r8d, r14d
0x1800a0215  mov     rcx, [rbp+charBuffer]
0x1800a0219  lea     rcx, [rcx+r8*2]; unsigned __int16 *
0x1800a021d  mov     r8, rax; unsigned __int16 *
0x1800a0220  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a0225  mov     rcx, [rbp+30h]; this
0x1800a0229  test    eax, eax
0x1800a022b  js      loc_1800A02D0
0x1800a0231  mov     edx, r14d
0x1800a0234  lea     ecx, [r15+r14]
0x1800a0238  or      eax, 0FFFFFFFFh
0x1800a023b  cmp     ecx, r14d
0x1800a023e  cmovnb  eax, ecx
0x1800a0241  mov     r14d, eax
0x1800a0244  cmp     ecx, edx
0x1800a0246  sbb     r9d, r9d
0x1800a0249  and     r9d, 80070216h; char *
0x1800a0250  mov     rax, [rbp+30h]
0x1800a0254  cmp     ecx, edx
0x1800a0256  jb      short loc_1800A02BB
0x1800a0258  lea     rcx, [rbp+var_28]
0x1800a025c  call    ??EMultiStringIterator@@QEAAAEAV0@XZ; MultiStringIterator::operator++(void)
0x1800a0261  lea     rdx, [rbp+var_18]
0x1800a0265  lea     rcx, [rbp+var_28]
0x1800a0269  call    ??9MultiStringIterator@@QEBA_NAEBV0@@Z; MultiStringIterator::operator!=(MultiStringIterator const &)
0x1800a026e  test    al, al
0x1800a0270  jnz     loc_1800A01EE
0x1800a0276  lea     rdx, [rbp+bufferHandle]
0x1800a027a  lea     rcx, [rbp+arg_18]
0x1800a027e  call    ?make_hstring_from_buffer@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@@Z; wil::make_hstring_from_buffer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&)
0x1800a0283  mov     rcx, [rax]
0x1800a0286  mov     [rbp+arg_0], rcx
0x1800a028a  lea     rdx, [rbp+arg_0]; HSTRING *
0x1800a028e  mov     rcx, rdi; newString
0x1800a0291  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800a0296  lea     rcx, [rbp+arg_18]; this
0x1800a029a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a029f  nop
0x1800a02a0  lea     rcx, [rbp+bufferHandle]
0x1800a02a4  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x1800a02a9  nop
0x1800a02aa  mov     rax, rdi
0x1800a02ad  add     rsp, 48h
0x1800a02b1  pop     r15
0x1800a02b3  pop     r14
0x1800a02b5  pop     rdi
0x1800a02b6  pop     rsi
0x1800a02b7  pop     rbx
0x1800a02b8  pop     rbp
0x1800a02b9  retn
0x1800a02bb  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x1800a02c2  mov     edx, 15Eh; void *
0x1800a02c7  mov     rcx, rax; this
0x1800a02ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a02d0  mov     r9d, eax; char *
0x1800a02d3  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x1800a02da  mov     edx, 15Ch; void *
0x1800a02df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a02e5  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x1800a02ec  mov     edx, 145h; void *
0x1800a02f1  mov     rcx, rax; this
0x1800a02f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a02fa  mov     r9d, 80070057h; char *
0x1800a0300  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x1800a0307  mov     edx, 142h; void *
0x1800a030c  mov     rcx, rbx; this
0x1800a030f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a0315  mov     rcx, [rdi]; string
0x1800a0318  call    cs:__imp_WindowsDeleteString
0x1800a031f  nop     dword ptr [rax+rax+00h]
0x1800a0324  mov     qword ptr [rdi], 0
0x1800a032b  mov     r8, rdi; string
0x1800a032e  mov     edx, 1; length
0x1800a0333  lea     rcx, ?firstNullTerminator@?8???$?0VRegMultiSzValueData@RegistryCompatibility@DEH@OSIntegration@@@MultiString@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVRegMultiSzValueData@345@@Z@4QBGB; sourceString
0x1800a033a  call    cs:__imp_WindowsCreateString
0x1800a0341  nop     dword ptr [rax+rax+00h]
0x1800a0346  mov     rcx, [rbp+30h]; this
0x1800a034a  test    eax, eax
0x1800a034c  jns     loc_1800A02AA
0x1800a0352  mov     r9d, eax; char *
0x1800a0355  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x1800a035c  mov     edx, 14Dh; void *
0x1800a0361  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
