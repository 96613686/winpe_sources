# StructuredQuery1::LeafCondition::Save(IXMLDOMNode *)

- ea: `0x1800659c0`
- end: `0x180065bf5`
- name: `?Save@LeafCondition@StructuredQuery1@@UEAAJPEAUIXMLDOMNode@@@Z`
- size: `565`
- prototype: `__int64 __fastcall(StructuredQuery1::LeafCondition *__hidden this, struct IXMLDOMNode *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180010904`
- `0x180015a40`
- `0x1800411e4`
- `0x1800655b0`
- `0x1800659c0`
- `0x180073fdc`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065a3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065a3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065bc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065bc2`
- `PROPSYS!PropVariantToStringAlloc` at `0x180065b4e`
- `PROPSYS!PropVariantToStringAlloc` at `0x180065b4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StructuredQuery1::LeafCondition::Save(StructuredQuery1::LeafCondition *this, struct IXMLDOMNode *a2)
{
  int ConditionPropertyNameFromKey; // ebx
  wchar_t **v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rcx
  wchar_t *v8; // rdi
  unsigned int i; // eax
  unsigned int j; // eax
  const wchar_t *v11; // r8
  const wchar_t *v12; // r8
  struct IXMLDOMElement *v14; // [rsp+50h] [rbp+30h] BYREF
  PWSTR ppszOut; // [rsp+60h] [rbp+40h] BYREF
  struct _RTL_CRITICAL_SECTION *v16; // [rsp+68h] [rbp+48h] BYREF

  ConditionPropertyNameFromKey = StructuredQuery1::BaseCondition::Save(this, a2);
  if ( ConditionPropertyNameFromKey >= 0 )
  {
    v14 = 0;
    ConditionPropertyNameFromKey = ((__int64 (__fastcall *)(struct IXMLDOMNode *, GUID *, struct IXMLDOMElement **))a2->lpVtbl->QueryInterface)(
                                     a2,
                                     &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
                                     &v14);
    if ( ConditionPropertyNameFromKey >= 0 )
    {
      ConditionPropertyNameFromKey = XmlAddStringAttribute(L"type", v14, L"leafCondition");
      if ( ConditionPropertyNameFromKey >= 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
        v16 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 120);
        ppszOut = 0;
        ConditionPropertyNameFromKey = StructuredQuery1::GetConditionPropertyNameFromKey(
                                         (PROPERTYKEY *)((char *)this + 32),
                                         (const struct _tagpropertykey *)&ppszOut,
                                         v5);
        if ( ConditionPropertyNameFromKey >= 0 )
        {
          v8 = ppszOut;
          if ( ppszOut
            || (ConditionPropertyNameFromKey = _AllocString<CTCoAllocPolicy>(v7, v6, &cchOriginalDestLength, &ppszOut),
                v8 = ppszOut,
                ConditionPropertyNameFromKey >= 0) )
          {
            ConditionPropertyNameFromKey = XmlAddStringAttribute(L"property", v14, v8);
            if ( ConditionPropertyNameFromKey >= 0 )
            {
              for ( i = 0; ; ++i )
              {
                ConditionPropertyNameFromKey = -2147418113;
                if ( i >= 0xF )
                  break;
                if ( dword_1800970B8[4 * i] == *((_DWORD *)this + 13) )
                {
                  ConditionPropertyNameFromKey = XmlAddStringAttribute(L"operator", v14, (&off_1800970B0)[2 * i]);
                  if ( ConditionPropertyNameFromKey >= 0 )
                  {
                    for ( j = 0; ; ++j )
                    {
                      if ( j >= 0x13 )
                      {
                        ConditionPropertyNameFromKey = -2147467259;
                        goto LABEL_26;
                      }
                      if ( word_180096F68[8 * j] == *((_WORD *)this + 28) )
                        break;
                    }
                    ConditionPropertyNameFromKey = XmlAddStringAttribute(
                                                     L"propertyType",
                                                     v14,
                                                     *((const wchar_t **)&c_pttovtt + 2 * (int)j));
                    if ( ConditionPropertyNameFromKey >= 0 )
                    {
                      ppszOut = 0;
                      ConditionPropertyNameFromKey = PropVariantToStringAlloc(
                                                       (const PROPVARIANT *const)this + 7,
                                                       &ppszOut);
                      if ( ConditionPropertyNameFromKey >= 0 )
                      {
                        ConditionPropertyNameFromKey = XmlAddStringAttribute(L"value", v14, ppszOut);
                        if ( ConditionPropertyNameFromKey >= 0 )
                        {
                          v11 = (const wchar_t *)*((_QWORD *)this + 10);
                          if ( !v11
                            || (ConditionPropertyNameFromKey = XmlAddStringAttribute(L"valuetype", v14, v11),
                                ConditionPropertyNameFromKey >= 0) )
                          {
                            v12 = (const wchar_t *)*((_QWORD *)this + 11);
                            if ( v12 )
                              ConditionPropertyNameFromKey = XmlAddStringAttribute(L"localeName", v14, v12);
                          }
                        }
                        CoTaskMemFree(ppszOut);
                      }
                    }
                  }
                  break;
                }
              }
            }
          }
LABEL_26:
          CoTaskMemFree(v8);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v16);
      }
      ((void (__fastcall *)(struct IXMLDOMElement *))v14->lpVtbl->Release)(v14);
    }
  }
  return (unsigned int)ConditionPropertyNameFromKey;
}

