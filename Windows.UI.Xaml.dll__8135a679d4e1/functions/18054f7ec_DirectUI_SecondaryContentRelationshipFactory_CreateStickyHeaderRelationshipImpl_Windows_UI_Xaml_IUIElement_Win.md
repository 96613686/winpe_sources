# DirectUI::SecondaryContentRelationshipFactory::CreateStickyHeaderRelationshipImpl(Windows::UI::Xaml::IUIElement *,Windows::UI::Xaml::IUIElement *,Windows::UI::Xaml::IDependencyObject *,Windows::UI::Xaml::IDependencyObject *,double,double,double,Windows::UI::Xaml::Internal::ISecondaryContentRelationship * *)

- ea: `0x18054f7ec`
- end: `0x18054fa53`
- name: `?CreateStickyHeaderRelationshipImpl@SecondaryContentRelationshipFactory@DirectUI@@AEAAJPEAUIUIElement@Xaml@UI@Windows@@0PEAUIDependencyObject@456@1NNNPEAPEAUISecondaryContentRelationship@Internal@456@@Z`
- size: `615`
- prototype: `HRESULT __fastcall(DirectUI::SecondaryContentRelationshipFactory *this, Windows::UI::Xaml::IUIElement *pScrollViewer, Windows::UI::Xaml::IUIElement *pPanelObject, Windows::UI::Xaml::IDependencyObject *pPanelTransform, Windows::UI::Xaml::IDependencyObject *pHeaderTransform, long double groupTopY, long double groupBottomY, long double headerHeight, Windows::UI::Xaml::Internal::ISecondaryContentRelationship **ppReturnValue)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180ada2e0`

## callees

