# Windows::UI::Composition::ProxyObject::StartAnimationGroup(Windows::UI::Composition::ICompositionAnimationBase *)

- ea: `0x180072b50`
- end: `0x180072cfa`
- name: `?StartAnimationGroup@ProxyObject@Composition@UI@Windows@@UEAAJPEAUICompositionAnimationBase@234@@Z`
- size: `426`
- prototype: `int(Windows::UI::Composition::ProxyObject *__hidden this, struct Windows::UI::Composition::ICompositionAnimationBase *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000bc00`
- `0x18000f810`
- `0x18001358c`
- `0x180048980`
- `0x180072668`
- `0x180072b50`
- `0x180074480`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072c53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072cdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072c53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072cdd`

## string_xrefs

- `0x180072c91`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtproxyobject.cpp`
- `0x180072cc5`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtproxyobject.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ProxyObject::StartAnimationGroup(
        Windows::UI::Composition::ProxyObject *this,
        struct IUnknown *a2)
{
  struct Microsoft::WRL2::ContextSession *v4; // rcx
  int v5; // eax
  Windows::UI::Composition::CompositionAnimation *v6; // rbx
  struct Microsoft::WRL2::ContextSession *v7; // rcx
  int v8; // eax
  Microsoft::WRL2::NestableRuntimeClass *v9; // rdi
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // esi
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  HSTRING string; // [rsp+60h] [rbp+28h] BYREF

  string = 0;
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&string);
  v4 = (struct Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
  string = 0;
  v5 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
         v4,
         a2,
         (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionAnimation::s_InterfaceType,
         (struct Microsoft::WRL2::ContextRuntimeClass **)&string);
  v6 = (Windows::UI::Composition::CompositionAnimation *)string;
  if ( v5 >= 0 && string )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    Windows::UI::Composition::CompositionAnimation::GetTarget(v6, &string);
    v11 = (*(__int64 (__fastcall **)(Windows::UI::Composition::ProxyObject *, HSTRING, Windows::UI::Composition::CompositionAnimation *, _QWORD))(*(_QWORD *)this + 152LL))(
            this,
            string,
            v6,
            0);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x297,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtproxyobject.cpp",
        (const char *)(unsigned int)v11,
        0);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v6);
      return v12;
    }
    WindowsDeleteString(string);
    goto LABEL_5;
  }
  string = 0;
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&string);
  v7 = (struct Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
  string = 0;
  v8 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
         v7,
         a2,
         (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionAnimationGroup::s_InterfaceType,
         (struct Microsoft::WRL2::ContextRuntimeClass **)&string);
  v9 = (Microsoft::WRL2::NestableRuntimeClass *)string;
  if ( v8 < 0 )
    goto LABEL_3;
  if ( !string )
  {
LABEL_5:
    if ( v6 )
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v6);
    return 0;
  }
  v13 = Windows::UI::Composition::CompositionAnimationGroup::PlayAnimations(
          (__int64)string,
          (HSTRING)this,
          0,
          0,
          &string,
          0);
  v14 = v13;
  if ( v13 >= 0 )
  {
LABEL_3:
    if ( v9 )
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v9);
    goto LABEL_5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A8,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtproxyobject.cpp",
    (const char *)(unsigned int)v13,
    v15);
  Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v9);
  if ( v6 )
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v6);
  return v14;
}

