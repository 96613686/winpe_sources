# CAutomationElement::InternalGetPropertyValueEx(int,int,int,ushort const *,tagVARIANT *)

- ea: `0x1800adc28`
- end: `0x1800ae380`
- name: `?InternalGetPropertyValueEx@CAutomationElement@@AEAAJHHHPEBGPEAUtagVARIANT@@@Z`
- size: `1880`
- prototype: `__int64 __fastcall(CAutomationElement *__hidden this, int, int, int, const unsigned __int16 *, VARIANTARG *pvarg)`
- caller_count: `5`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ae390`
- `0x1800cff20`
- `0x18015e080`
- `0x18017bcc0`
- `0x180260ac0`

## callees

- `0x18000f680`
- `0x18002f580`
- `0x18003ea38`
- `0x180061630`
- `0x180093850`
- `0x1800ad424`
- `0x1800ad62c`
- `0x1800ad728`
- `0x1800adaa4`
- `0x1800adc28`
- `0x1800b710c`
- `0x1800be9c8`
- `0x1800cfa40`
- `0x1800d9490`
- `0x1800e231c`
- `0x180133550`
- `0x1801a4ee0`
- `0x1801e8320`
- `0x180234818`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800adee2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800adfa8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800adee2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800adfa8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800adc8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800adc8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800adcb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800adcb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0f9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800adef5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800adfbb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800adef5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800adfbb`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae162`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae35e`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae162`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae35e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800ae198`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800ae198`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800ae327`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800ae327`

## string_xrefs

- `0x1800ae292`: `onecore\windows\accessibletech\uiautomationcore\misc.cpp`
- `0x1800adddf`: `onecore\windows\accessibletech\uiautomationcore\cautomationelement.cpp`
- `0x1800adeb6`: `onecore\windows\accessibletech\uiautomationcore\cautomationelement.cpp`
- `0x1800ae056`: `onecore\windows\accessibletech\uiautomationcore\cautomationelement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall CAutomationElement::InternalGetPropertyValueEx(
        CAutomationElement *this,
        int a2,
        int a3,
        int a4,
        unsigned __int16 *a5,
        VARIANTARG *pvarg)
{
  GUID **i; // r14
  CCacheHandler *v11; // rcx
  unsigned __int16 *v12; // r12
  int Property; // eax
  int v14; // ebx
  unsigned int v15; // esi
  unsigned __int16 *v16; // rbx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rsi
  struct IUnknown *v18; // rcx
  __int16 v19; // ax
  VARTYPE vt; // ax
  int v21; // eax
  const struct PropertyInfo *PropertyInfo; // rax
  _DWORD *v24; // rcx
  int v25; // eax
  int v26; // edx
  unsigned __int16 *v27; // rbx
  const OLECHAR *v28; // rdi
  int v29; // ecx
  const OLECHAR *v30; // rax
  int v31; // edx
  unsigned __int16 *v32; // rbx
  signed int LastError; // eax
  unsigned __int16 *v34; // r13
  const OLECHAR *v35; // rdi
  int v36; // ecx
  const OLECHAR *v37; // rax
  unsigned __int16 *v38; // rbx
  signed int v39; // eax
  unsigned __int16 *v40; // r13
  const OLECHAR *v41; // rax
  __int64 v42; // rdx
  int v43; // r9d
  int v44; // r8d
  const unsigned __int16 *v45; // rdx
  const OLECHAR *v46; // rax
  const OLECHAR *v47; // rax
  int v48; // eax
  int v49; // r15d
  __int64 v50; // rax
  __int64 v51; // rcx
  int v52; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v53; // [rsp+40h] [rbp-C0h] BYREF
  int v54; // [rsp+48h] [rbp-B8h] BYREF
  SAFEARRAY *psa; // [rsp+50h] [rbp-B0h] BYREF
  int v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+68h] [rbp-98h]
  WCHAR Buffer[512]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  v54 = a2;
  if ( !pvarg )
  {
    v43 = 500;
    v44 = -2147467261;
    v45 = L"retVal";
    return Error::ClientApiError(a5, v45, v44, v43);
  }
  pvarg->vt = 0;
  EnterCriticalSection(&_schemaLock);
  if ( (unsigned int)(a2 - 30000) > 0xAF )
  {
    for ( i = (GUID **)g_pUserDefinedProperties; i; i = (GUID **)*i )
    {
      if ( *((_DWORD *)i + 6) == a2 )
      {
        i += 2;
        break;
      }
    }
  }
  else
  {
    i = &(&off_1802DE930)[8 * (unsigned __int64)(unsigned int)(a2 - 30000)];
  }
  LeaveCriticalSection(&_schemaLock);
  if ( !i )
  {
    v43 = 502;
    v44 = -2147024809;
    v45 = L"propertyId";
    return Error::ClientApiError(a5, v45, v44, v43);
  }
  if ( !a4 )
  {
    v11 = (CCacheHandler *)*((_QWORD *)this + 14);
    v12 = 0;
    if ( v11 )
    {
      Property = CCacheHandler::GetProperty(v11, *((_DWORD *)this + 26), v54, pvarg);
      v14 = Property;
      v15 = -2147024809;
      if ( Property != -2147024809 )
      {
        if ( Property >= 0 )
          goto LABEL_9;
        v42 = 2143;
LABEL_64:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v42,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\cautomationelement.cpp",
          (const char *)(unsigned int)v14,
          v52);
        return v14;
      }
      if ( LoadStringW(g_hInstance, 0x1FAu, Buffer, 512) )
      {
        v32 = SysAllocString(Buffer);
        v53 = v32;
        LastError = v32 == 0 ? 0x8007000E : 0;
        v34 = v32;
        v12 = v32;
      }
      else
      {
        v32 = 0;
        v53 = 0;
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v34 = 0;
      }
      if ( LastError >= 0 )
        Error::SetError(v32, 0);
      v35 = &word_180313900;
      v36 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v37 = &word_180313900;
        if ( v32 )
          v37 = v34;
        WPP_SF_SdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, (__int64)L"propertyId", (__int64)v37);
      }
      if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 1) == 0 )
        goto LABEL_50;
      v47 = &word_180313900;
      if ( v32 )
        v47 = v12;
      if ( a5 )
        LODWORD(v35) = (_DWORD)a5;
    }
    else
    {
      if ( LoadStringW(g_hInstance, 0x1FAu, Buffer, 512) )
      {
        v38 = SysAllocString(Buffer);
        v53 = v38;
        v39 = v38 == 0 ? 0x8007000E : 0;
        v40 = v38;
        v12 = v38;
      }
      else
      {
        v38 = 0;
        v53 = 0;
        v39 = GetLastError();
        if ( v39 > 0 )
          v39 = (unsigned __int16)v39 | 0x80070000;
        v40 = 0;
      }
      if ( v39 >= 0 )
        Error::SetError(v38, 0);
      v15 = -2147024809;
      v35 = &word_180313900;
      v36 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v41 = &word_180313900;
        if ( v38 )
          v41 = v40;
        WPP_SF_SdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, (__int64)L"propertyId", (__int64)v41);
      }
      if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 1) == 0 )
        goto LABEL_50;
      v47 = &word_180313900;
      if ( v38 )
        v47 = v12;
      if ( a5 )
        LODWORD(v35) = (_DWORD)a5;
    }
    McTemplateU0zzz_EventWriteTransfer(v36, v31, (_DWORD)v35, (unsigned int)L"propertyId", (__int64)v47);
