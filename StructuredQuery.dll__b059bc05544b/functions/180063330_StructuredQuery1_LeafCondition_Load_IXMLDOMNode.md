# StructuredQuery1::LeafCondition::Load(IXMLDOMNode *)

- ea: `0x180063330`
- end: `0x18006364c`
- name: `?Load@LeafCondition@StructuredQuery1@@UEAAJPEAUIXMLDOMNode@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(StructuredQuery1::LeafCondition *__hidden this, struct IXMLDOMNode *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800094f8`
- `0x180015a40`
- `0x1800411e4`
- `0x180059920`
- `0x18005daf0`
- `0x180062f30`
- `0x180063330`
- `0x180063fa0`
- `0x18006682c`
- `0x180074338`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006339f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006339f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006347d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800634ab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006347d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800634ab`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x1800635db`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x1800635db`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x1800634ca`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x1800634ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800633ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800634f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063601`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800633ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800634f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063601`
- `PROPSYS!PSGetPropertyDescription` at `0x180063525`
- `PROPSYS!PSGetPropertyDescription` at `0x180063525`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StructuredQuery1::LeafCondition::Load(StructuredQuery1::LeafCondition *this, struct IXMLDOMNode *a2)
{
  int KeyFromConditionPropertyName; // edi
  struct _tagpropertykey *v5; // r8
  void *v6; // rcx
  enum tagCONDITION_OPERATION *v7; // r8
  unsigned __int16 v8; // r12
  const WCHAR *v9; // r13
  unsigned int i; // r14d
  __int16 v11; // ax
  __int64 v12; // rdx
  __int64 v13; // rcx
  int Error; // eax
  struct tagPROPVARIANT *nChar; // [rsp+20h] [rbp-E0h] BYREF
  struct IXMLDOMNamedNodeMap *v17; // [rsp+28h] [rbp-D8h] BYREF
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPCWCH lpString1; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpString; // [rsp+48h] [rbp-B8h] BYREF
  struct _RTL_CRITICAL_SECTION *v22; // [rsp+50h] [rbp-B0h] BYREF
  size_t LocaleName[22]; // [rsp+60h] [rbp-A0h] BYREF

  KeyFromConditionPropertyName = StructuredQuery1::BaseCondition::Load(this, a2);
  if ( KeyFromConditionPropertyName >= 0 )
  {
    v17 = 0;
    KeyFromConditionPropertyName = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNamedNodeMap **))a2->lpVtbl->get_attributes)(
                                     a2,
                                     &v17);
    if ( KeyFromConditionPropertyName >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
      v22 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 120);
      pv = 0;
      if ( XmlGetStringAttribute(L"property", v17, (wchar_t **)&pv) )
        goto LABEL_36;
      v6 = pv;
      if ( !pv || *(_WORD *)pv )
      {
        KeyFromConditionPropertyName = StructuredQuery1::GetKeyFromConditionPropertyName(
                                         (wchar_t *)pv,
                                         (const wchar_t *)this + 16,
                                         v5);
        v6 = pv;
      }
      else
      {
        *(PROPERTYKEY *)((char *)this + 32) = PKEY_Null;
      }
      CoTaskMemFree(v6);
      if ( KeyFromConditionPropertyName >= 0 )
      {
LABEL_36:
        lpString1 = 0;
        if ( XmlGetStringAttribute(L"operator", v17, (wchar_t **)&lpString1)
          || (KeyFromConditionPropertyName = StructuredQuery1::OperationFromString(
                                               lpString1,
                                               (const wchar_t *)this + 26,
                                               v7),
              CoTaskMemFree((LPVOID)lpString1),
              KeyFromConditionPropertyName >= 0) )
        {
          lpString = 0;
          if ( XmlGetStringAttribute(L"propertyType", v17, (wchar_t **)&lpString) )
          {
            LOWORD(nChar) = 1;
            ppv = 0;
            if ( PSGetPropertyDescription(
                   (const PROPERTYKEY *const)((char *)this + 32),
                   &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
                   &ppv) >= 0 )
            {
              (*(void (__fastcall **)(void *, struct tagPROPVARIANT **))(*(_QWORD *)ppv + 40LL))(ppv, &nChar);
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            }
            v11 = (__int16)nChar;
            if ( (_WORD)nChar == 1 )
              v11 = 8;
            v8 = v11;
          }
          else
          {
            v8 = 0;
            v9 = lpString;
            LODWORD(nChar) = lstrlenW(lpString);
            KeyFromConditionPropertyName = -2147467259;
            for ( i = 0; i < 0x13; ++i )
            {
              if ( (_DWORD)nChar == lstrlenW(*((LPCWSTR *)&c_pttovtt + 2 * (int)i))
                && !StrCmpNW(v9, *((PCWSTR *)&c_pttovtt + 2 * (int)i), (int)nChar) )
              {
                v8 = *((_WORD *)&c_pttovtt + 8 * (int)i + 4);
                KeyFromConditionPropertyName = 0;
                break;
              }
            }
            CoTaskMemFree((LPVOID)lpString);
            if ( KeyFromConditionPropertyName < 0 )
              goto LABEL_32;
          }
          ppv = 0;
          XmlGetStringAttribute(L"value", v17, (wchar_t **)&ppv);
          KeyFromConditionPropertyName = StructuredQuery1::ValueFromString(
                                           (wchar_t *)ppv,
                                           (const wchar_t *)this + 16,
                                           (const struct _tagpropertykey *)v8,
                                           (unsigned __int16)this + 56,
                                           nChar);
          if ( KeyFromConditionPropertyName >= 0 )
          {
            XmlGetStringAttribute(L"valuetype", v17, (wchar_t **)this + 10);
            if ( XmlGetStringAttribute(L"localeName", v17, (wchar_t **)this + 11) )
            {
              if ( GetUserDefaultLocaleName((LPWSTR)LocaleName, 85) )
                Error = _AllocString<CTCoAllocPolicy>(v13, v12, LocaleName, (_QWORD *)this + 11);
              else
                Error = ResultFromKnownLastError();
              KeyFromConditionPropertyName = Error;
            }
          }
          CoTaskMemFree(ppv);
        }
      }
