# Windows::UI::Composition::Interactions::VisualInteractionSource::CreateConditionalExpressionAnimator(gsl::span<Windows::UI::Composition::Interactions::ICompositionConditionalValue *,-1>,SourceModifierIndex,Windows::UI::Composition::CompositionPropertyAnimator * *)

- ea: `0x180079a18`
- end: `0x180079eef`
- name: `?CreateConditionalExpressionAnimator@VisualInteractionSource@Interactions@Composition@UI@Windows@@AEAAJV?$span@PEAUICompositionConditionalValue@Interactions@Composition@UI@Windows@@$0?0@gsl@@W4SourceModifierIndex@@PEAPEAVCompositionPropertyAnimator@345@@Z`
- size: `1239`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180079ef8`

## callees

- `0x18000f810`
- `0x18001358c`
- `0x1800171b0`
- `0x1800348d0`
- `0x180038c10`
- `0x1800399c0`
- `0x180048980`
- `0x180073388`
- `0x180075ac4`
- `0x18007810c`
- `0x180078ec0`
- `0x180079a18`
- `0x18008d3d0`
- `0x18008f00c`
- `0x1800afd98`
- `0x1800dee2c`
- `0x1800f6f10`
- `0x1800f7a80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180079bd9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180079c6a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180079bd9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180079c6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079bbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079bbf`

## string_xrefs

- `0x180079af8`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositioninteractionsource.cpp`
- `0x180079ca3`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositioninteractionsource.cpp`
- `0x180079dd4`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositioninteractionsource.cpp`
- `0x180079e37`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositioninteractionsource.cpp`
- `0x180079e84`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositioninteractionsource.cpp`
- `0x180079ebb`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositioninteractionsource.cpp`
- `0x180079e22`: `An animation template on a ConditionalValue was modified during PopulatePropertyInfo call.`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::Interactions::VisualInteractionSource::CreateConditionalExpressionAnimator(
        __int64 a1,
        _QWORD *a2,
        int a3,
        Microsoft::WRL2::NestableRuntimeClass **a4)
{
  __int64 v4; // r15
  __int64 v8; // rdi
  void *v9; // rax
  Windows::UI::Composition::CompositionAnimation *v10; // rax
  Windows::UI::Composition::CompositionAnimation *v11; // rbx
  int v12; // edi
  struct IUnknown **v14; // r14
  struct IUnknown **v15; // r12
  const WCHAR *v16; // rdi
  int v17; // esi
  int v18; // esi
  int v19; // esi
  unsigned __int64 v20; // rsi
  unsigned int v21; // eax
  UINT32 v22; // edx
  HRESULT v23; // eax
  struct IUnknown *v24; // rdx
  struct Microsoft::WRL2::ContextSession *v25; // rcx
  int v26; // eax
  Microsoft::WRL2::NestableRuntimeClass *v27; // rdi
  int v28; // r15d
  int v29; // eax
  int v30; // eax
  Microsoft::WRL2::NestableRuntimeClass *v31; // rcx
  int Instance; // eax
  _QWORD *v33; // r12
  unsigned int i; // r14d
  struct IUnknown **v35; // rax
  struct Microsoft::WRL2::ContextSession *v36; // rcx
  int v37; // eax
  Microsoft::WRL2::NestableRuntimeClass *v38; // rdi
  int v39; // [rsp+20h] [rbp-59h]
  int v40; // [rsp+20h] [rbp-59h]
  char *v41; // [rsp+28h] [rbp-51h]
  Microsoft::WRL2::NestableRuntimeClass *v42; // [rsp+40h] [rbp-39h] BYREF
  Microsoft::WRL2::NestableRuntimeClass *v43; // [rsp+48h] [rbp-31h] BYREF
  _QWORD *v44; // [rsp+50h] [rbp-29h] BYREF
  char *v45[2]; // [rsp+58h] [rbp-21h] BYREF
  char *v46; // [rsp+68h] [rbp-11h]
  Microsoft::WRL2::NestableRuntimeClass **v47; // [rsp+70h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-1h] BYREF
  HSTRING string; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = *a2;
  v47 = a4;
  v44 = a2;
  *a4 = 0;
  v46 = 0;
  *(_OWORD *)v45 = 0;
  if ( v4 )
  {
    v8 = *(_QWORD *)(a1 + 24);
    v9 = DefaultHeap::Alloc(0x188u);
    if ( v9 )
    {
      v10 = (Windows::UI::Composition::CompositionAnimation *)memset_0(v9, 0, 0x188u);
      v11 = v10;
      if ( v10 )
      {
        Windows::UI::Composition::CompositionAnimation::CompositionAnimation(v10);
        *(_QWORD *)v11 = &Windows::UI::Composition::ConditionalExpressionAnimation::`vftable';
        *((_QWORD *)v11 + 45) = 0;
        *((_QWORD *)v11 + 46) = 0;
        *((_QWORD *)v11 + 47) = 0;
      }
      else
      {
        v11 = 0;
      }
      *((_QWORD *)v11 + 1) = &Windows::UI::Composition::CompositionAnimation::s_InterfaceType;
      v12 = Windows::UI::Composition::ConditionalExpressionAnimation::RuntimeClassInitialize(v11, v8, 1);
      if ( v12 >= 0 )
      {
        v14 = (struct IUnknown **)a2[1];
        v15 = &v14[v4];
        while ( v14 != v15 )
        {
          v24 = *v14;
          v25 = *(struct Microsoft::WRL2::ContextSession **)(a1 + 24);
          v42 = 0;
          v26 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
                  v25,
                  v24,
                  (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::Interactions::CompositionConditionalValue::s_InterfaceType,
                  &v42);
          v27 = v42;
          v28 = v26;
          v43 = v42;
          if ( v26 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1C0,
              (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositioninteractionsource.cpp",
              (const char *)(unsigned int)v26,
              v39);
            if ( v27 )
            {
              v31 = v27;
LABEL_37:
              Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v31);
            }
            goto LABEL_38;
          }
          v29 = Windows::UI::Composition::Interactions::CompositionConditionalValue::AddToConditional(v42, v11);
          v28 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1C1,
              (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositioninteractionsource.cpp",
              (const char *)(unsigned int)v29,
              v39);
            Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(&v43);
LABEL_38:
            if ( v11 )
              Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v11);
            v12 = v28;
            goto LABEL_8;
          }
          v30 = *((_DWORD *)v27 + 44);
          LODWORD(v42) = v30;
          if ( v45[1] == v46 )
          {
            std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(v45, v45[1], &v42);
          }
          else
          {
            *(_DWORD *)v45[1] = v30;
            v45[1] += 4;
          }
          if ( v27 )
            Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v27);
          ++v14;
        }
        v16 = 0;
        if ( a3 )
        {
          v17 = a3 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( v18 )
            {
              v19 = v18 - 1;
              if ( v19 )
              {
                if ( v19 == 1 )
                  v16 = L"SourceModifierScale";
              }
              else
              {
                v16 = L"SourceModifierY";
              }
            }
            else
            {
              v16 = L"SourceModifierX";
            }
          }
          else
          {
            v16 = L"SourceModifierCenterpointY";
          }
        }
        else
        {
          v16 = L"SourceModifierCenterpointX";
        }
        v42 = 0;
        v20 = -1;
        string = 0;
        do
          ++v20;
        while ( v16[v20] );
        if ( v20 > 0xFFFFFFFF )
        {
          RaiseException(0x80070216, 1u, 0, 0);
          __debugbreak();
        }
        v21 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v20);
        v22 = v21 - 1;
        if ( (unsigned int)v20 < v21 )
          v22 = v20;
        v23 = WindowsCreateStringReference(v16, v22, &hstringHeader, &string);
        if ( v23 < 0 )
        {
          RaiseException(v23, 1u, 0, 0);
          __debugbreak();
        }
        Instance = Windows::UI::Composition::ConditionalExpressionAnimation::GenerateInstance(
                     v11,
                     v11,
                     0,
                     0,
                     (__int64)&v42);
        v12 = Instance;
        if ( Instance >= 0 )
        {
          v33 = v44;
          for ( i = 0; ; ++i )
          {
            if ( (unsigned __int64)i >= *v33 )
            {
              *v47 = v42;
              if ( v11 )
                Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v11);
              goto LABEL_53;
            }
            v44 = 0;
            Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(&v44);
            v35 = (struct IUnknown **)gsl::span<Windows::UI::Composition::Interactions::ICompositionConditionalValue *,-1>::operator[](
                                        v33,
                                        i);
            v36 = *(struct Microsoft::WRL2::ContextSession **)(a1 + 24);
            v43 = 0;
            v37 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
                    v36,
                    *v35,
                    (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::Interactions::CompositionConditionalValue::s_InterfaceType,
                    &v43);
            v38 = v43;
            v28 = v37;
            if ( v37 < 0 )
              break;
            if ( (v45[1] - v45[0]) >> 2 <= (unsigned __int64)i )
              std::_Dwm_Xlength_error(v45[0]);
            if ( *((_DWORD *)v43 + 44) != *(_DWORD *)&v45[0][4 * i] )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x1FF,
                (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositioninteractionsource.cpp",
                (const char *)0x8000FFFFLL,
                (int)"An animation template on a ConditionalValue was modified during PopulatePropertyInfo call.",
                v41);
              if ( v38 )
                Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v38);
              if ( v42 )
                Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v42);
              if ( v11 )
                Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v11);
              v12 = -2147418113;
              goto LABEL_8;
            }
            if ( v43 )
              Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v43);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1FB,
            (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositioninteractionsource.cpp",
            (const char *)(unsigned int)v37,
            v40);
          if ( v38 )
            Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v38);
          v31 = v42;
          if ( v42 )
            goto LABEL_37;
          goto LABEL_38;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F3,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositioninteractionsource.cpp",
          (const char *)(unsigned int)Instance,
          v40);
        if ( v42 )
          Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v42);
        if ( v11 )
          Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v11);
        goto LABEL_8;
      }
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v11);
    }
    else
    {
      v12 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositioninteractionsource.cpp",
      (const char *)(unsigned int)v12,
      v39);