LABEL_50:
    AutoCleanupInfo<unsigned short *>::SafeRelease(&v53);
    return v15;
  }
  LODWORD(v12) = 0;
  if ( *((_DWORD *)this + 16) )
  {
    v15 = -2147220991;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84F,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\cautomationelement.cpp",
      (const char *)v15,
      v52);
    return v15;
  }
  v24 = (_DWORD *)*((_QWORD *)this + 7);
  if ( !v24 || v24[2] != 826362197 )
  {
    v53 = 0;
    v25 = LoadResourceString(0x1FCu, &v53);
    v27 = v53;
    if ( v25 >= 0 )
      Error::SetError(v53, 0);
    v28 = &word_180313900;
    v15 = -2147467259;
    v29 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v30 = &word_180313900;
      if ( v27 )
        v30 = v27;
      WPP_SF_SdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 5, (__int64)L"this", (__int64)v30);
    }
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 1) != 0 )
    {
      v46 = &word_180313900;
      if ( v27 )
        v46 = v27;
      if ( a5 )
        LODWORD(v28) = (_DWORD)a5;
      McTemplateU0zzz_EventWriteTransfer(v29, v26, (_DWORD)v28, (unsigned int)L"this", (__int64)v46);
    }
    AutoCleanupInfo<unsigned short *>::SafeRelease(&v53);
    goto LABEL_39;
  }
  v52 = 0;
  v14 = (*(__int64 (__fastcall **)(_DWORD *, __int64, __int64, int *))(*(_QWORD *)v24 + 64LL))(v24, 1, 1, &v54);
  if ( v14 < 0 )
  {
    v42 = 2130;
    goto LABEL_64;
  }
