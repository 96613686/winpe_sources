# Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner::GenerateAnimators(void)

- ea: `0x18008e4b4`
- end: `0x18008e94f`
- name: `?GenerateAnimators@CompositionAnimationTriggerPartner@Internal@Composition@UI@Windows@@AEAAJXZ`
- size: `1179`
- prototype: `__int64 __fastcall(Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008e2e0`

## callees

- `0x1800093f4`
- `0x18000aca4`
- `0x18000bc00`
- `0x18000f850`
- `0x18001358c`
- `0x18002be50`
- `0x18002df90`
- `0x180030f60`
- `0x180033c2c`
- `0x180048980`
- `0x18007610c`
- `0x18007810c`
- `0x1800792c8`
- `0x18008e4b4`
- `0x18008f00c`
- `0x1800e08a0`
- `0x1800ebe2c`
- `0x1800eca1c`
- `0x1800f6f10`
- `0x18015b3dc`
- `0x18016df08`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008e8b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008e8b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008e528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008e528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e71f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e71f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e89a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e89a`

## string_xrefs

- `0x18008e73f`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationtriggerpartner.cpp`
- `0x18008e765`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationtriggerpartner.cpp`
- `0x18008e7de`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationtriggerpartner.cpp`
- `0x18008e8e3`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationtriggerpartner.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner::GenerateAnimators(
        Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner *this)
{
  __int64 *i; // rdi
  __int64 v3; // rbx
  HRESULT v4; // eax
  struct Microsoft::WRL2::ContextSession *v5; // rcx
  int v6; // eax
  struct Windows::UI::Composition::CompositionAnimation *v7; // rbx
  int v8; // eax
  unsigned int v9; // ebx
  Microsoft::WRL2::NestableRuntimeClass **v10; // rdx
  struct Microsoft::WRL2::ContextSession *v11; // rcx
  int started; // eax
  Windows::UI::Composition::CompositionPropertyAnimator **j; // rbx
  Microsoft::WRL2::NestableRuntimeClass *v14; // r15
  Microsoft::WRL2::NestableRuntimeClass **v15; // rdx
  __int64 v16; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdi
  __int64 k; // rbx
  int v21; // ecx
  __int64 v22; // rbx
  __int64 v23; // r14
  HRESULT v24; // eax
  int v25; // eax
  int v26; // [rsp+20h] [rbp-59h]
  Microsoft::WRL2::NestableRuntimeClass *v27; // [rsp+30h] [rbp-49h] BYREF
  struct Microsoft::WRL2::ContextRuntimeClass *v28; // [rsp+38h] [rbp-41h] BYREF
  HSTRING newString; // [rsp+40h] [rbp-39h] BYREF
  struct Microsoft::WRL2::ContextRuntimeClass *v30; // [rsp+48h] [rbp-31h] BYREF
  struct IUnknown *v31; // [rsp+50h] [rbp-29h] BYREF
  struct IUnknown *v32; // [rsp+58h] [rbp-21h] BYREF
  Microsoft::WRL2::NestableRuntimeClass *v33; // [rsp+60h] [rbp-19h] BYREF
  __int128 v34; // [rsp+68h] [rbp-11h] BYREF
  __int64 v35; // [rsp+78h] [rbp-1h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  HSTRING string; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  for ( i = (__int64 *)*((_QWORD *)this + 23); i != *((__int64 **)this + 24); ++i )
  {
    v3 = *i;
    v27 = 0;
    newString = 0;
    v32 = 0;
    v31 = 0;
    v30 = 0;
    WindowsDeleteString(0);
    newString = 0;
    v4 = WindowsDuplicateString(*(HSTRING *)(v3 + 160), &newString);
    if ( v4 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationtriggerpartner.cpp",
        (const char *)(unsigned int)v4,
        v26);
    Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueue>::operator=(&v32, *(_QWORD *)(*i + 168));
    Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimationBase>::operator=(&v31, *(_QWORD *)(*i + 176));
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v30);
    v5 = (struct Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
    v30 = 0;
    v6 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
           v5,
           v31,
           (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionAnimation::s_InterfaceType,
           &v30);
    v7 = v30;
    if ( v6 < 0 )
    {
      v28 = 0;
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v28);
      v11 = (struct Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
      v28 = 0;
      started = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
                  v11,
                  v31,
                  (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionAnimationGroup::s_InterfaceType,
                  &v28);
      v9 = started;
      if ( started < 0 )
      {
        v16 = 117;
LABEL_30:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationtriggerpartner.cpp",
          (const char *)(unsigned int)started,
          v26);
        if ( hstringHeader.Reserved.Reserved1 )
        {
          std::_Deallocate<16>(
            hstringHeader.Reserved.Reserved1,
            (*(_QWORD *)&hstringHeader.Reserved.Reserved2[16] - (unsigned __int64)hstringHeader.Reserved.Reserved1)
          & 0xFFFFFFFFFFFFFFF8uLL);
          memset(&hstringHeader, 0, sizeof(hstringHeader));
        }
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v28);
LABEL_33:
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v30);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v31);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v32);
        WindowsDeleteString(newString);
        newString = 0;
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v27);
        return v9;
      }
      started = Windows::UI::Composition::CompositionAnimationGroup::StartAnimationGroupWithIAnimationObject(
                  (__int64)v28,
                  v32,
                  (__int64)&hstringHeader);
      v9 = started;
      if ( started < 0 )
      {
        v16 = 118;
        goto LABEL_30;
      }
      for ( j = (Windows::UI::Composition::CompositionPropertyAnimator **)hstringHeader.Reserved.Reserved1;
            j != *(Windows::UI::Composition::CompositionPropertyAnimator ***)&hstringHeader.Reserved.Reserved2[8];
            ++j )
      {
        Windows::UI::Composition::CompositionPropertyAnimator::SetOwningTrigger(*j, this);
        v14 = *j;
        v33 = v14;
        if ( v14 )
          Microsoft::WRL2::NestableRuntimeClass::InternalAddRef(v14);
        v15 = (Microsoft::WRL2::NestableRuntimeClass **)*((_QWORD *)this + 28);
        if ( v15 == *((Microsoft::WRL2::NestableRuntimeClass ***)this + 29) )
        {
          std::vector<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>>::_Emplace_reallocate<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>>(
            (char *)this + 216,
            v15,
            &v33);
        }
        else
        {
          *v15 = 0;
          if ( v15 != &v33 )
          {
            *v15 = v14;
            v33 = 0;
          }
          *((_QWORD *)this + 28) += 8LL;
        }
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v33);
      }
      if ( hstringHeader.Reserved.Reserved1 )
      {
        std::_Deallocate<16>(
          hstringHeader.Reserved.Reserved1,
          (*(_QWORD *)&hstringHeader.Reserved.Reserved2[16] - (unsigned __int64)hstringHeader.Reserved.Reserved1)
        & 0xFFFFFFFFFFFFFFF8uLL);
        memset(&hstringHeader, 0, sizeof(hstringHeader));
      }
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v28);
    }
    else
    {
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v27);
      v8 = Windows::UI::Composition::CompositionObjectFactory::StartAnimationWithIAnimationObject(
             v32,
             (Windows::UI::Composition::AnimationHelper *)newString,
             v7,
             &v27);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6B,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationtriggerpartner.cpp",
          (const char *)(unsigned int)v8,
          v26);
        goto LABEL_33;
      }
      Windows::UI::Composition::CompositionPropertyAnimator::SetOwningTrigger(v27, this);
      v10 = (Microsoft::WRL2::NestableRuntimeClass **)*((_QWORD *)this + 28);
      if ( v10 == *((Microsoft::WRL2::NestableRuntimeClass ***)this + 29) )
      {
        std::vector<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>>::_Emplace_reallocate<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator> const &>(
          (char *)this + 216,
          v10,
          &v27);
      }
      else
      {
        *v10 = v27;
        if ( v27 )
          Microsoft::WRL2::NestableRuntimeClass::InternalAddRef(v27);
        *((_QWORD *)this + 28) += 8LL;
      }
    }
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v30);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v32);
    WindowsDeleteString(newString);
    newString = 0;
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v27);
  }
  v18 = (__int64)(*((_QWORD *)this + 28) - *((_QWORD *)this + 27)) >> 3;
  v34 = 0;
  v35 = 0;
  std::vector<unsigned int>::reserve(&v34, v18);
  v19 = *((_QWORD *)this + 28);
  for ( k = *((_QWORD *)this + 27); k != v19; k += 8 )
  {
    v21 = *(_DWORD *)(*(_QWORD *)k + 144LL);
    LODWORD(v27) = v21;
    if ( *((_QWORD *)&v34 + 1) == v35 )
    {
      std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(&v34, *((_QWORD *)&v34 + 1), &v27);
    }
    else
    {
      **((_DWORD **)&v34 + 1) = v21;
      *((_QWORD *)&v34 + 1) += 4LL;
    }
  }
  Windows::UI::Composition::ProxyObject::SetReferenceArrayProperty(
    this,
    2,
    v34,
    (__int64)(*((_QWORD *)&v34 + 1) - v34) >> 2);
  v22 = *(_QWORD *)this;
  v23 = *((_QWORD *)this + 22);
  string = 0;
  v24 = WindowsCreateStringReference(L"Triggered", 9u, &hstringHeader, &string);
  if ( v24 < 0 )
  {
    RaiseException(v24, 1u, 0, 0);
    __debugbreak();
  }
  v25 = (*(__int64 (__fastcall **)(Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner *, HSTRING, __int64, _QWORD))(v22 + 152))(
          this,
          string,
          v23,
          0);
  v9 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationtriggerpartner.cpp",
      (const char *)(unsigned int)v25,
      (_DWORD)this + 208);
    std::vector<unsigned int>::_Tidy(&v34);
    return v9;
  }
  Windows::UI::Composition::ProxyObject::SetReferenceProperty(
    this,
    1,
    *(unsigned int *)(*((_QWORD *)this + 26) + 144LL));
  std::vector<unsigned int>::_Tidy(&v34);
  return 0;
}