- `0x180004bc0`
- `0x18010c6dc`
- `0x180384178`
- `0x18054f7ec`
- `0x18054fa5c`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18054fa04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18054fa12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18054fa21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18054fa2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18054fa04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18054fa12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18054fa21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18054fa2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18054f84d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18054f883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18054f8b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18054f8e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18054f84d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18054f883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18054f8b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18054f8e8`

## pseudocode

```c
__int64 __fastcall DirectUI::SecondaryContentRelationshipFactory::CreateStickyHeaderRelationshipImpl(
        DirectUI::SecondaryContentRelationshipFactory *this,
        Windows::UI::Xaml::IUIElement *pScrollViewer,
        Windows::UI::Xaml::IUIElement *pPanelObject,
        Windows::UI::Xaml::IDependencyObject *pPanelTransform,
        Windows::UI::Xaml::IDependencyObject *pHeaderTransform,
        long double groupTopY,
        long double groupBottomY,
        long double headerHeight,
        Windows::UI::Xaml::Internal::ISecondaryContentRelationship **ppReturnValue)
{
  unsigned int v9; // r14d
  HSTRING__ *hstring; // rbx
  HSTRING__ *v11; // rdi
  HRESULT String; // eax
  HRESULT v15; // eax
  HSTRING__ *strOrthogonalPrimaryContentProperty; // rsi
  HRESULT v17; // eax
  HRESULT v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  HRESULT v21; // eax
  HRESULT v22; // eax
  Windows::UI::Xaml::Internal::ISecondaryContentRelationship **v23; // r15
  HRESULT NPointSecondaryContentRelationship; // eax
  DirectUI::DirectManipulationProperty secondaryContentProperty; // [rsp+28h] [rbp-99h]
  DirectUI::DirectManipulationProperty orthogonalSecondaryContentProperty; // [rsp+40h] [rbp-81h]
  Windows::Internal::String strVerticalOffsetPropertyName; // [rsp+78h] [rbp-49h] BYREF
  HSTRING__ *target; // [rsp+80h] [rbp-41h] BYREF
  Windows::Internal::String strHorizontalOffsetPropertyName; // [rsp+88h] [rbp-39h] BYREF
  long double primaryContentValues[3]; // [rsp+90h] [rbp-31h] BYREF
  long double secondaryContentValues[10]; // [rsp+A8h] [rbp-19h] BYREF
  Windows::Internal::String strTranslateXPropertyName; // [rsp+108h] [rbp+47h] BYREF
  Windows::UI::Xaml::IUIElement *pPrimaryContent; // [rsp+110h] [rbp+4Fh]

  pPrimaryContent = pScrollViewer;
  v9 = 0;
  hstring = 0;
  v11 = 0;
  primaryContentValues[0] = 0.0;
  target = 0;
  strTranslateXPropertyName._hstring = 0;
  strVerticalOffsetPropertyName._hstring = 0;
  if ( !CQuirksMode2::QuirkEnableCustomParametricCurves() )
    return v9;
  strHorizontalOffsetPropertyName._hstring = 0;
  String = WindowsCreateString(L"HorizontalOffset", 0x10u, &strHorizontalOffsetPropertyName._hstring);
  v15 = Windows::Internal::String::FreeAndAssignOnSuccess(
          String,
          strHorizontalOffsetPropertyName._hstring,
          (HSTRING__ **)primaryContentValues);
  strOrthogonalPrimaryContentProperty = *(HSTRING__ **)&primaryContentValues[0];
  v9 = v15;
  if ( v15 < 0 )
  {
    OnFailure_2990_(v15);
    goto $Cleanup_4069;
  }
  primaryContentValues[0] = 0.0;
  v17 = WindowsCreateString(L"VerticalOffset", 0xEu, (HSTRING *)primaryContentValues);
  v18 = Windows::Internal::String::FreeAndAssignOnSuccess(v17, *(HSTRING__ **)&primaryContentValues[0], &target);
  v9 = v18;
  if ( v18 >= 0 )
  {
    primaryContentValues[0] = 0.0;
    v19 = WindowsCreateString(L"TranslateX", 0xAu, (HSTRING *)primaryContentValues);
    v20 = Windows::Internal::String::FreeAndAssignOnSuccess(
            v19,
            *(HSTRING__ **)&primaryContentValues[0],
            &strTranslateXPropertyName._hstring);
    v9 = v20;
    if ( v20 < 0 )
    {
      OnFailure_2990_(v20);
      hstring = strTranslateXPropertyName._hstring;
LABEL_15:
      if ( hstring )
        WindowsDeleteString(hstring);
      goto LABEL_17;
    }
    primaryContentValues[0] = 0.0;
    v21 = WindowsCreateString(L"TranslateY", 0xAu, (HSTRING *)primaryContentValues);
    v22 = Windows::Internal::String::FreeAndAssignOnSuccess(
            v21,
            *(HSTRING__ **)&primaryContentValues[0],
            &strVerticalOffsetPropertyName._hstring);
    v9 = v22;
    if ( v22 < 0 )
    {
      OnFailure_2990_(v22);
      hstring = strTranslateXPropertyName._hstring;
      v11 = strVerticalOffsetPropertyName._hstring;
    }
    else
    {
      v23 = ppReturnValue;
      hstring = strTranslateXPropertyName._hstring;
      v11 = strVerticalOffsetPropertyName._hstring;
      secondaryContentValues[0] = groupBottomY - headerHeight;
      LOBYTE(orthogonalSecondaryContentProperty) = 1;
      primaryContentValues[1] = fmin(0.0, groupTopY - 1.0);
      *(_QWORD *)&secondaryContentValues[3] = COERCE_UNSIGNED_INT64(groupBottomY - headerHeight - groupTopY) ^ _xmm;
      primaryContentValues[2] = groupTopY;
      *(_OWORD *)&secondaryContentValues[1] = 0;
      LOBYTE(secondaryContentProperty) = 2;
      NPointSecondaryContentRelationship = DirectUI::CreateNPointSecondaryContentRelationship(
                                             pPrimaryContent,
                                             pPanelObject,
                                             pPanelTransform,
                                             target,
                                             secondaryContentProperty,
                                             strVerticalOffsetPropertyName._hstring,
                                             strOrthogonalPrimaryContentProperty,
                                             orthogonalSecondaryContentProperty,
                                             strTranslateXPropertyName._hstring,
                                             3u,
                                             &primaryContentValues[1],
                                             &secondaryContentValues[1],
                                             ppReturnValue);
      v9 = NPointSecondaryContentRelationship;
      if ( NPointSecondaryContentRelationship < 0 )
        OnFailure_2990_(NPointSecondaryContentRelationship);
      else
        (*v23)->SetAuxiliaryDependencyPropertyHolder(*v23, pHeaderTransform);
    }
$Cleanup_4069:
    if ( v11 )
      WindowsDeleteString(v11);
    goto LABEL_15;
  }
  OnFailure_2990_(v18);
LABEL_17:
  if ( target )
    WindowsDeleteString(target);
  if ( strOrthogonalPrimaryContentProperty )
    WindowsDeleteString(strOrthogonalPrimaryContentProperty);
  return v9;
}