LABEL_9:
  v16 = 0;
  v58 = 0;
  if ( pvarg->vt != 8204 )
  {
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg->llVal;
    goto LABEL_11;
  }
  psa = 0;
  v56 = 0;
  v57 = 0;
  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg->llVal;
  v48 = SafeArrayAccessor<tagVARIANT>::Access(&psa, pvarg->llVal);
  v49 = v48;
  if ( v48 >= 0 )
  {
    if ( v56 == 2 )
    {
      v50 = v57;
      if ( *(_WORD *)v57 == 10 && *(_WORD *)(v57 + 24) == 13 )
      {
        v51 = *(_QWORD *)(v57 + 32);
        if ( v51 )
        {
          v16 = (unsigned __int16 *)QI<IErrorInfo>(v51);
          v53 = v16;
          if ( !v16 )
          {
            wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v53);
            SafeArrayAccessor<IDispatch *>::~SafeArrayAccessor<IDispatch *>(&psa);
            goto LABEL_11;
          }
          v53 = 0;
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v53);
          v50 = v57;
        }
        else
        {
          v16 = 0;
        }
        LODWORD(v12) = *(_DWORD *)(v50 + 8);
        if ( psa )
          SafeArrayUnaccessData(psa);
        goto LABEL_83;
      }
    }
    v49 = 1;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\misc.cpp",
      (const char *)(unsigned int)v48,
      v52);
  }
  SafeArrayAccessor<IDispatch *>::~SafeArrayAccessor<IDispatch *>(&psa);
  if ( v49 )
  {
LABEL_11:
    v18 = g_punkNotSupportedValue;
    if ( pvarg->vt == 13 && p_llVal->punkVal == g_punkNotSupportedValue )
    {
      vt = 13;
    }
    else
    {
      v19 = *((_WORD *)i + 20);
      if ( v19 && v19 != pvarg->vt )
      {
        Error::GeneralProviderError(0, L"IRawElementProviderSimple::GetPropertyValue", 0, 0, 420, 0);
        VariantClear(pvarg);
        pvarg->vt = 13;
        p_llVal->llVal = (LONGLONG)g_punkNotSupportedValue;
        vt = 13;
        v18 = g_punkNotSupportedValue;
      }
      else
      {
        vt = pvarg->vt;
      }
    }
    if ( !a3 && vt == 13 && p_llVal->punkVal == v18 )
    {
      PropertyInfo = Schema::GetPropertyInfo(v54);
      if ( !PropertyInfo )
      {
        Error::InternalErrorWorker(L"didn't find property ID");
        return -2147467259;
      }
      if ( (int)Schema::GetDefaultValue(*((unsigned int *)PropertyInfo + 12), pvarg) < 0 )
        return -2147467259;
    }
    v21 = CAutomationElement::VariantWrapIUiaNode(pvarg, v54 == 30156);
    v14 = v21;
    if ( v21 >= 0 )
      return 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x896,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\cautomationelement.cpp",
      (const char *)(unsigned int)v21,
      v52);
    return v14;
  }
LABEL_83:
  if ( v16 )
    SetErrorInfo(0, (IErrorInfo *)v16);
  VariantClear(pvarg);
  pvarg->vt = 0;
  if ( v16 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v16 + 16LL))(v16);
  return (int)v12;
}