LABEL_8:
    std::vector<unsigned int>::_Tidy(v45);
    return (unsigned int)v12;
  }
LABEL_53:
  std::vector<unsigned int>::_Tidy(v45);
  return 0;
}

```

## disassembly

```asm
0x180079a18  mov     [rsp-8+arg_10], rbx
0x180079a1d  push    rbp
0x180079a1e  push    rsi
0x180079a1f  push    rdi
0x180079a20  push    r12
0x180079a22  push    r13
0x180079a24  push    r14
0x180079a26  push    r15
0x180079a28  lea     rbp, [rsp-27h]
0x180079a2d  sub     rsp, 0A0h
0x180079a34  mov     rax, cs:__security_cookie
0x180079a3b  xor     rax, rsp
0x180079a3e  mov     [rbp+57h+var_38], rax
0x180079a42  mov     r15, [rdx]
0x180079a45  xor     r12d, r12d
0x180079a48  mov     [rbp+57h+var_60], r9
0x180079a4c  xorps   xmm0, xmm0
0x180079a4f  mov     [rbp+57h+var_80], rdx
0x180079a53  mov     esi, r8d
0x180079a56  mov     [r9], r12
0x180079a59  mov     r14, rdx
0x180079a5c  mov     [rbp+57h+var_68], r12
0x180079a60  mov     r13, rcx
0x180079a63  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x180079a68  test    r15, r15
0x180079a6b  jz      loc_180079DC0
0x180079a71  mov     rdi, [rcx+18h]
0x180079a75  mov     ebx, 188h
0x180079a7a  mov     ecx, ebx; unsigned __int64
0x180079a7c  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x180079a81  test    rax, rax
0x180079a84  jz      loc_180079C7D
0x180079a8a  mov     r8d, ebx; Size
0x180079a8d  xor     edx, edx; Val
0x180079a8f  mov     rcx, rax; void *
0x180079a92  call    memset_0
0x180079a97  mov     rbx, rax
0x180079a9a  test    rax, rax
0x180079a9d  jz      loc_180079E78
0x180079aa3  mov     rcx, rax; this
0x180079aa6  call    ??0CompositionAnimation@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::CompositionAnimation::CompositionAnimation(void)
0x180079aab  lea     rax, ??_7ConditionalExpressionAnimation@Composition@UI@Windows@@6B@; const Windows::UI::Composition::ConditionalExpressionAnimation::`vftable'
0x180079ab2  mov     [rbx], rax
0x180079ab5  mov     [rbx+168h], r12
0x180079abc  mov     [rbx+170h], r12
0x180079ac3  mov     [rbx+178h], r12
0x180079aca  lea     rax, ?s_InterfaceType@CompositionAnimation@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::CompositionAnimation::s_InterfaceType
0x180079ad1  mov     r8d, 1
0x180079ad7  mov     rdx, rdi
0x180079ada  mov     [rbx+8], rax
0x180079ade  mov     rcx, rbx
0x180079ae1  call    ?RuntimeClassInitialize@ConditionalExpressionAnimation@Composition@UI@Windows@@QEAAJPEAVCompositor@234@W4Enum@ConditionalExpressionAnimationSelectionMode@@@Z; Windows::UI::Composition::ConditionalExpressionAnimation::RuntimeClassInitialize(Windows::UI::Composition::Compositor *,ConditionalExpressionAnimationSelectionMode::Enum)
0x180079ae6  mov     edi, eax
0x180079ae8  test    eax, eax
0x180079aea  jns     short loc_180079B3E
0x180079aec  mov     rcx, rbx; this
0x180079aef  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079af4  mov     rcx, [rbp+5Fh]; this
0x180079af8  lea     r8, aOnecoreuapWind_46; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180079aff  mov     r9d, edi; char *
0x180079b02  mov     edx, 1B8h; void *
0x180079b07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079b0c  lea     rcx, [rbp+57h+var_78]
0x180079b10  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180079b15  mov     eax, edi
0x180079b17  mov     rcx, [rbp+57h+var_38]
0x180079b1b  xor     rcx, rsp; StackCookie
0x180079b1e  call    __security_check_cookie
0x180079b23  mov     rbx, [rsp+0D0h+arg_10]
0x180079b2b  add     rsp, 0A0h
0x180079b32  pop     r15
0x180079b34  pop     r14
0x180079b36  pop     r13
0x180079b38  pop     r12
0x180079b3a  pop     rdi
0x180079b3b  pop     rsi
0x180079b3c  pop     rbp
0x180079b3d  retn
0x180079b3e  mov     r14, [r14+8]
0x180079b42  lea     r12, [r14+r15*8]
0x180079b46  xor     r15d, r15d
0x180079b49  cmp     r14, r12
0x180079b4c  jnz     loc_180079BE0
0x180079b52  mov     rdi, r15
0x180079b55  test    esi, esi
0x180079b57  jz      loc_180079EDD
0x180079b5d  sub     esi, 1
0x180079b60  jz      loc_180079C93
0x180079b66  sub     esi, 1
0x180079b69  jz      loc_180079CD9
0x180079b6f  sub     esi, 1
0x180079b72  jz      loc_180079C71
0x180079b78  cmp     esi, 1
0x180079b7b  jz      loc_180079C87
0x180079b81  mov     [rbp+57h+var_90], r15
0x180079b85  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180079b89  mov     [rbp+57h+string], r15
0x180079b8d  inc     rsi
0x180079b90  cmp     [rdi+rsi*2], r15w
0x180079b95  jnz     short loc_180079B8D
0x180079b97  mov     eax, 0FFFFFFFFh
0x180079b9c  cmp     rsi, rax
0x180079b9f  ja      loc_180079C5B
0x180079ba5  mov     ecx, esi; unsigned int
0x180079ba7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180079bac  cmp     esi, eax
0x180079bae  lea     r9, [rbp+57h+string]; string
0x180079bb2  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180079bb6  mov     rcx, rdi; sourceString
0x180079bb9  lea     edx, [rax-1]
0x180079bbc  cmovb   edx, esi; length
0x180079bbf  call    cs:__imp_WindowsCreateStringReference
0x180079bc5  test    eax, eax
0x180079bc7  jns     loc_180079CE5
0x180079bcd  xor     r9d, r9d; lpArguments
0x180079bd0  xor     r8d, r8d; nNumberOfArguments
0x180079bd3  mov     ecx, eax; dwExceptionCode
0x180079bd5  lea     edx, [r9+1]; dwExceptionFlags
0x180079bd9  call    cs:__imp_RaiseException
0x180079bdf  int     3; Trap to Debugger
0x180079be0  mov     rdx, [r14]; struct IUnknown *
0x180079be3  lea     r9, [rbp+57h+var_90]; struct Microsoft::WRL2::ContextRuntimeClass **
0x180079be7  mov     rcx, [r13+18h]; struct Microsoft::WRL2::ContextSession *
0x180079beb  lea     r8, ?s_InterfaceType@CompositionConditionalValue@Interactions@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x180079bf2  mov     [rbp+57h+var_90], r15
0x180079bf6  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x180079bfb  mov     rdi, [rbp+57h+var_90]
0x180079bff  mov     r15d, eax
0x180079c02  mov     [rbp+57h+var_88], rdi
0x180079c06  test    eax, eax
0x180079c08  js      loc_180079C9F
0x180079c0e  mov     rdx, rbx; struct Windows::UI::Composition::ConditionalExpressionAnimation *
0x180079c11  mov     rcx, rdi; this
0x180079c14  call    ?AddToConditional@CompositionConditionalValue@Interactions@Composition@UI@Windows@@QEAAJPEAVConditionalExpressionAnimation@345@@Z; Windows::UI::Composition::Interactions::CompositionConditionalValue::AddToConditional(Windows::UI::Composition::ConditionalExpressionAnimation *)
0x180079c19  mov     r15d, eax
0x180079c1c  test    eax, eax
0x180079c1e  js      loc_180079EB7
0x180079c24  mov     rdx, [rbp+57h+var_78+8]
0x180079c28  mov     eax, [rdi+0B0h]
0x180079c2e  mov     dword ptr [rbp+57h+var_90], eax
0x180079c31  cmp     rdx, [rbp+57h+var_68]
0x180079c35  jz      loc_180079E0C
0x180079c3b  mov     [rdx], eax
0x180079c3d  add     [rbp+57h+var_78+8], 4
0x180079c42  xor     r15d, r15d
0x180079c45  test    rdi, rdi
0x180079c48  jz      short loc_180079C52
0x180079c4a  mov     rcx, rdi; this
0x180079c4d  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079c52  add     r14, 8
0x180079c56  jmp     loc_180079B49
0x180079c5b  xor     r9d, r9d; lpArguments
0x180079c5e  xor     r8d, r8d; nNumberOfArguments
0x180079c61  mov     ecx, 80070216h; dwExceptionCode
0x180079c66  lea     edx, [r9+1]; dwExceptionFlags
0x180079c6a  call    cs:__imp_RaiseException
0x180079c70  int     3; Trap to Debugger
0x180079c71  lea     rdi, aSourcemodifier_0; "SourceModifierY"
0x180079c78  jmp     loc_180079B81
0x180079c7d  mov     edi, 8007000Eh
0x180079c82  jmp     loc_180079AF4
0x180079c87  lea     rdi, aSourcemodifier_3; "SourceModifierScale"
0x180079c8e  jmp     loc_180079B81
0x180079c93  lea     rdi, aSourcemodifier_1; "SourceModifierCenterpointY"
0x180079c9a  jmp     loc_180079B81
0x180079c9f  mov     rcx, [rbp+5Fh]; this
0x180079ca3  lea     r8, aOnecoreuapWind_46; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180079caa  mov     r9d, r15d; char *
0x180079cad  mov     edx, 1C0h; void *
0x180079cb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079cb7  test    rdi, rdi
0x180079cba  jz      short loc_180079CC4
0x180079cbc  mov     rcx, rdi; this
0x180079cbf  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079cc4  test    rbx, rbx
0x180079cc7  jz      short loc_180079CD1
0x180079cc9  mov     rcx, rbx; this
0x180079ccc  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079cd1  mov     edi, r15d
0x180079cd4  jmp     loc_180079B0C
0x180079cd9  lea     rdi, aSourcemodifier; "SourceModifierX"
0x180079ce0  jmp     loc_180079B81
0x180079ce5  mov     r9, [rbp+57h+string]
0x180079ce9  lea     rax, [rbp+57h+var_90]
0x180079ced  mov     [rsp+0D0h+var_A0], rax; __int64
0x180079cf2  mov     r8, r13
0x180079cf5  mov     [rsp+0D0h+var_A8], r15; char *
0x180079cfa  mov     rdx, rbx; this
0x180079cfd  mov     rcx, rbx; struct Windows::UI::Composition::CompositionObject *
0x180079d00  mov     [rsp+0D0h+var_B0], r15; int
0x180079d05  call    ?GenerateInstance@ConditionalExpressionAnimation@Composition@UI@Windows@@UEAAJPEAVCompositionAnimation@234@PEAVCompositionObject@234@PEAUHSTRING__@@PEAVSubchannelMaskInfo@@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@PEAPEAVCompositionPropertyAnimator@234@@Z; Windows::UI::Composition::ConditionalExpressionAnimation::GenerateInstance(Windows::UI::Composition::CompositionAnimation *,Windows::UI::Composition::CompositionObject *,HSTRING__ *,SubchannelMaskInfo *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry> *,Windows::UI::Composition::CompositionPropertyAnimator * *)
0x180079d0a  mov     edi, eax
0x180079d0c  test    eax, eax
0x180079d0e  js      loc_180079DD0
0x180079d14  mov     r12, [rbp+57h+var_80]
0x180079d18  mov     r14d, r15d
0x180079d1b  mov     esi, r14d
0x180079d1e  cmp     rsi, [r12]
0x180079d22  jnb     loc_180079DA8
0x180079d28  lea     rcx, [rbp+57h+var_80]
0x180079d2c  mov     [rbp+57h+var_80], r15
0x180079d30  call    ?InternalUnlock@?$RefPtr@VNaturalMotionAnimation@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(void)
0x180079d35  mov     edx, esi
0x180079d37  mov     rcx, r12
0x180079d3a  call    ??A?$span@PEAUICompositionConditionalValue@Interactions@Composition@UI@Windows@@$0?0@gsl@@QEBAAEAPEAUICompositionConditionalValue@Interactions@Composition@UI@Windows@@_K@Z; gsl::span<Windows::UI::Composition::Interactions::ICompositionConditionalValue *,-1>::operator[](unsigned __int64)
0x180079d3f  mov     rcx, [r13+18h]; struct Microsoft::WRL2::ContextSession *
0x180079d43  lea     r9, [rbp+57h+var_88]; struct Microsoft::WRL2::ContextRuntimeClass **
0x180079d47  lea     r8, ?s_InterfaceType@CompositionConditionalValue@Interactions@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x180079d4e  mov     [rbp+57h+var_88], r15
0x180079d52  mov     rdx, [rax]; struct IUnknown *
0x180079d55  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x180079d5a  mov     rdi, [rbp+57h+var_88]
0x180079d5e  mov     r15d, eax
0x180079d61  test    eax, eax
0x180079d63  js      loc_180079E80
0x180079d69  mov     rax, [rbp+57h+var_78+8]
0x180079d6d  mov     rcx, [rbp+57h+var_78]; char *
0x180079d71  sub     rax, rcx
0x180079d74  sar     rax, 2
0x180079d78  cmp     rax, rsi
0x180079d7b  jbe     loc_180079EE9
0x180079d81  mov     eax, [rcx+rsi*4]
0x180079d84  cmp     [rdi+0B0h], eax
0x180079d8a  jnz     loc_180079E1E
0x180079d90  xor     r15d, r15d
0x180079d93  test    rdi, rdi
0x180079d96  jz      short loc_180079DA0
0x180079d98  mov     rcx, rdi; this
0x180079d9b  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079da0  inc     r14d
0x180079da3  jmp     loc_180079D1B
0x180079da8  mov     rcx, [rbp+57h+var_60]
0x180079dac  mov     rax, [rbp+57h+var_90]
0x180079db0  mov     [rcx], rax
0x180079db3  test    rbx, rbx
0x180079db6  jz      short loc_180079DC0
0x180079db8  mov     rcx, rbx; this
0x180079dbb  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079dc0  lea     rcx, [rbp+57h+var_78]
0x180079dc4  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180079dc9  xor     eax, eax
0x180079dcb  jmp     loc_180079B17
0x180079dd0  mov     rcx, [rbp+5Fh]; this
0x180079dd4  lea     r8, aOnecoreuapWind_46; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180079ddb  mov     r9d, eax; char *
0x180079dde  mov     edx, 1F3h; void *
0x180079de3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079de8  mov     rcx, [rbp+57h+var_90]; this
0x180079dec  test    rcx, rcx
0x180079def  jz      short loc_180079DF6
0x180079df1  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079df6  test    rbx, rbx
0x180079df9  jz      loc_180079B0C
0x180079dff  mov     rcx, rbx; this
0x180079e02  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079e07  jmp     loc_180079B0C
0x180079e0c  lea     r8, [rbp+57h+var_90]
0x180079e10  lea     rcx, [rbp+57h+var_78]
0x180079e14  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x180079e19  jmp     loc_180079C42
0x180079e1e  mov     rcx, [rbp+5Fh]; this
0x180079e22  lea     rax, aAnAnimationTem_0; "An animation template on a ConditionalV"...
0x180079e29  mov     r14d, 8000FFFFh
0x180079e2f  mov     [rsp+0D0h+var_B0], rax; int
0x180079e34  mov     r9d, r14d; char *
0x180079e37  lea     r8, aOnecoreuapWind_46; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180079e3e  mov     edx, 1FFh; void *
0x180079e43  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180079e48  test    rdi, rdi
0x180079e4b  jz      short loc_180079E55
0x180079e4d  mov     rcx, rdi; this
0x180079e50  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079e55  mov     rcx, [rbp+57h+var_90]; this
0x180079e59  test    rcx, rcx
0x180079e5c  jz      short loc_180079E63
0x180079e5e  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079e63  test    rbx, rbx
0x180079e66  jz      short loc_180079E70
0x180079e68  mov     rcx, rbx; this
0x180079e6b  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079e70  mov     edi, r14d
0x180079e73  jmp     loc_180079B0C
0x180079e78  mov     rbx, r12
0x180079e7b  jmp     loc_180079ACA
0x180079e80  mov     rcx, [rbp+5Fh]; this
0x180079e84  lea     r8, aOnecoreuapWind_46; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180079e8b  mov     r9d, r15d; char *
0x180079e8e  mov     edx, 1FBh; void *
0x180079e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079e98  test    rdi, rdi
0x180079e9b  jz      short loc_180079EA5
0x180079e9d  mov     rcx, rdi; this
0x180079ea0  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180079ea5  mov     rcx, [rbp+57h+var_90]
0x180079ea9  test    rcx, rcx
0x180079eac  jnz     loc_180079CBF
0x180079eb2  jmp     loc_180079CC4
0x180079eb7  mov     rcx, [rbp+5Fh]; this
0x180079ebb  lea     r8, aOnecoreuapWind_46; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180079ec2  mov     r9d, r15d; char *
  ... truncated ...
```