```

## disassembly

```asm
0x1800659c0  mov     [rsp-28h+arg_8], rbx
0x1800659c5  push    rbp
0x1800659c6  push    rsi
0x1800659c7  push    rdi
0x1800659c8  push    r12
0x1800659ca  push    r14
0x1800659cc  mov     rbp, rsp
0x1800659cf  sub     rsp, 20h
0x1800659d3  mov     rdi, rdx
0x1800659d6  mov     rsi, rcx
0x1800659d9  call    ?Save@BaseCondition@StructuredQuery1@@UEAAJPEAUIXMLDOMNode@@@Z; StructuredQuery1::BaseCondition::Save(IXMLDOMNode *)
0x1800659de  mov     ebx, eax
0x1800659e0  test    eax, eax
0x1800659e2  js      loc_180065BE2
0x1800659e8  mov     [rbp+arg_0], 0
0x1800659f0  mov     rax, [rdi]
0x1800659f3  lea     r8, [rbp+arg_0]
0x1800659f7  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800659fe  mov     rcx, rdi
0x180065a01  mov     rax, [rax]
0x180065a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065a09  mov     ebx, eax
0x180065a0b  test    eax, eax
0x180065a0d  js      loc_180065BE2
0x180065a13  lea     r8, aLeafcondition; "leafCondition"
0x180065a1a  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180065a1e  lea     rcx, aType; "type"
0x180065a25  call    ?XmlAddStringAttribute@@YAJPEB_WPEAUIXMLDOMElement@@0@Z; XmlAddStringAttribute(wchar_t const *,IXMLDOMElement *,wchar_t const *)
0x180065a2a  mov     ebx, eax
0x180065a2c  test    eax, eax
0x180065a2e  js      loc_180065BD2
0x180065a34  lea     rbx, [rsi+78h]
0x180065a38  mov     rcx, rbx; lpCriticalSection
0x180065a3b  call    cs:__imp_EnterCriticalSection
0x180065a41  mov     [rbp+arg_18], rbx
0x180065a45  mov     [rbp+ppszOut], 0
0x180065a4d  lea     rcx, [rsi+20h]; propkey
0x180065a51  lea     rdx, [rbp+ppszOut]; struct _tagpropertykey *
0x180065a55  call    ?GetConditionPropertyNameFromKey@StructuredQuery1@@YAJAEBU_tagpropertykey@@PEAPEA_W@Z; StructuredQuery1::GetConditionPropertyNameFromKey(_tagpropertykey const &,wchar_t * *)
0x180065a5a  mov     ebx, eax
0x180065a5c  test    eax, eax
0x180065a5e  js      loc_180065BC9
0x180065a64  mov     rdi, [rbp+ppszOut]
0x180065a68  test    rdi, rdi
0x180065a6b  jnz     short loc_180065A8B
0x180065a6d  lea     r9, [rbp+ppszOut]
0x180065a71  lea     r8, cchOriginalDestLength
0x180065a78  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x180065a7d  mov     ebx, eax
0x180065a7f  mov     rdi, [rbp+ppszOut]
0x180065a83  test    eax, eax
0x180065a85  js      loc_180065BBF
0x180065a8b  mov     r8, rdi; psz
0x180065a8e  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180065a92  lea     rcx, aProperty; "property"
0x180065a99  call    ?XmlAddStringAttribute@@YAJPEB_WPEAUIXMLDOMElement@@0@Z; XmlAddStringAttribute(wchar_t const *,IXMLDOMElement *,wchar_t const *)
0x180065a9e  mov     ebx, eax
0x180065aa0  test    eax, eax
0x180065aa2  js      loc_180065BBF
0x180065aa8  mov     ecx, [rsi+34h]
0x180065aab  xor     eax, eax
0x180065aad  lea     r12, __ImageBase
0x180065ab4  mov     ebx, 8000FFFFh
0x180065ab9  cmp     eax, 0Fh
0x180065abc  jnb     loc_180065BBF
0x180065ac2  mov     r8d, eax
0x180065ac5  add     r8, r8
0x180065ac8  cmp     ds:rva dword_1800970B8[r12+r8*8], ecx
0x180065ad0  jz      short loc_180065AD6
0x180065ad2  inc     eax
0x180065ad4  jmp     short loc_180065AB4
0x180065ad6  mov     r8, ds:rva off_1800970B0[r12+r8*8]; psz
0x180065ade  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180065ae2  lea     rcx, aOperator; "operator"
0x180065ae9  call    ?XmlAddStringAttribute@@YAJPEB_WPEAUIXMLDOMElement@@0@Z; XmlAddStringAttribute(wchar_t const *,IXMLDOMElement *,wchar_t const *)
0x180065aee  mov     ebx, eax
0x180065af0  test    eax, eax
0x180065af2  js      loc_180065BBF
0x180065af8  movzx   ecx, word ptr [rsi+38h]
0x180065afc  xor     eax, eax
0x180065afe  cmp     eax, 13h
0x180065b01  jnb     loc_180065BBA
0x180065b07  movsxd  r8, eax
0x180065b0a  add     r8, r8
0x180065b0d  cmp     ds:rva word_180096F68[r12+r8*8], cx
0x180065b16  jz      short loc_180065B1C
0x180065b18  inc     eax
0x180065b1a  jmp     short loc_180065AFE
0x180065b1c  mov     r8, ds:rva ?c_pttovtt@@3QBU_unnamed_type_c_pttovtt_@@B[r12+r8*8]; psz
0x180065b24  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180065b28  lea     rcx, aPropertytype; "propertyType"
0x180065b2f  call    ?XmlAddStringAttribute@@YAJPEB_WPEAUIXMLDOMElement@@0@Z; XmlAddStringAttribute(wchar_t const *,IXMLDOMElement *,wchar_t const *)
0x180065b34  mov     ebx, eax
0x180065b36  test    eax, eax
0x180065b38  js      loc_180065BBF
0x180065b3e  mov     [rbp+ppszOut], 0
0x180065b46  lea     rdx, [rbp+ppszOut]; ppszOut
0x180065b4a  lea     rcx, [rsi+38h]; propvar
0x180065b4e  call    cs:__imp_PropVariantToStringAlloc
0x180065b54  mov     ebx, eax
0x180065b56  test    eax, eax
0x180065b58  js      short loc_180065BBF
0x180065b5a  mov     r8, [rbp+ppszOut]; psz
0x180065b5e  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180065b62  lea     rcx, aValue; "value"
0x180065b69  call    ?XmlAddStringAttribute@@YAJPEB_WPEAUIXMLDOMElement@@0@Z; XmlAddStringAttribute(wchar_t const *,IXMLDOMElement *,wchar_t const *)
0x180065b6e  mov     ebx, eax
0x180065b70  test    eax, eax
0x180065b72  js      short loc_180065BAE
0x180065b74  mov     r8, [rsi+50h]; psz
0x180065b78  test    r8, r8
0x180065b7b  jz      short loc_180065B93
0x180065b7d  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180065b81  lea     rcx, aValuetype; "valuetype"
0x180065b88  call    ?XmlAddStringAttribute@@YAJPEB_WPEAUIXMLDOMElement@@0@Z; XmlAddStringAttribute(wchar_t const *,IXMLDOMElement *,wchar_t const *)
0x180065b8d  mov     ebx, eax
0x180065b8f  test    eax, eax
0x180065b91  js      short loc_180065BAE
0x180065b93  mov     r8, [rsi+58h]; psz
0x180065b97  test    r8, r8
0x180065b9a  jz      short loc_180065BAE
0x180065b9c  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180065ba0  lea     rcx, aLocalename; "localeName"
0x180065ba7  call    ?XmlAddStringAttribute@@YAJPEB_WPEAUIXMLDOMElement@@0@Z; XmlAddStringAttribute(wchar_t const *,IXMLDOMElement *,wchar_t const *)
0x180065bac  mov     ebx, eax
0x180065bae  mov     rcx, [rbp+ppszOut]; pv
0x180065bb2  call    cs:__imp_CoTaskMemFree
0x180065bb8  jmp     short loc_180065BBF
0x180065bba  mov     ebx, 80004005h
0x180065bbf  mov     rcx, rdi; pv
0x180065bc2  call    cs:__imp_CoTaskMemFree
0x180065bc8  nop
0x180065bc9  lea     rcx, [rbp+arg_18]
0x180065bcd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180065bd2  mov     rcx, [rbp+arg_0]
0x180065bd6  mov     rax, [rcx]
0x180065bd9  mov     rax, [rax+10h]
0x180065bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065be2  mov     eax, ebx
0x180065be4  mov     rbx, [rsp+20h+arg_8]
0x180065be9  add     rsp, 20h
0x180065bed  pop     r14
0x180065bef  pop     r12
0x180065bf1  pop     rdi
0x180065bf2  pop     rsi
0x180065bf3  pop     rbp
0x180065bf4  retn
```