```

## disassembly

```asm
0x1800adc28  mov     [rsp-8+arg_10], rbx
0x1800adc2d  push    rbp
0x1800adc2e  push    rsi
0x1800adc2f  push    rdi
0x1800adc30  push    r12
0x1800adc32  push    r13
0x1800adc34  push    r14
0x1800adc36  push    r15
0x1800adc38  lea     rbp, [rsp-380h]
0x1800adc40  sub     rsp, 480h
0x1800adc47  mov     rax, cs:__security_cookie
0x1800adc4e  xor     rax, rsp
0x1800adc51  mov     [rbp+3B0h+var_40], rax
0x1800adc58  mov     r12d, r9d
0x1800adc5b  mov     r13d, r8d
0x1800adc5e  mov     esi, edx
0x1800adc60  mov     rbx, rcx
0x1800adc63  mov     r15, [rbp+3B0h+arg_20]
0x1800adc6a  mov     rdi, [rbp+3B0h+pvarg]
0x1800adc71  mov     [rsp+4B0h+var_468], edx
0x1800adc75  test    rdi, rdi
0x1800adc78  jz      loc_1800AE0B7
0x1800adc7e  xor     eax, eax
0x1800adc80  mov     [rdi], ax
0x1800adc83  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800adc8a  call    cs:__imp_EnterCriticalSection
0x1800adc90  lea     eax, [rsi-7530h]
0x1800adc96  cmp     eax, 0AFh
0x1800adc9b  ja      loc_1800AE10B
0x1800adca1  mov     r14d, eax
0x1800adca4  shl     r14, 6
0x1800adca8  lea     rax, off_1802DE930
0x1800adcaf  add     r14, rax
0x1800adcb2  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800adcb9  call    cs:__imp_LeaveCriticalSection
0x1800adcbf  test    r14, r14
0x1800adcc2  jz      loc_1800AE1A0
0x1800adcc8  mov     edx, 1
0x1800adccd  test    r12d, r12d
0x1800adcd0  jnz     loc_1800ADDF5
0x1800adcd6  mov     rcx, [rbx+70h]; this
0x1800adcda  xor     r12d, r12d
0x1800adcdd  test    rcx, rcx
0x1800adce0  jz      loc_1800ADF92
0x1800adce6  mov     r9, rdi; struct tagVARIANT *
0x1800adce9  mov     r8d, [rsp+4B0h+var_468]; int
0x1800adcee  mov     edx, [rbx+68h]; int
0x1800adcf1  call    ?GetProperty@CCacheHandler@@QEAAJHHPEAUtagVARIANT@@@Z; CCacheHandler::GetProperty(int,int,tagVARIANT *)
0x1800adcf6  mov     ebx, eax
0x1800adcf8  mov     esi, 80070057h
0x1800adcfd  cmp     eax, esi
0x1800adcff  jz      loc_1800ADECC
0x1800add05  test    eax, eax
0x1800add07  js      loc_1800AE051
0x1800add0d  mov     rbx, r12
0x1800add10  mov     [rsp+4B0h+var_448], rbx
0x1800add15  mov     eax, 200Ch
0x1800add1a  cmp     [rdi], ax
0x1800add1d  jz      loc_1800AE261
0x1800add23  lea     rsi, [rdi+8]
0x1800add27  mov     rcx, cs:?g_punkNotSupportedValue@@3PEAUIUnknown@@EA; IUnknown * g_punkNotSupportedValue
0x1800add2e  mov     ebx, 0Dh
0x1800add33  cmp     [rdi], bx
0x1800add36  jz      short loc_1800ADDA0
0x1800add38  movzx   eax, word ptr [r14+28h]
0x1800add3d  test    ax, ax
0x1800add40  jz      short loc_1800ADD4B
0x1800add42  cmp     ax, [rdi]
0x1800add45  jnz     loc_1800AE33A
0x1800add4b  movzx   eax, word ptr [rdi]
0x1800add4e  test    r13d, r13d
0x1800add51  jnz     short loc_1800ADD58
0x1800add53  cmp     ax, bx
0x1800add56  jz      short loc_1800ADDAA
0x1800add58  mov     edx, r12d
0x1800add5b  cmp     [rsp+4B0h+var_468], 75CCh
0x1800add63  setz    dl; int
0x1800add66  mov     rcx, rdi; struct tagVARIANT *
0x1800add69  call    ?VariantWrapIUiaNode@CAutomationElement@@SAJPEAUtagVARIANT@@H@Z; CAutomationElement::VariantWrapIUiaNode(tagVARIANT *,int)
0x1800add6e  mov     ebx, eax
0x1800add70  test    eax, eax
0x1800add72  js      short loc_1800ADDD5
0x1800add74  xor     eax, eax
0x1800add76  mov     rcx, [rbp+3B0h+var_40]
0x1800add7d  xor     rcx, rsp; StackCookie
0x1800add80  call    __security_check_cookie
0x1800add85  mov     rbx, [rsp+4B0h+arg_10]
0x1800add8d  add     rsp, 480h
0x1800add94  pop     r15
0x1800add96  pop     r14
0x1800add98  pop     r13
0x1800add9a  pop     r12
0x1800add9c  pop     rdi
0x1800add9d  pop     rsi
0x1800add9e  pop     rbp
0x1800add9f  retn
0x1800adda0  cmp     [rsi], rcx
0x1800adda3  jnz     short loc_1800ADD38
0x1800adda5  movzx   eax, bx
0x1800adda8  jmp     short loc_1800ADD4E
0x1800addaa  cmp     [rsi], rcx
0x1800addad  jnz     short loc_1800ADD58
0x1800addaf  mov     ecx, [rsp+4B0h+var_468]; int
0x1800addb3  call    ?GetPropertyInfo@Schema@@SAPEBUPropertyInfo@@H@Z; Schema::GetPropertyInfo(int)
0x1800addb8  test    rax, rax
0x1800addbb  jz      loc_1800AE0A0
0x1800addc1  mov     rdx, rdi
0x1800addc4  mov     ecx, [rax+30h]
0x1800addc7  call    ?GetDefaultValue@Schema@@SAJW4DefaultValue@@PEAUtagVARIANT@@@Z; Schema::GetDefaultValue(DefaultValue,tagVARIANT *)
0x1800addcc  test    eax, eax
0x1800addce  jns     short loc_1800ADD58
0x1800addd0  jmp     loc_1800AE0AD
0x1800addd5  mov     rcx, [rbp+3B8h]; this
0x1800adddc  mov     r9d, ebx; char *
0x1800adddf  lea     r8, aOnecoreWindows_89; "onecore\\windows\\accessibletech\\uiaut"...
0x1800adde6  mov     edx, 896h; void *
0x1800addeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800addf0  nop
0x1800addf1  mov     eax, ebx
0x1800addf3  jmp     short loc_1800ADD76
0x1800addf5  xor     r12d, r12d
0x1800addf8  cmp     [rbx+40h], r12d
0x1800addfc  jnz     loc_1800AE1B8
0x1800ade02  mov     rcx, [rbx+38h]
0x1800ade06  test    rcx, rcx
0x1800ade09  jz      short loc_1800ADE18
0x1800ade0b  cmp     dword ptr [rcx+8], 31414955h
0x1800ade12  jz      loc_1800AE071
0x1800ade18  mov     [rsp+4B0h+var_470], r12
0x1800ade1d  lea     rdx, [rsp+4B0h+var_470]; unsigned __int16 **
0x1800ade22  mov     ecx, 1FCh; uID
0x1800ade27  call    ?LoadResourceString@@YAJHPEAPEAG@Z; LoadResourceString(int,ushort * *)
0x1800ade2c  mov     rbx, [rsp+4B0h+var_470]
0x1800ade31  test    eax, eax
0x1800ade33  jns     loc_1800AE1C2
0x1800ade39  lea     rax, WPP_GLOBAL_Control
0x1800ade40  lea     rdi, word_180313900
0x1800ade47  lea     r14, aThis; "this"
0x1800ade4e  mov     esi, 80004005h
0x1800ade53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ade5a  cmp     rcx, rax
0x1800ade5d  jz      short loc_1800ADE95
0x1800ade5f  test    byte ptr [rcx+1Ch], 2
0x1800ade63  jz      short loc_1800ADE95
0x1800ade65  mov     rax, rdi
0x1800ade68  test    rbx, rbx
0x1800ade6b  cmovnz  rax, rbx
0x1800ade6f  mov     r9, rdi
0x1800ade72  test    r15, r15
0x1800ade75  cmovnz  r9, r15
0x1800ade79  mov     edx, 12h
0x1800ade7e  mov     [rsp+4B0h+var_480], rax; __int64
0x1800ade83  mov     [rsp+4B0h+var_488], r14; __int64
0x1800ade88  mov     dword ptr [rsp+4B0h+var_490], esi; int
0x1800ade8c  mov     rcx, [rcx+10h]; LoggerHandle
0x1800ade90  call    WPP_SF_SdSS
0x1800ade95  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 1
0x1800ade9c  jnz     loc_1800AE1D1
0x1800adea2  lea     rcx, [rsp+4B0h+var_470]
0x1800adea7  call    ?SafeRelease@?$AutoCleanupInfo@PEAG@@SAXAEAPEAG@Z; AutoCleanupInfo<ushort *>::SafeRelease(ushort * &)
0x1800adeac  mov     rcx, [rbp+3B8h]; this
0x1800adeb3  mov     r9d, esi; char *
0x1800adeb6  lea     r8, aOnecoreWindows_89; "onecore\\windows\\accessibletech\\uiaut"...
0x1800adebd  mov     edx, 84Fh; void *
0x1800adec2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adec7  jmp     loc_1800ADF8B
0x1800adecc  mov     r9d, 200h; cchBufferMax
0x1800aded2  lea     r8, [rsp+4B0h+Buffer]; lpBuffer
0x1800aded7  lea     edx, [r9-6]; uID
0x1800adedb  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800adee2  call    cs:__imp_LoadStringW
0x1800adee8  test    eax, eax
0x1800adeea  jz      loc_1800AE0D7
0x1800adef0  lea     rcx, [rsp+4B0h+Buffer]; psz
0x1800adef5  call    cs:__imp_SysAllocString
0x1800adefb  mov     rbx, rax
0x1800adefe  mov     [rsp+4B0h+var_470], rax
0x1800adf03  neg     rax
0x1800adf06  sbb     eax, eax
0x1800adf08  not     eax
0x1800adf0a  and     eax, 8007000Eh
0x1800adf0f  mov     r13, rbx
0x1800adf12  mov     r12, rbx
0x1800adf15  test    eax, eax
0x1800adf17  jns     loc_1800AE22C
0x1800adf1d  lea     rax, WPP_GLOBAL_Control
0x1800adf24  lea     r14, aPropertyid; "propertyId"
0x1800adf2b  lea     rdi, word_180313900
0x1800adf32  mov     rcx, cs:WPP_GLOBAL_Control
0x1800adf39  cmp     rcx, rax
0x1800adf3c  jz      short loc_1800ADF74
0x1800adf3e  test    byte ptr [rcx+1Ch], 2
0x1800adf42  jz      short loc_1800ADF74
0x1800adf44  mov     rax, rdi
0x1800adf47  test    rbx, rbx
0x1800adf4a  cmovnz  rax, r13
0x1800adf4e  mov     r9, rdi
0x1800adf51  test    r15, r15
0x1800adf54  cmovnz  r9, r15
0x1800adf58  mov     edx, 12h
0x1800adf5d  mov     [rsp+4B0h+var_480], rax; __int64
0x1800adf62  mov     [rsp+4B0h+var_488], r14; __int64
0x1800adf67  mov     dword ptr [rsp+4B0h+var_490], esi; char
0x1800adf6b  mov     rcx, [rcx+10h]; LoggerHandle
0x1800adf6f  call    WPP_SF_SdSS
0x1800adf74  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 1
0x1800adf7b  jnz     loc_1800AE23B
0x1800adf81  lea     rcx, [rsp+4B0h+var_470]
0x1800adf86  call    ?SafeRelease@?$AutoCleanupInfo@PEAG@@SAXAEAPEAG@Z; AutoCleanupInfo<ushort *>::SafeRelease(ushort * &)
0x1800adf8b  mov     eax, esi
0x1800adf8d  jmp     loc_1800ADD76
0x1800adf92  mov     r9d, 200h; cchBufferMax
0x1800adf98  lea     r8, [rsp+4B0h+Buffer]; lpBuffer
0x1800adf9d  lea     edx, [r9-6]; uID
0x1800adfa1  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800adfa8  call    cs:__imp_LoadStringW
0x1800adfae  test    eax, eax
0x1800adfb0  jz      loc_1800AE0F1
0x1800adfb6  lea     rcx, [rsp+4B0h+Buffer]; psz
0x1800adfbb  call    cs:__imp_SysAllocString
0x1800adfc1  mov     rbx, rax
0x1800adfc4  mov     [rsp+4B0h+var_470], rax
0x1800adfc9  neg     rax
0x1800adfcc  sbb     eax, eax
0x1800adfce  not     eax
0x1800adfd0  and     eax, 8007000Eh
0x1800adfd5  mov     r13, rbx
0x1800adfd8  mov     r12, rbx
0x1800adfdb  test    eax, eax
0x1800adfdd  jns     loc_1800AE1F7
0x1800adfe3  lea     rax, WPP_GLOBAL_Control
0x1800adfea  mov     esi, 80070057h
0x1800adfef  lea     r14, aPropertyid; "propertyId"
0x1800adff6  lea     rdi, word_180313900
0x1800adffd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae004  cmp     rcx, rax
0x1800ae007  jz      short loc_1800AE03F
0x1800ae009  test    byte ptr [rcx+1Ch], 2
0x1800ae00d  jz      short loc_1800AE03F
0x1800ae00f  mov     rax, rdi
0x1800ae012  test    rbx, rbx
0x1800ae015  cmovnz  rax, r13
0x1800ae019  mov     r9, rdi
0x1800ae01c  test    r15, r15
0x1800ae01f  cmovnz  r9, r15
0x1800ae023  mov     edx, 12h
0x1800ae028  mov     [rsp+4B0h+var_480], rax; __int64
0x1800ae02d  mov     [rsp+4B0h+var_488], r14; __int64
0x1800ae032  mov     dword ptr [rsp+4B0h+var_490], esi; char
0x1800ae036  mov     rcx, [rcx+10h]; LoggerHandle
0x1800ae03a  call    WPP_SF_SdSS
0x1800ae03f  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 1
0x1800ae046  jnz     loc_1800AE206
0x1800ae04c  jmp     loc_1800ADF81
0x1800ae051  mov     edx, 85Fh; void *
0x1800ae056  lea     r8, aOnecoreWindows_89; "onecore\\windows\\accessibletech\\uiaut"...
0x1800ae05d  mov     r9d, ebx; char *
0x1800ae060  mov     rcx, [rbp+3B8h]; this
0x1800ae067  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae06c  jmp     loc_1800ADDF1
0x1800ae071  mov     rax, [rcx]
0x1800ae074  mov     [rsp+4B0h+var_488], rdi
0x1800ae079  mov     dword ptr [rsp+4B0h+var_490], r12d
0x1800ae07e  lea     r9, [rsp+4B0h+var_468]
0x1800ae083  mov     r8d, edx
0x1800ae086  mov     rax, [rax+40h]
0x1800ae08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae08f  mov     ebx, eax
0x1800ae091  test    eax, eax
0x1800ae093  jns     loc_1800ADD0D
0x1800ae099  mov     edx, 852h
0x1800ae09e  jmp     short loc_1800AE056
0x1800ae0a0  lea     rcx, aDidnTFindPrope; "didn't find property ID"
0x1800ae0a7  call    ?InternalErrorWorker@Error@@SAJPEBG@Z; Error::InternalErrorWorker(ushort const *)
0x1800ae0ac  nop
0x1800ae0ad  mov     eax, 80004005h
0x1800ae0b2  jmp     loc_1800ADD76
0x1800ae0b7  mov     r9d, 1F4h; int
0x1800ae0bd  mov     r8d, 80004003h; int
0x1800ae0c3  lea     rdx, aRetval; "retVal"
0x1800ae0ca  mov     rcx, r15; unsigned __int16 *
0x1800ae0cd  call    ?ClientApiError@Error@@SAJPEBG0JH@Z; Error::ClientApiError(ushort const *,ushort const *,long,int)
0x1800ae0d2  jmp     loc_1800ADD76
0x1800ae0d7  mov     rbx, r12
0x1800ae0da  mov     [rsp+4B0h+var_470], rbx
0x1800ae0df  call    cs:__imp_GetLastError
0x1800ae0e5  test    eax, eax
0x1800ae0e7  jg      short loc_1800AE12A
0x1800ae0e9  mov     r13, r12
0x1800ae0ec  jmp     loc_1800ADF15
0x1800ae0f1  mov     rbx, r12
0x1800ae0f4  mov     [rsp+4B0h+var_470], rbx
0x1800ae0f9  call    cs:__imp_GetLastError
0x1800ae0ff  test    eax, eax
0x1800ae101  jg      short loc_1800AE134
0x1800ae103  mov     r13, r12
0x1800ae106  jmp     loc_1800ADFDB
0x1800ae10b  mov     r14, cs:?g_pUserDefinedProperties@@3PEAUUserDefinedPropertyInfo@@EA; UserDefinedPropertyInfo * g_pUserDefinedProperties
0x1800ae112  test    r14, r14
0x1800ae115  jz      loc_1800ADCB2
  ... truncated ...
```
