# Windows::UI::Composition::CompositorCommon::CreateExpressionAnimation(HSTRING__ *,Windows::UI::Composition::ExpressionAnimation * *)

- ea: `0x1800336e8`
- end: `0x18003383e`
- name: `?CreateExpressionAnimation@CompositorCommon@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@PEAPEAVExpressionAnimation@234@@Z`
- size: `342`
- prototype: `int(Windows::UI::Composition::CompositorCommon *__hidden this, HSTRING, struct Windows::UI::Composition::ExpressionAnimation **)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18008b578`
- `0x1800b4500`
- `0x18016e8ac`

## callees

- `0x18000d8cc`
- `0x18000f810`
- `0x18001358c`
- `0x180030db8`
- `0x1800336e8`
- `0x1800348d0`
- `0x180038c10`
- `0x180039138`
- `0x180039638`
- `0x1800f7a80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003379d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003379d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003378a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003378a`

## string_xrefs

- `0x1800337e8`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x1800337c4`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtexpressionanimation.cpp`
- `0x180033820`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtexpressionanimation.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositorCommon::CreateExpressionAnimation(
        Windows::UI::Composition::CompositorCommon *this,
        HSTRING a2,
        struct Windows::UI::Composition::ExpressionAnimation **a3)
{
  void *v6; // rax
  Windows::UI::Composition::ExpressionAnimation *v7; // rax
  __int64 v8; // rbx
  unsigned int v9; // edi
  HSTRING v11; // rcx
  HRESULT v12; // eax
  __int64 v13; // rdx
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  *a3 = 0;
  v16 = 0;
  v6 = DefaultHeap::Alloc(0x3D8u);
  if ( v6 )
  {
    v7 = (Windows::UI::Composition::ExpressionAnimation *)memset_0(v6, 0, 0x3D8u);
    if ( v7 )
      v8 = Windows::UI::Composition::ExpressionAnimation::ExpressionAnimation(v7);
    else
      v8 = 0;
    *(_QWORD *)(v8 + 8) = &Windows::UI::Composition::ExpressionAnimation::s_InterfaceType;
    v9 = Windows::UI::Composition::CompositionAnimation::RuntimeClassInitialize(
           (Windows::UI::Composition::CompositionAnimation *)v8,
           this);
    if ( (v9 & 0x80000000) != 0 )
    {
      v13 = 54;
    }
    else
    {
      *(_DWORD *)(v8 + 316) = 0;
      if ( !a2 )
      {
LABEL_6:
        *a3 = (struct Windows::UI::Composition::ExpressionAnimation *)v8;
        return 0;
      }
      v11 = *(HSTRING *)(v8 + 952);
      if ( v11 )
      {
        WindowsDeleteString(v11);
        *(_QWORD *)(v8 + 952) = 0;
      }
      v12 = WindowsDuplicateString(a2, (HSTRING *)(v8 + 952));
      v9 = v12;
      if ( v12 >= 0 )
      {
        Windows::UI::Composition::ExpressionAnimationBuilder::Reset((Windows::UI::Composition::ExpressionAnimationBuilder *)(v8 + 376));
        Windows::UI::Composition::CompositionAnimation::InvalidateCache((Windows::UI::Composition::CompositionAnimation *)v8);
        goto LABEL_6;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A1,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtexpressionanimation.cpp",
        (const char *)(unsigned int)v12,
        v14);
      v13 = 61;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtexpressionanimation.cpp",
      (const char *)v9,
      v14);
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease((Microsoft::WRL2::NestableRuntimeClass *)v8);
  }
  else
  {
    v9 = -2147024882;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5CD,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
    (const char *)v9,
    v14);
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(&v16);
  return v9;
}