```

## disassembly

```asm
0x180072b50  push    rbp
0x180072b52  push    rbx
0x180072b53  push    rsi
0x180072b54  push    rdi
0x180072b55  mov     rbp, rsp
0x180072b58  sub     rsp, 38h
0x180072b5c  mov     rsi, rcx
0x180072b5f  mov     [rbp+string], 0
0x180072b67  lea     rcx, [rbp+string]; void *
0x180072b6b  mov     rdi, rdx
0x180072b6e  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180072b73  mov     rcx, [rsi+18h]; struct Microsoft::WRL2::ContextSession *
0x180072b77  lea     r9, [rbp+string]; struct Microsoft::WRL2::ContextRuntimeClass **
0x180072b7b  lea     r8, ?s_InterfaceType@CompositionAnimation@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x180072b82  mov     [rbp+string], 0
0x180072b8a  mov     rdx, rdi; struct IUnknown *
0x180072b8d  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x180072b92  mov     rbx, [rbp+string]
0x180072b96  test    eax, eax
0x180072b98  jns     short loc_180072BFB
0x180072b9a  lea     rcx, [rbp+string]; void *
0x180072b9e  mov     [rbp+string], 0
0x180072ba6  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180072bab  mov     rcx, [rsi+18h]; struct Microsoft::WRL2::ContextSession *
0x180072baf  lea     r9, [rbp+string]; struct Microsoft::WRL2::ContextRuntimeClass **
0x180072bb3  lea     r8, ?s_InterfaceType@CompositionAnimationGroup@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x180072bba  mov     [rbp+string], 0
0x180072bc2  mov     rdx, rdi; struct IUnknown *
0x180072bc5  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x180072bca  mov     rdi, [rbp+string]
0x180072bce  test    eax, eax
0x180072bd0  jns     loc_180072C5B
0x180072bd6  test    rdi, rdi
0x180072bd9  jz      short loc_180072BE3
0x180072bdb  mov     rcx, rdi; this
0x180072bde  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180072be3  test    rbx, rbx
0x180072be6  jz      short loc_180072BF0
0x180072be8  mov     rcx, rbx; this
0x180072beb  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180072bf0  xor     eax, eax
0x180072bf2  add     rsp, 38h
0x180072bf6  pop     rdi
0x180072bf7  pop     rsi
0x180072bf8  pop     rbx
0x180072bf9  pop     rbp
0x180072bfa  retn
0x180072bfb  test    rbx, rbx
0x180072bfe  jz      short loc_180072B9A
0x180072c00  xor     ecx, ecx; string
0x180072c02  mov     [rbp+string], 0
0x180072c0a  call    cs:__imp_WindowsDeleteString
0x180072c10  lea     rdx, [rbp+string]; HSTRING *
0x180072c14  mov     [rbp+string], 0
0x180072c1c  mov     rcx, rbx; this
0x180072c1f  call    ?GetTarget@CompositionAnimation@Composition@UI@Windows@@QEAAXPEAPEAUHSTRING__@@@Z; Windows::UI::Composition::CompositionAnimation::GetTarget(HSTRING__ * *)
0x180072c24  mov     rax, [rsi]
0x180072c27  xor     r9d, r9d
0x180072c2a  mov     rdx, [rbp+string]
0x180072c2e  mov     r8, rbx
0x180072c31  mov     rcx, rsi
0x180072c34  mov     qword ptr [rsp+38h+var_18], 0; int
0x180072c3d  mov     rax, [rax+98h]
0x180072c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c49  mov     edi, eax
0x180072c4b  test    eax, eax
0x180072c4d  js      short loc_180072CC1
0x180072c4f  mov     rcx, [rbp+string]; string
0x180072c53  call    cs:__imp_WindowsDeleteString
0x180072c59  jmp     short loc_180072BE3
0x180072c5b  test    rdi, rdi
0x180072c5e  jz      short loc_180072BE3
0x180072c60  lea     rax, [rbp+string]
0x180072c64  mov     [rsp+38h+var_10], 0
0x180072c6d  xor     r9d, r9d
0x180072c70  mov     qword ptr [rsp+38h+var_18], rax; int
0x180072c75  xor     r8d, r8d
0x180072c78  mov     rdx, rsi
0x180072c7b  mov     rcx, rdi
0x180072c7e  call    ?PlayAnimations@CompositionAnimationGroup@Composition@UI@Windows@@QEAAJPEAVCompositionObject@234@PEBUAnimationValueData@234@W4AnimationValueSynchronizationBehavior@234@PEA_NPEAV?$vector@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@V?$allocator@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@@std@@@std@@@Z; Windows::UI::Composition::CompositionAnimationGroup::PlayAnimations(Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::AnimationValueData const *,Windows::UI::Composition::AnimationValueSynchronizationBehavior,bool *,std::vector<Windows::UI::Composition::CompositionPropertyAnimator *> *)
0x180072c83  mov     esi, eax
0x180072c85  test    eax, eax
0x180072c87  jns     loc_180072BD6
0x180072c8d  mov     rcx, [rbp+20h]; this
0x180072c91  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180072c98  mov     r9d, eax; char *
0x180072c9b  mov     edx, 2A8h; void *
0x180072ca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072ca5  mov     rcx, rdi; this
0x180072ca8  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180072cad  test    rbx, rbx
0x180072cb0  jz      short loc_180072CBA
0x180072cb2  mov     rcx, rbx; this
0x180072cb5  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180072cba  mov     eax, esi
0x180072cbc  jmp     loc_180072BF2
0x180072cc1  mov     rcx, [rbp+20h]; this
0x180072cc5  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180072ccc  mov     r9d, edi; char *
0x180072ccf  mov     edx, 297h; void *
0x180072cd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072cd9  mov     rcx, [rbp+string]; string
0x180072cdd  call    cs:__imp_WindowsDeleteString
0x180072ce3  mov     rcx, rbx; this
0x180072ce6  mov     [rbp+string], 0
0x180072cee  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180072cf3  mov     eax, edi
0x180072cf5  jmp     loc_180072BF2
```