```

## disassembly

```asm
0x18054f7ec  mov     rax, rsp
0x18054f7ef  mov     [rax+18h], rbx
0x18054f7f3  mov     [rax+10h], pScrollViewer
0x18054f7f7  mov     [rax+8], rcx
0x18054f7fb  push    rbp
0x18054f7fc  push    rsi
0x18054f7fd  push    rdi
0x18054f7fe  push    r12
0x18054f800  push    r13
0x18054f802  push    r14
0x18054f804  push    r15
0x18054f806  lea     rbp, [rax-3Fh]
0x18054f80a  sub     rsp, 0C0h
0x18054f811  xor     r14d, r14d
0x18054f814  xor     ebx, ebx
0x18054f816  xor     edi, edi
0x18054f818  mov     [rbp+37h+primaryContentValues], r14
0x18054f81c  mov     [rbp+37h+target], r14
0x18054f820  mov     r12, pPanelTransform
0x18054f823  mov     [rbp+37h+strTranslateXPropertyName._hstring], rbx
0x18054f827  mov     r13, pPanelObject
0x18054f82a  mov     [rbp+37h+strVerticalOffsetPropertyName._hstring], rdi
0x18054f82e  call    ?QuirkEnableCustomParametricCurves@CQuirksMode2@@SA_NXZ; CQuirksMode2::QuirkEnableCustomParametricCurves(void)
0x18054f833  test    al, al
0x18054f835  jz      loc_18054FA35
0x18054f83b  lea     pPanelObject, [rbp+37h+strHorizontalOffsetPropertyName]; string
0x18054f83f  mov     [rbp+37h+strHorizontalOffsetPropertyName._hstring], rbx
0x18054f843  lea     edx, [rbx+10h]; length
0x18054f846  lea     rcx, aHorizontaloffs; "HorizontalOffset"
0x18054f84d  call    cs:__imp_WindowsCreateString
0x18054f853  mov     pScrollViewer, [rbp+37h+strHorizontalOffsetPropertyName._hstring]; newValue
0x18054f857  lea     pPanelObject, [rbp+37h+primaryContentValues]; target
0x18054f85b  mov     ecx, eax; hr
0x18054f85d  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18054f862  mov     rsi, [rbp+37h+primaryContentValues]
0x18054f866  mov     r14d, eax
0x18054f869  test    eax, eax
0x18054f86b  js      loc_18054F9F5
0x18054f871  lea     pPanelObject, [rbp+37h+primaryContentValues]; string
0x18054f875  mov     [rbp+37h+primaryContentValues], rbx
0x18054f879  lea     edx, [rbx+0Eh]; length
0x18054f87c  lea     rcx, aVerticaloffset; "VerticalOffset"
0x18054f883  call    cs:__imp_WindowsCreateString
0x18054f889  mov     pScrollViewer, [rbp+37h+primaryContentValues]; newValue
0x18054f88d  lea     pPanelObject, [rbp+37h+target]; target
0x18054f891  mov     ecx, eax; hr
0x18054f893  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18054f898  mov     r14d, eax
0x18054f89b  test    eax, eax
0x18054f89d  js      loc_18054F9EC
0x18054f8a3  mov     [rbp+37h+primaryContentValues], rbx
0x18054f8a7  lea     pPanelObject, [rbp+37h+primaryContentValues]; string
0x18054f8ab  lea     ebx, [rdi+0Ah]
0x18054f8ae  mov     edx, ebx; length
0x18054f8b0  lea     rcx, aTranslatex; "TranslateX"
0x18054f8b7  call    cs:__imp_WindowsCreateString
0x18054f8bd  mov     pScrollViewer, [rbp+37h+primaryContentValues]; newValue
0x18054f8c1  lea     pPanelObject, [rbp+37h+strTranslateXPropertyName]; target
0x18054f8c5  mov     ecx, eax; hr
0x18054f8c7  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18054f8cc  mov     r14d, eax
0x18054f8cf  test    eax, eax
0x18054f8d1  js      loc_18054F9DF
0x18054f8d7  lea     pPanelObject, [rbp+37h+primaryContentValues]; string
0x18054f8db  mov     [rbp+37h+primaryContentValues], rdi
0x18054f8df  mov     edx, ebx; length
0x18054f8e1  lea     rcx, aTranslatey; "TranslateY"
0x18054f8e8  call    cs:__imp_WindowsCreateString
0x18054f8ee  mov     pScrollViewer, [rbp+37h+primaryContentValues]; newValue
0x18054f8f2  lea     pPanelObject, [rbp+37h+strVerticalOffsetPropertyName]; target
0x18054f8f6  mov     ecx, eax; hr
0x18054f8f8  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18054f8fd  mov     r14d, eax
0x18054f900  test    eax, eax
0x18054f902  js      loc_18054F9CE
0x18054f908  movsd   xmm2, [rbp+37h+arg_28]
0x18054f90d  lea     rax, [rbp+37h+secondaryContentValues+8]
0x18054f911  mov     r15, [rbp+37h+ppSecondaryContentRelationship]
0x18054f918  movaps  xmm1, xmm2
0x18054f91b  subsd   xmm1, cs:__real@3ff0000000000000
0x18054f923  mov     rbx, [rbp+37h+strTranslateXPropertyName._hstring]
0x18054f927  xorps   xmm0, xmm0
0x18054f92a  mov     rdi, [rbp+37h+strVerticalOffsetPropertyName._hstring]
0x18054f92e  mov     pPanelObject, r12; pDependencyPropertyHolder
0x18054f931  mov     pPanelTransform, [rbp+37h+target]; strPrimaryContentProperty
0x18054f935  mov     pScrollViewer, r13; pSecondaryContent
0x18054f938  mov     rcx, [rbp+37h+pPrimaryContent]; pPrimaryContent
0x18054f93c  mov     [rsp+60h], r15; ppSecondaryContentRelationship
0x18054f941  minsd   xmm0, xmm1
0x18054f945  movsd   xmm1, [rbp+37h+arg_30]
0x18054f94a  subsd   xmm1, [rbp+37h+arg_38]
0x18054f94f  mov     [rsp+0F0h+pSecondaryContentValues], rax; pSecondaryContentValues
0x18054f954  lea     rax, [rbp+37h+primaryContentValues+8]
0x18054f958  mov     [rsp+0F0h+pPrimaryContentValues], rax; pPrimaryContentValues
0x18054f95d  mov     [rsp+0F0h+numPoints], 3; numPoints
0x18054f965  mov     [rsp+0F0h+strOrthogonalAssociatedDependencyProperty], rbx; strOrthogonalAssociatedDependencyProperty
0x18054f96a  movsd   [rbp+37h+secondaryContentValues], xmm1
0x18054f96f  subsd   xmm1, xmm2
0x18054f973  mov     byte ptr [rsp+0F0h+orthogonalSecondaryContentProperty], 1; orthogonalSecondaryContentProperty
0x18054f978  movsd   [rbp+37h+primaryContentValues+8], xmm0
0x18054f97d  xorps   xmm0, xmm0
0x18054f980  mov     [rsp+0F0h+strOrthogonalPrimaryContentProperty], rsi; strOrthogonalPrimaryContentProperty
0x18054f985  mov     [rsp+0F0h+strAssociatedDependencyProperty], rdi; strAssociatedDependencyProperty
0x18054f98a  xorps   xmm1, cs:__xmm@80000000000000008000000000000000
0x18054f991  movsd   [rbp+37h+var_38], xmm1
0x18054f996  movsd   [rbp+37h+primaryContentValues+10h], xmm2
0x18054f99b  movups  xmmword ptr [rbp+37h+secondaryContentValues+8], xmm0
0x18054f99f  mov     byte ptr [rsp+0F0h+secondaryContentProperty], 2; secondaryContentProperty
0x18054f9a4  call    ?CreateNPointSecondaryContentRelationship@DirectUI@@YAJPEAUIUIElement@Xaml@UI@Windows@@0PEAUIDependencyObject@345@PEAUHSTRING__@@W4DirectManipulationProperty@1@2232IPEBN4PEAPEAUISecondaryContentRelationship@Internal@345@@Z; DirectUI::CreateNPointSecondaryContentRelationship(Windows::UI::Xaml::IUIElement *,Windows::UI::Xaml::IUIElement *,Windows::UI::Xaml::IDependencyObject *,HSTRING__ *,DirectUI::DirectManipulationProperty,HSTRING__ *,HSTRING__ *,DirectUI::DirectManipulationProperty,HSTRING__ *,uint,double const *,double const *,Windows::UI::Xaml::Internal::ISecondaryContentRelationship * *)
0x18054f9a9  mov     r14d, eax
0x18054f9ac  test    eax, eax
0x18054f9ae  js      short loc_18054F9C5
0x18054f9b0  mov     rcx, [r15]
0x18054f9b3  mov     pScrollViewer, [rbp+37h+arg_20]
0x18054f9b7  mov     rax, [rcx]
0x18054f9ba  mov     rax, [rax+30h]
0x18054f9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18054f9c3  jmp     short $Cleanup_4069
0x18054f9c5  mov     ecx, eax; failedFrameHR
0x18054f9c7  call    OnFailure_2990_
0x18054f9cc  jmp     short $Cleanup_4069
0x18054f9ce  mov     ecx, eax; failedFrameHR
0x18054f9d0  call    OnFailure_2990_
0x18054f9d5  mov     rbx, [rbp+37h+strTranslateXPropertyName._hstring]
0x18054f9d9  mov     rdi, [rbp+37h+strVerticalOffsetPropertyName._hstring]
0x18054f9dd  jmp     short $Cleanup_4069
0x18054f9df  mov     ecx, eax; failedFrameHR
0x18054f9e1  call    OnFailure_2990_
0x18054f9e6  mov     rbx, [rbp+37h+strTranslateXPropertyName._hstring]
0x18054f9ea  jmp     short loc_18054FA0A
0x18054f9ec  mov     ecx, eax; failedFrameHR
0x18054f9ee  call    OnFailure_2990_
0x18054f9f3  jmp     short loc_18054FA18
0x18054f9f5  mov     ecx, eax; failedFrameHR
0x18054f9f7  call    OnFailure_2990_
0x18054f9fc  test    rdi, rdi
0x18054f9ff  jz      short loc_18054FA0A
0x18054fa01  mov     rcx, rdi; string
0x18054fa04  call    cs:__imp_WindowsDeleteString
0x18054fa0a  test    rbx, rbx
0x18054fa0d  jz      short loc_18054FA18
0x18054fa0f  mov     rcx, rbx; string
0x18054fa12  call    cs:__imp_WindowsDeleteString
0x18054fa18  mov     rcx, [rbp+37h+target]; string
0x18054fa1c  test    rcx, rcx
0x18054fa1f  jz      short loc_18054FA27
0x18054fa21  call    cs:__imp_WindowsDeleteString
0x18054fa27  test    rsi, rsi
0x18054fa2a  jz      short loc_18054FA35
0x18054fa2c  mov     rcx, rsi; string
0x18054fa2f  call    cs:__imp_WindowsDeleteString
0x18054fa35  mov     rbx, [rsp+0F0h+arg_10]
0x18054fa3d  mov     eax, r14d
0x18054fa40  add     rsp, 0C0h
0x18054fa47  pop     r15
0x18054fa49  pop     r14
0x18054fa4b  pop     r13
0x18054fa4d  pop     r12
0x18054fa4f  pop     rdi
0x18054fa50  pop     rsi
0x18054fa51  pop     rbp
0x18054fa52  retn
```