```

## disassembly

```asm
0x1800336e8  push    rbx
0x1800336ea  push    rsi
0x1800336eb  push    rdi
0x1800336ec  push    r14
0x1800336ee  sub     rsp, 28h
0x1800336f2  mov     rdi, rcx
0x1800336f5  mov     qword ptr [r8], 0
0x1800336fc  mov     ebx, 3D8h
0x180033701  mov     [rsp+48h+arg_0], 0
0x18003370a  mov     ecx, ebx; unsigned __int64
0x18003370c  mov     r14, r8
0x18003370f  mov     rsi, rdx
0x180033712  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x180033717  test    rax, rax
0x18003371a  jz      loc_18003380D
0x180033720  mov     r8d, ebx; Size
0x180033723  xor     edx, edx; Val
0x180033725  mov     rcx, rax; void *
0x180033728  call    memset_0
0x18003372d  test    rax, rax
0x180033730  jz      loc_180033814
0x180033736  mov     rcx, rax; this
0x180033739  call    ??0ExpressionAnimation@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::ExpressionAnimation::ExpressionAnimation(void)
0x18003373e  mov     rbx, rax
0x180033741  lea     rax, ?s_InterfaceType@ExpressionAnimation@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::ExpressionAnimation::s_InterfaceType
0x180033748  mov     rdx, rdi; struct Windows::UI::Composition::Compositor *
0x18003374b  mov     rcx, rbx; this
0x18003374e  mov     [rbx+8], rax
0x180033752  call    ?RuntimeClassInitialize@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAVCompositor@234@@Z; Windows::UI::Composition::CompositionAnimation::RuntimeClassInitialize(Windows::UI::Composition::Compositor *)
0x180033757  mov     edi, eax
0x180033759  test    eax, eax
0x18003375b  js      short loc_1800337BF
0x18003375d  mov     dword ptr [rbx+13Ch], 0
0x180033767  test    rsi, rsi
0x18003376a  jnz     short loc_18003377B
0x18003376c  mov     [r14], rbx
0x18003376f  xor     eax, eax
0x180033771  add     rsp, 28h
0x180033775  pop     r14
0x180033777  pop     rdi
0x180033778  pop     rsi
0x180033779  pop     rbx
0x18003377a  retn
0x18003377b  lea     rdi, [rbx+3B8h]
0x180033782  mov     rcx, [rdi]; string
0x180033785  test    rcx, rcx
0x180033788  jz      short loc_180033797
0x18003378a  call    cs:__imp_WindowsDeleteString
0x180033790  mov     qword ptr [rdi], 0
0x180033797  mov     rdx, rdi; newString
0x18003379a  mov     rcx, rsi; string
0x18003379d  call    cs:__imp_WindowsDuplicateString
0x1800337a3  mov     edi, eax
0x1800337a5  test    eax, eax
0x1800337a7  js      short loc_18003381B
0x1800337a9  lea     rcx, [rbx+178h]; this
0x1800337b0  call    ?Reset@ExpressionAnimationBuilder@Composition@UI@Windows@@QEAAJXZ; Windows::UI::Composition::ExpressionAnimationBuilder::Reset(void)
0x1800337b5  mov     rcx, rbx; this
0x1800337b8  call    ?InvalidateCache@CompositionAnimation@Composition@UI@Windows@@IEAAXXZ; Windows::UI::Composition::CompositionAnimation::InvalidateCache(void)
0x1800337bd  jmp     short loc_18003376C
0x1800337bf  mov     edx, 36h ; '6'; void *
0x1800337c4  lea     rsi, aOnecoreuapWind_19; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800337cb  mov     rcx, [rsp+48h]; this
0x1800337d0  mov     r9d, edi; char *
0x1800337d3  mov     r8, rsi; unsigned int
0x1800337d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800337db  mov     rcx, rbx; this
0x1800337de  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800337e3  mov     rcx, [rsp+48h]; this
0x1800337e8  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800337ef  mov     r9d, edi; char *
0x1800337f2  mov     edx, 5CDh; void *
0x1800337f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800337fc  lea     rcx, [rsp+48h+arg_0]
0x180033801  call    ?InternalUnlock@?$RefPtr@VNaturalMotionAnimation@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(void)
0x180033806  mov     eax, edi
0x180033808  jmp     loc_180033771
0x18003380d  mov     edi, 8007000Eh
0x180033812  jmp     short loc_1800337E3
0x180033814  xor     ebx, ebx
0x180033816  jmp     loc_180033741
0x18003381b  mov     rcx, [rsp+48h]; this
0x180033820  lea     rsi, aOnecoreuapWind_19; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180033827  mov     r8, rsi; unsigned int
0x18003382a  mov     r9d, edi; char *
0x18003382d  mov     edx, 1A1h; void *
0x180033832  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033837  mov     edx, 3Dh ; '='
0x18003383c  jmp     short loc_1800337CB
```