LABEL_32:
      ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v17->lpVtbl->Release)(v17);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v22);
    }
  }
  return (unsigned int)KeyFromConditionPropertyName;
}

```

## disassembly

```asm
0x180063330  mov     [rsp-8+arg_10], rbx
0x180063335  push    rbp
0x180063336  push    rsi
0x180063337  push    rdi
0x180063338  push    r12
0x18006333a  push    r13
0x18006333c  push    r14
0x18006333e  push    r15
0x180063340  lea     rbp, [rsp-20h]
0x180063345  sub     rsp, 120h
0x18006334c  mov     rax, cs:__security_cookie
0x180063353  xor     rax, rsp
0x180063356  mov     [rbp+50h+var_40], rax
0x18006335a  mov     rbx, rdx
0x18006335d  mov     rsi, rcx
0x180063360  call    ?Load@BaseCondition@StructuredQuery1@@UEAAJPEAUIXMLDOMNode@@@Z; StructuredQuery1::BaseCondition::Load(IXMLDOMNode *)
0x180063365  mov     edi, eax
0x180063367  xor     r15d, r15d
0x18006336a  test    eax, eax
0x18006336c  js      loc_180063623
0x180063372  mov     [rsp+150h+var_128], r15
0x180063377  mov     rax, [rbx]
0x18006337a  lea     rdx, [rsp+150h+var_128]
0x18006337f  mov     rcx, rbx
0x180063382  mov     rax, [rax+88h]
0x180063389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006338e  mov     edi, eax
0x180063390  test    eax, eax
0x180063392  js      loc_180063623
0x180063398  lea     rbx, [rsi+78h]
0x18006339c  mov     rcx, rbx; lpCriticalSection
0x18006339f  call    cs:__imp_EnterCriticalSection
0x1800633a5  mov     [rsp+150h+var_100], rbx
0x1800633aa  mov     [rsp+150h+pv], r15
0x1800633af  lea     r8, [rsp+150h+pv]; wchar_t **
0x1800633b4  mov     rdx, [rsp+150h+var_128]; struct IXMLDOMNamedNodeMap *
0x1800633b9  lea     rcx, aProperty; "property"
0x1800633c0  call    ?XmlGetStringAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAPEA_W@Z; XmlGetStringAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,wchar_t * *)
0x1800633c5  test    eax, eax
0x1800633c7  jnz     short loc_18006340D
0x1800633c9  mov     rcx, [rsp+150h+pv]; Buffer
0x1800633ce  test    rcx, rcx
0x1800633d1  jz      short loc_1800633EF
0x1800633d3  cmp     [rcx], r15w
0x1800633d7  jnz     short loc_1800633EF
0x1800633d9  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x1800633e0  movups  xmmword ptr [rsi+20h], xmm0
0x1800633e4  mov     eax, cs:PKEY_Null.pid
0x1800633ea  mov     [rsi+30h], eax
0x1800633ed  jmp     short loc_1800633FF
0x1800633ef  lea     rdx, [rsi+20h]; wchar_t *
0x1800633f3  call    ?GetKeyFromConditionPropertyName@StructuredQuery1@@YAJPEB_WPEAU_tagpropertykey@@@Z; StructuredQuery1::GetKeyFromConditionPropertyName(wchar_t const *,_tagpropertykey *)
0x1800633f8  mov     edi, eax
0x1800633fa  mov     rcx, [rsp+150h+pv]; pv
0x1800633ff  call    cs:__imp_CoTaskMemFree
0x180063405  test    edi, edi
0x180063407  js      loc_180063607
0x18006340d  mov     [rsp+150h+lpString1], r15
0x180063412  lea     r8, [rsp+150h+lpString1]; wchar_t **
0x180063417  mov     rdx, [rsp+150h+var_128]; struct IXMLDOMNamedNodeMap *
0x18006341c  lea     rcx, aOperator; "operator"
0x180063423  call    ?XmlGetStringAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAPEA_W@Z; XmlGetStringAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,wchar_t * *)
0x180063428  test    eax, eax
0x18006342a  jnz     short loc_18006344F
0x18006342c  lea     rdx, [rsi+34h]; wchar_t *
0x180063430  mov     rcx, [rsp+150h+lpString1]; lpString1
0x180063435  call    ?OperationFromString@StructuredQuery1@@YAJPEB_WPEAW4tagCONDITION_OPERATION@@@Z; StructuredQuery1::OperationFromString(wchar_t const *,tagCONDITION_OPERATION *)
0x18006343a  mov     edi, eax
0x18006343c  mov     rcx, [rsp+150h+lpString1]; pv
0x180063441  call    cs:__imp_CoTaskMemFree
0x180063447  test    edi, edi
0x180063449  js      loc_180063607
0x18006344f  mov     [rsp+150h+lpString], r15
0x180063454  lea     r8, [rsp+150h+lpString]; wchar_t **
0x180063459  mov     rdx, [rsp+150h+var_128]; struct IXMLDOMNamedNodeMap *
0x18006345e  lea     rcx, aPropertytype; "propertyType"
0x180063465  call    ?XmlGetStringAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAPEA_W@Z; XmlGetStringAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,wchar_t * *)
0x18006346a  test    eax, eax
0x18006346c  jnz     loc_180063506
0x180063472  mov     r12d, r15d
0x180063475  mov     r13, [rsp+150h+lpString]
0x18006347a  mov     rcx, r13; lpString
0x18006347d  call    cs:__imp_lstrlenW
0x180063483  mov     dword ptr [rsp+150h+nChar], eax
0x180063487  mov     edi, 80004005h
0x18006348c  mov     r14d, r15d
0x18006348f  mov     ebx, 1
0x180063494  lea     rax, ?c_pttovtt@@3QBU_unnamed_type_c_pttovtt_@@B; _unnamed_type_c_pttovtt_ const near * const c_pttovtt
0x18006349b  cmp     r14d, 13h
0x18006349f  jnb     short loc_1800634EE
0x1800634a1  movsxd  r15, r14d
0x1800634a4  add     r15, r15
0x1800634a7  mov     rcx, [rax+r15*8]; lpString
0x1800634ab  call    cs:__imp_lstrlenW
0x1800634b1  mov     ecx, dword ptr [rsp+150h+nChar]
0x1800634b5  cmp     ecx, eax
0x1800634b7  jnz     short loc_1800634D4
0x1800634b9  mov     r8d, ecx; nChar
0x1800634bc  lea     rdx, ?c_pttovtt@@3QBU_unnamed_type_c_pttovtt_@@B; _unnamed_type_c_pttovtt_ const near * const c_pttovtt
0x1800634c3  mov     rdx, [rdx+r15*8]; psz2
0x1800634c7  mov     rcx, r13; psz1
0x1800634ca  call    cs:__imp_StrCmpNW
0x1800634d0  test    eax, eax
0x1800634d2  jz      short loc_1800634D9
0x1800634d4  add     r14d, ebx
0x1800634d7  jmp     short loc_180063494
0x1800634d9  lea     rax, ?c_pttovtt@@3QBU_unnamed_type_c_pttovtt_@@B; _unnamed_type_c_pttovtt_ const near * const c_pttovtt
0x1800634e0  movzx   r12d, word ptr [rax+r15*8+8]
0x1800634e6  xor     r15d, r15d
0x1800634e9  mov     edi, r15d
0x1800634ec  jmp     short loc_1800634F1
0x1800634ee  xor     r15d, r15d
0x1800634f1  mov     rcx, [rsp+150h+lpString]; pv
0x1800634f6  call    cs:__imp_CoTaskMemFree
0x1800634fc  test    edi, edi
0x1800634fe  js      loc_180063607
0x180063504  jmp     short loc_180063569
0x180063506  mov     ebx, 1
0x18006350b  mov     word ptr [rsp+150h+nChar], bx; struct tagPROPVARIANT *
0x180063510  mov     [rsp+150h+ppv], r15
0x180063515  lea     rcx, [rsi+20h]; propkey
0x180063519  lea     r8, [rsp+150h+ppv]; ppv
0x18006351e  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x180063525  call    cs:__imp_PSGetPropertyDescription
0x18006352b  test    eax, eax
0x18006352d  js      short loc_180063556
0x18006352f  mov     rcx, [rsp+150h+ppv]
0x180063534  mov     rax, [rcx]
0x180063537  lea     rdx, [rsp+150h+nChar]
0x18006353c  mov     rax, [rax+28h]
0x180063540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063545  mov     rcx, [rsp+150h+ppv]
0x18006354a  mov     rax, [rcx]
0x18006354d  mov     rax, [rax+10h]
0x180063551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063556  movzx   eax, word ptr [rsp+150h+nChar]
0x18006355b  cmp     ax, bx
0x18006355e  jnz     short loc_180063565
0x180063560  mov     eax, 8
0x180063565  movzx   r12d, ax
0x180063569  mov     rbx, rsi
0x18006356c  mov     [rsp+150h+ppv], r15
0x180063571  lea     r8, [rsp+150h+ppv]; wchar_t **
0x180063576  mov     rdx, [rsp+150h+var_128]; struct IXMLDOMNamedNodeMap *
0x18006357b  lea     rcx, aValue; "value"
0x180063582  call    ?XmlGetStringAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAPEA_W@Z; XmlGetStringAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,wchar_t * *)
0x180063587  lea     r9, [rsi+38h]; unsigned __int16
0x18006358b  lea     rdx, [rbx+20h]; wchar_t *
0x18006358f  movzx   r8d, r12w; struct _tagpropertykey *
0x180063593  mov     rcx, [rsp+150h+ppv]; this
0x180063598  call    ?ValueFromString@StructuredQuery1@@YAJPEB_WAEBU_tagpropertykey@@GPEAUtagPROPVARIANT@@@Z; StructuredQuery1::ValueFromString(wchar_t const *,_tagpropertykey const &,ushort,tagPROPVARIANT *)
0x18006359d  mov     edi, eax
0x18006359f  test    eax, eax
0x1800635a1  js      short loc_1800635FC
0x1800635a3  lea     r8, [rsi+50h]; wchar_t **
0x1800635a7  mov     rdx, [rsp+150h+var_128]; struct IXMLDOMNamedNodeMap *
0x1800635ac  lea     rcx, aValuetype; "valuetype"
0x1800635b3  call    ?XmlGetStringAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAPEA_W@Z; XmlGetStringAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,wchar_t * *)
0x1800635b8  lea     r8, [rsi+58h]; wchar_t **
0x1800635bc  mov     rdx, [rsp+150h+var_128]; struct IXMLDOMNamedNodeMap *
0x1800635c1  lea     rcx, aLocalename; "localeName"
0x1800635c8  call    ?XmlGetStringAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAPEA_W@Z; XmlGetStringAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,wchar_t * *)
0x1800635cd  test    eax, eax
0x1800635cf  jz      short loc_1800635FC
0x1800635d1  mov     edx, 55h ; 'U'; cchLocaleName
0x1800635d6  lea     rcx, [rsp+150h+LocaleName]; lpLocaleName
0x1800635db  call    cs:__imp_GetUserDefaultLocaleName
0x1800635e1  test    eax, eax
0x1800635e3  jz      short loc_1800635F5
0x1800635e5  lea     r9, [rsi+58h]
0x1800635e9  lea     r8, [rsp+150h+LocaleName]
0x1800635ee  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x1800635f3  jmp     short loc_1800635FA
0x1800635f5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800635fa  mov     edi, eax
0x1800635fc  mov     rcx, [rsp+150h+ppv]; pv
0x180063601  call    cs:__imp_CoTaskMemFree
0x180063607  mov     rcx, [rsp+150h+var_128]
0x18006360c  mov     rax, [rcx]
0x18006360f  mov     rax, [rax+10h]
0x180063613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063618  nop
0x180063619  lea     rcx, [rsp+150h+var_100]
0x18006361e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180063623  mov     eax, edi
0x180063625  mov     rcx, [rbp+50h+var_40]
0x180063629  xor     rcx, rsp; StackCookie
0x18006362c  call    __security_check_cookie
0x180063631  mov     rbx, [rsp+150h+arg_10]
0x180063639  add     rsp, 120h
0x180063640  pop     r15
0x180063642  pop     r14
0x180063644  pop     r13
0x180063646  pop     r12
0x180063648  pop     rdi
0x180063649  pop     rsi
0x18006364a  pop     rbp
0x18006364b  retn
```