```

## disassembly

```asm
0x18008e4b4  mov     [rsp-8+arg_8], rbx
0x18008e4b9  mov     [rsp-8+arg_10], rsi
0x18008e4be  push    rbp
0x18008e4bf  push    rdi
0x18008e4c0  push    r12
0x18008e4c2  push    r14
0x18008e4c4  push    r15
0x18008e4c6  lea     rbp, [rsp-37h]
0x18008e4cb  sub     rsp, 0B0h
0x18008e4d2  mov     rax, cs:__security_cookie
0x18008e4d9  xor     rax, rsp
0x18008e4dc  mov     [rbp+57h+var_30], rax
0x18008e4e0  mov     rdi, [rcx+0B8h]
0x18008e4e7  mov     rsi, rcx
0x18008e4ea  xor     r12d, r12d
0x18008e4ed  cmp     rdi, [rsi+0C0h]
0x18008e4f4  jz      loc_18008E7F0
0x18008e4fa  mov     rbx, [rdi]
0x18008e4fd  xor     ecx, ecx; string
0x18008e4ff  mov     [rbp+57h+var_A0], r12
0x18008e503  mov     [rbp+57h+newString], r12
0x18008e507  mov     [rbp+57h+var_78], r12
0x18008e50b  mov     [rbp+57h+var_80], r12
0x18008e50f  mov     [rbp+57h+var_88], r12
0x18008e513  call    cs:__imp_WindowsDeleteString
0x18008e519  mov     [rbp+57h+newString], r12
0x18008e51d  lea     rdx, [rbp+57h+newString]; newString
0x18008e521  mov     rcx, [rbx+0A0h]; string
0x18008e528  call    cs:__imp_WindowsDuplicateString
0x18008e52e  mov     rcx, [rbp+5Fh]; this
0x18008e532  test    eax, eax
0x18008e534  js      loc_18008E7DB
0x18008e53a  mov     rdx, [rdi]
0x18008e53d  lea     rcx, [rbp+57h+var_78]
0x18008e541  mov     rdx, [rdx+0A8h]
0x18008e548  call    ??4?$ComPtr@UIDispatcherQueue@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDispatcherQueue@System@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueue>::operator=(Windows::System::IDispatcherQueue *)
0x18008e54d  mov     rdx, [rdi]
0x18008e550  lea     rcx, [rbp+57h+var_80]
0x18008e554  mov     rdx, [rdx+0B0h]
0x18008e55b  call    ??4?$ComPtr@UICompositionAnimationBase@Composition@UI@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUICompositionAnimationBase@Composition@UI@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimationBase>::operator=(Windows::UI::Composition::ICompositionAnimationBase *)
0x18008e560  lea     rcx, [rbp+57h+var_88]; void *
0x18008e564  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18008e569  mov     rdx, [rbp+57h+var_80]; struct IUnknown *
0x18008e56d  lea     r9, [rbp+57h+var_88]; struct Microsoft::WRL2::ContextRuntimeClass **
0x18008e571  mov     rcx, [rsi+18h]; struct Microsoft::WRL2::ContextSession *
0x18008e575  lea     r8, ?s_InterfaceType@CompositionAnimation@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x18008e57c  mov     [rbp+57h+var_88], r12
0x18008e580  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x18008e585  mov     rbx, [rbp+57h+var_88]
0x18008e589  mov     [rbp+57h+var_88], rbx
0x18008e58d  test    eax, eax
0x18008e58f  js      short loc_18008E605
0x18008e591  lea     rcx, [rbp+57h+var_A0]; void *
0x18008e595  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18008e59a  mov     rdx, [rbp+57h+newString]; this
0x18008e59e  lea     r9, [rbp+57h+var_A0]; struct Windows::UI::Composition::CompositionPropertyAnimator **
0x18008e5a2  mov     rcx, [rbp+57h+var_78]; struct IUnknown *
0x18008e5a6  mov     r8, rbx; struct Windows::UI::Composition::CompositionAnimation *
0x18008e5a9  call    ?StartAnimationWithIAnimationObject@CompositionObjectFactory@Composition@UI@Windows@@SAJPEAUIAnimationObject@234@PEAUHSTRING__@@PEAVCompositionAnimation@234@PEAPEAVCompositionPropertyAnimator@234@@Z; Windows::UI::Composition::CompositionObjectFactory::StartAnimationWithIAnimationObject(Windows::UI::Composition::IAnimationObject *,HSTRING__ *,Windows::UI::Composition::CompositionAnimation *,Windows::UI::Composition::CompositionPropertyAnimator * *)
0x18008e5ae  mov     ebx, eax
0x18008e5b0  test    eax, eax
0x18008e5b2  js      loc_18008E73B
0x18008e5b8  mov     rcx, [rbp+57h+var_A0]; this
0x18008e5bc  mov     rdx, rsi; struct Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner *
0x18008e5bf  call    ?SetOwningTrigger@CompositionPropertyAnimator@Composition@UI@Windows@@QEAAXPEAVCompositionAnimationTriggerPartner@Internal@234@@Z; Windows::UI::Composition::CompositionPropertyAnimator::SetOwningTrigger(Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner *)
0x18008e5c4  lea     rbx, [rsi+0D8h]
0x18008e5cb  mov     rdx, [rbx+8]
0x18008e5cf  cmp     rdx, [rbx+10h]
0x18008e5d3  jz      short loc_18008E5F4
0x18008e5d5  mov     rax, [rbp+57h+var_A0]
0x18008e5d9  mov     [rdx], rax
0x18008e5dc  mov     rcx, [rbp+57h+var_A0]; this
0x18008e5e0  test    rcx, rcx
0x18008e5e3  jz      short loc_18008E5EA
0x18008e5e5  call    ?InternalAddRef@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalAddRef(void)
0x18008e5ea  add     qword ptr [rbx+8], 8
0x18008e5ef  jmp     loc_18008E700
0x18008e5f4  lea     r8, [rbp+57h+var_A0]
0x18008e5f8  mov     rcx, rbx
0x18008e5fb  call    ??$_Emplace_reallocate@AEBV?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@@?$vector@V?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@V?$allocator@V?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@@std@@@std@@AEAAPEAV?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>>::_Emplace_reallocate<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator> const &>(Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator> * const,Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator> const &)
0x18008e600  jmp     loc_18008E700
0x18008e605  xorps   xmm0, xmm0
0x18008e608  mov     [rbp+57h+var_98], r12
0x18008e60c  lea     rcx, [rbp+57h+var_98]; void *
0x18008e610  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r12
0x18008e614  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18008e619  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18008e61e  mov     rdx, [rbp+57h+var_80]; struct IUnknown *
0x18008e622  lea     r9, [rbp+57h+var_98]; struct Microsoft::WRL2::ContextRuntimeClass **
0x18008e626  mov     rcx, [rsi+18h]; struct Microsoft::WRL2::ContextSession *
0x18008e62a  lea     r8, ?s_InterfaceType@CompositionAnimationGroup@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x18008e631  mov     [rbp+57h+var_98], r12
0x18008e635  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x18008e63a  mov     rcx, [rbp+57h+var_98]
0x18008e63e  mov     ebx, eax
0x18008e640  mov     [rbp+57h+var_98], rcx
0x18008e644  test    eax, eax
0x18008e646  js      loc_18008E75C
0x18008e64c  mov     rdx, [rbp+57h+var_78]
0x18008e650  lea     r8, [rbp+57h+hstringHeader]
0x18008e654  call    ?StartAnimationGroupWithIAnimationObject@CompositionAnimationGroup@Composition@UI@Windows@@QEAAJPEAUIAnimationObject@234@PEAV?$vector@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@V?$allocator@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@@std@@@std@@@Z; Windows::UI::Composition::CompositionAnimationGroup::StartAnimationGroupWithIAnimationObject(Windows::UI::Composition::IAnimationObject *,std::vector<Windows::UI::Composition::CompositionPropertyAnimator *> *)
0x18008e659  mov     ebx, eax
0x18008e65b  test    eax, eax
0x18008e65d  js      loc_18008E755
0x18008e663  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18008e667  cmp     rbx, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18008e66b  jz      short loc_18008E6D2
0x18008e66d  mov     rcx, [rbx]; this
0x18008e670  mov     rdx, rsi; struct Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner *
0x18008e673  call    ?SetOwningTrigger@CompositionPropertyAnimator@Composition@UI@Windows@@QEAAXPEAVCompositionAnimationTriggerPartner@Internal@234@@Z; Windows::UI::Composition::CompositionPropertyAnimator::SetOwningTrigger(Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner *)
0x18008e678  mov     r15, [rbx]
0x18008e67b  lea     r14, [rsi+0D8h]
0x18008e682  mov     [rbp+57h+var_70], r15
0x18008e686  test    r15, r15
0x18008e689  jz      short loc_18008E693
0x18008e68b  mov     rcx, r15; this
0x18008e68e  call    ?InternalAddRef@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalAddRef(void)
0x18008e693  mov     rdx, [r14+8]
0x18008e697  cmp     rdx, [r14+10h]
0x18008e69b  jz      short loc_18008E6B7
0x18008e69d  lea     rax, [rbp+57h+var_70]
0x18008e6a1  mov     [rdx], r12
0x18008e6a4  cmp     rdx, rax
0x18008e6a7  jz      short loc_18008E6B0
0x18008e6a9  mov     [rdx], r15
0x18008e6ac  mov     [rbp+57h+var_70], r12
0x18008e6b0  add     qword ptr [r14+8], 8
0x18008e6b5  jmp     short loc_18008E6C3
0x18008e6b7  lea     r8, [rbp+57h+var_70]
0x18008e6bb  mov     rcx, r14
0x18008e6be  call    ??$_Emplace_reallocate@V?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@@?$vector@V?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@V?$allocator@V?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@@std@@@std@@AEAAPEAV?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@QEAV234@$$QEAV234@@Z; std::vector<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>>::_Emplace_reallocate<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>>(Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator> * const,Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator> &&)
0x18008e6c3  lea     rcx, [rbp+57h+var_70]; void *
0x18008e6c7  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18008e6cc  add     rbx, 8
0x18008e6d0  jmp     short loc_18008E667
0x18008e6d2  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18008e6d6  test    rcx, rcx
0x18008e6d9  jz      short loc_18008E6F7
0x18008e6db  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18008e6df  sub     rdx, rcx
0x18008e6e2  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18008e6e6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008e6eb  xorps   xmm0, xmm0
0x18008e6ee  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r12
0x18008e6f2  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18008e6f7  lea     rcx, [rbp+57h+var_98]; void *
0x18008e6fb  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18008e700  lea     rcx, [rbp+57h+var_88]; void *
0x18008e704  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18008e709  lea     rcx, [rbp+57h+var_80]
0x18008e70d  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18008e712  lea     rcx, [rbp+57h+var_78]
0x18008e716  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18008e71b  mov     rcx, [rbp+57h+newString]; string
0x18008e71f  call    cs:__imp_WindowsDeleteString
0x18008e725  lea     rcx, [rbp+57h+var_A0]; void *
0x18008e729  mov     [rbp+57h+newString], r12
0x18008e72d  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18008e732  add     rdi, 8
0x18008e736  jmp     loc_18008E4ED
0x18008e73b  mov     rcx, [rbp+5Fh]; this
0x18008e73f  lea     r8, aOnecoreuapWind_111; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18008e746  mov     r9d, eax; char *
0x18008e749  mov     edx, 6Bh ; 'k'; void *
0x18008e74e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e753  jmp     short loc_18008E7A2
0x18008e755  mov     edx, 76h ; 'v'
0x18008e75a  jmp     short loc_18008E761
0x18008e75c  mov     edx, 75h ; 'u'; void *
0x18008e761  mov     rcx, [rbp+5Fh]; this
0x18008e765  lea     r8, aOnecoreuapWind_111; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18008e76c  mov     r9d, eax; char *
0x18008e76f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e774  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18008e778  test    rcx, rcx
0x18008e77b  jz      short loc_18008E799
0x18008e77d  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18008e781  sub     rdx, rcx
0x18008e784  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18008e788  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008e78d  xorps   xmm0, xmm0
0x18008e790  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r12
0x18008e794  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18008e799  lea     rcx, [rbp+57h+var_98]; void *
0x18008e79d  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18008e7a2  lea     rcx, [rbp+57h+var_88]; void *
0x18008e7a6  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18008e7ab  lea     rcx, [rbp+57h+var_80]
0x18008e7af  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18008e7b4  lea     rcx, [rbp+57h+var_78]
0x18008e7b8  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18008e7bd  mov     rcx, [rbp+57h+newString]; string
0x18008e7c1  call    cs:__imp_WindowsDeleteString
0x18008e7c7  lea     rcx, [rbp+57h+var_A0]; void *
0x18008e7cb  mov     [rbp+57h+newString], r12
0x18008e7cf  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18008e7d4  mov     eax, ebx
0x18008e7d6  jmp     loc_18008E927
0x18008e7db  mov     r9d, eax; char *
0x18008e7de  lea     r8, aOnecoreuapWind_111; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18008e7e5  mov     edx, 57h ; 'W'; void *
0x18008e7ea  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008e7f0  mov     rdx, [rsi+0E0h]
0x18008e7f7  lea     rcx, [rbp+57h+var_68]
0x18008e7fb  sub     rdx, [rsi+0D8h]
0x18008e802  xorps   xmm0, xmm0
0x18008e805  sar     rdx, 3
0x18008e809  movdqu  [rbp+57h+var_68], xmm0
0x18008e80e  mov     [rbp+57h+var_58], r12
0x18008e812  call    ?reserve@?$vector@IV?$allocator@I@std@@@std@@QEAAX_K@Z; std::vector<uint>::reserve(unsigned __int64)
0x18008e817  mov     rdi, [rsi+0E0h]
0x18008e81e  mov     rbx, [rsi+0D8h]
0x18008e825  jmp     short loc_18008E857
0x18008e827  mov     rax, [rbx]
0x18008e82a  mov     rdx, qword ptr [rbp+57h+var_68+8]
0x18008e82e  mov     ecx, [rax+90h]
0x18008e834  mov     dword ptr [rbp+57h+var_A0], ecx
0x18008e837  cmp     rdx, [rbp+57h+var_58]
0x18008e83b  jz      short loc_18008E846
0x18008e83d  mov     [rdx], ecx
0x18008e83f  add     qword ptr [rbp+57h+var_68+8], 4
0x18008e844  jmp     short loc_18008E853
0x18008e846  lea     r8, [rbp+57h+var_A0]
0x18008e84a  lea     rcx, [rbp+57h+var_68]
0x18008e84e  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x18008e853  add     rbx, 8
0x18008e857  cmp     rbx, rdi
0x18008e85a  jnz     short loc_18008E827
0x18008e85c  mov     r9, qword ptr [rbp+57h+var_68+8]
0x18008e860  mov     edx, 2
0x18008e865  mov     r8, qword ptr [rbp+57h+var_68]
0x18008e869  mov     rcx, rsi
0x18008e86c  sub     r9, r8
0x18008e86f  sar     r9, 2
0x18008e873  call    ?SetReferenceArrayProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@PEBI_K@Z; Windows::UI::Composition::ProxyObject::SetReferenceArrayProperty(DCOMPOSITION_PROPERTY_ID,uint const *,unsigned __int64)
0x18008e878  mov     rbx, [rsi]
0x18008e87b  lea     r9, [rbp+57h+string]; string
0x18008e87f  mov     r14, [rsi+0B0h]
0x18008e886  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18008e88a  mov     edx, 9; length
0x18008e88f  mov     [rbp+57h+string], r12
0x18008e893  lea     rcx, aTriggered; "Triggered"
0x18008e89a  call    cs:__imp_WindowsCreateStringReference
0x18008e8a0  xor     r9d, r9d; lpArguments
0x18008e8a3  test    eax, eax
0x18008e8a5  jns     short loc_18008E8B7
0x18008e8a7  xor     r8d, r8d; nNumberOfArguments
0x18008e8aa  lea     edx, [r9+1]; dwExceptionFlags
0x18008e8ae  mov     ecx, eax; dwExceptionCode
0x18008e8b0  call    cs:__imp_RaiseException
0x18008e8b6  int     3; Trap to Debugger
0x18008e8b7  mov     rdx, [rbp+57h+string]
0x18008e8bb  lea     rdi, [rsi+0D0h]
0x18008e8c2  mov     rax, [rbx+98h]
0x18008e8c9  mov     r8, r14
0x18008e8cc  mov     rcx, rsi
0x18008e8cf  mov     qword ptr [rsp+0D0h+var_B0], rdi; int
0x18008e8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e8d9  mov     ebx, eax
0x18008e8db  test    eax, eax
0x18008e8dd  jns     short loc_18008E905
0x18008e8df  mov     rcx, [rbp+5Fh]; this
0x18008e8e3  lea     r8, aOnecoreuapWind_111; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18008e8ea  mov     r9d, eax; char *
0x18008e8ed  mov     edx, 8Fh; void *
0x18008e8f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e8f7  lea     rcx, [rbp+57h+var_68]
0x18008e8fb  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18008e900  jmp     loc_18008E7D4
0x18008e905  mov     r8, [rdi]
0x18008e908  mov     edx, 1
0x18008e90d  mov     rcx, rsi
0x18008e910  mov     r8d, [r8+90h]
0x18008e917  call    ?SetReferenceProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@I@Z; Windows::UI::Composition::ProxyObject::SetReferenceProperty(DCOMPOSITION_PROPERTY_ID,uint)
0x18008e91c  lea     rcx, [rbp+57h+var_68]
0x18008e920  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18008e925  xor     eax, eax
0x18008e927  mov     rcx, [rbp+57h+var_30]
0x18008e92b  xor     rcx, rsp; StackCookie
0x18008e92e  call    __security_check_cookie
0x18008e933  lea     r11, [rsp+0D0h+var_20]
0x18008e93b  mov     rbx, [r11+38h]
0x18008e93f  mov     rsi, [r11+40h]
0x18008e943  mov     rsp, r11
0x18008e946  pop     r15
0x18008e948  pop     r14
0x18008e94a  pop     r12
0x18008e94c  pop     rdi
0x18008e94d  pop     rbp
0x18008e94e  retn
```
