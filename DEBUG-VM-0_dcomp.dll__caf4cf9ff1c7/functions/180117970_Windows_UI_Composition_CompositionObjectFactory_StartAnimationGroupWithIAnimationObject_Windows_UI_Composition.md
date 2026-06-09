# Windows::UI::Composition::CompositionObjectFactory::StartAnimationGroupWithIAnimationObject(Windows::UI::Composition::IAnimationObject *,Windows::UI::Composition::ICompositionAnimationBase *)

- ea: `0x180117970`
- end: `0x180117b69`
- name: `?StartAnimationGroupWithIAnimationObject@CompositionObjectFactory@Composition@UI@Windows@@UEAAJPEAUIAnimationObject@234@PEAUICompositionAnimationBase@234@@Z`
- size: `505`
- prototype: `int(Windows::UI::Composition::CompositionObjectFactory *__hidden this, struct Windows::UI::Composition::IAnimationObject *, struct Windows::UI::Composition::ICompositionAnimationBase *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000bc00`
- `0x18000f810`
- `0x180012da0`
- `0x180013528`
- `0x180036f90`
- `0x180047750`
- `0x180048980`
- `0x180074480`
- `0x18007610c`
- `0x1800ebe2c`
- `0x180117970`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117aa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117abe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117aa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117abe`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1801179a6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180117a05`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1801179a6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180117a05`

## string_xrefs

- `0x1801179fa`: `The given object has already been closed / disposed and may no longer be used.`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionObjectFactory::StartAnimationGroupWithIAnimationObject(
        Windows::UI::Composition::CompositionObjectFactory *this,
        struct IUnknown *a2,
        struct IUnknown *a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // edi
  HSTRING v8; // rsi
  Microsoft::WRL2::ContextSession *v9; // rdi
  int v10; // eax
  Windows::UI::Composition::CompositionAnimation *v11; // r15
  int started; // eax
  int v13; // eax
  unsigned int v14; // edx
  HSTRING string; // [rsp+60h] [rbp+40h] BYREF
  HSTRING v16; // [rsp+68h] [rbp+48h] BYREF

  string = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    RoOriginateErrorW(2147942487LL, 0, L"The caller must specify a non-null, non-closed / disposed object.");
    return v5;
  }
  v6 = Microsoft::WRL2::NestableRuntimeClass::ValidateInterface(
         a3,
         (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Microsoft::WRL2::ContextRuntimeClass::s_InterfaceType,
         (struct Microsoft::WRL2::NestableRuntimeClass **)&string);
  if ( !v6 )
  {
    v8 = string;
    v9 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)string + 3);
    Microsoft::WRL2::ContextSession::BeginApiEntry(v9);
    if ( ((_BYTE)v8[12] & 2) == 0 )
    {
      v5 = -2147483629;
      RoOriginateErrorW(
        2147483667LL,
        0,
        L"The given object has already been closed / disposed and may no longer be used.");
LABEL_23:
      Microsoft::WRL2::ContextSession::EndApiEntry(v9);
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease((Microsoft::WRL2::NestableRuntimeClass *)v8);
      return v5;
    }
    if ( !a2 )
    {
      v5 = -2147024809;
      DoStackCaptureDirect(-2147024809, 0x5A0u);
      goto LABEL_23;
    }
    v16 = 0;
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v16);
    string = 0;
    v10 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
            v9,
            a3,
            (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionAnimation::s_InterfaceType,
            (struct Microsoft::WRL2::ContextRuntimeClass **)&string);
    v11 = (Windows::UI::Composition::CompositionAnimation *)string;
    v16 = string;
    string = 0;
    if ( v10 >= 0 )
    {
      WindowsDeleteString(0);
      string = 0;
      Windows::UI::Composition::CompositionAnimation::GetTarget(v11, &string);
      started = Windows::UI::Composition::CompositionObjectFactory::StartAnimationWithIAnimationObject(
                  a2,
                  (Windows::UI::Composition::AnimationHelper *)string,
                  v11,
                  0);
      v5 = started;
      if ( started < 0 )
      {
        DoStackCaptureDirect(started, 0x5A9u);
        WindowsDeleteString(string);
        string = 0;
LABEL_22:
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v16);
        goto LABEL_23;
      }
      WindowsDeleteString(string);
LABEL_18:
      v5 = 0;
      goto LABEL_22;
    }
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&string);
    string = 0;
    v13 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
            v9,
            a3,
            (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionAnimationGroup::s_InterfaceType,
            (struct Microsoft::WRL2::ContextRuntimeClass **)&string);
    v5 = v13;
    if ( v13 < 0 )
    {
      v14 = 1457;
    }
    else
    {
      v13 = Windows::UI::Composition::CompositionAnimationGroup::StartAnimationGroupWithIAnimationObject(
              (__int64)string,
              a2,
              0);
      v5 = v13;
      if ( v13 >= 0 )
      {
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&string);
        goto LABEL_18;
      }
      v14 = 1459;
    }
    DoStackCaptureDirect(v13, v14);
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&string);
    goto LABEL_22;
  }
  if ( string )
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease((Microsoft::WRL2::NestableRuntimeClass *)string);
  return v6;
}

```

## disassembly

```asm
0x180117970  mov     [rsp-28h+arg_0], rbx
0x180117975  push    rbp
0x180117976  push    rsi
0x180117977  push    rdi
0x180117978  push    r14
0x18011797a  push    r15
0x18011797c  mov     rbp, rsp
0x18011797f  sub     rsp, 20h
0x180117983  mov     [rbp+string], 0
0x18011798b  mov     rbx, r8
0x18011798e  mov     r14, rdx
0x180117991  test    r8, r8
0x180117994  jnz     short loc_1801179B1
0x180117996  mov     ebx, 80070057h
0x18011799b  lea     r8, aTheCallerMustS; "The caller must specify a non-null, non"...
0x1801179a2  mov     ecx, ebx
0x1801179a4  xor     edx, edx
0x1801179a6  call    cs:__imp_RoOriginateErrorW
0x1801179ac  jmp     loc_180117B56
0x1801179b1  lea     r8, [rbp+string]; struct Microsoft::WRL2::NestableRuntimeClass **
0x1801179b5  mov     rcx, rbx; struct IUnknown *
0x1801179b8  lea     rdx, ?s_InterfaceType@ContextRuntimeClass@WRL2@Microsoft@@2UInterfaceType@NestableRuntimeClass@23@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x1801179bf  call    ?ValidateInterface@NestableRuntimeClass@WRL2@Microsoft@@SAJPEAUIUnknown@@PEBUInterfaceType@123@PEAPEAV123@@Z; Microsoft::WRL2::NestableRuntimeClass::ValidateInterface(IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::NestableRuntimeClass * *)
0x1801179c4  mov     edi, eax
0x1801179c6  test    eax, eax
0x1801179c8  jz      short loc_1801179DF
0x1801179ca  mov     rcx, [rbp+string]; this
0x1801179ce  test    rcx, rcx
0x1801179d1  jz      short loc_1801179D8
0x1801179d3  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1801179d8  mov     eax, edi
0x1801179da  jmp     loc_180117B58
0x1801179df  mov     rsi, [rbp+string]
0x1801179e3  mov     rdi, [rsi+18h]
0x1801179e7  mov     rcx, rdi; this
0x1801179ea  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x1801179ef  test    byte ptr [rsi+30h], 2
0x1801179f3  jnz     short loc_180117A10
0x1801179f5  mov     ebx, 80000013h
0x1801179fa  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180117a01  mov     ecx, ebx
0x180117a03  xor     edx, edx
0x180117a05  call    cs:__imp_RoOriginateErrorW
0x180117a0b  jmp     loc_180117B46
0x180117a10  test    r14, r14
0x180117a13  jnz     short loc_180117A2B
0x180117a15  mov     ebx, 80070057h
0x180117a1a  mov     edx, 5A0h; unsigned int
0x180117a1f  mov     ecx, ebx; int
0x180117a21  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180117a26  jmp     loc_180117B46
0x180117a2b  lea     rcx, [rbp+arg_18]; void *
0x180117a2f  mov     [rbp+arg_18], 0
0x180117a37  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180117a3c  lea     r9, [rbp+string]; struct Microsoft::WRL2::ContextRuntimeClass **
0x180117a40  mov     [rbp+string], 0
0x180117a48  lea     r8, ?s_InterfaceType@CompositionAnimation@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x180117a4f  mov     rdx, rbx; struct IUnknown *
0x180117a52  mov     rcx, rdi; struct Microsoft::WRL2::ContextSession *
0x180117a55  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x180117a5a  mov     r15, [rbp+string]
0x180117a5e  mov     [rbp+arg_18], r15
0x180117a62  mov     [rbp+string], 0
0x180117a6a  test    eax, eax
0x180117a6c  js      short loc_180117ACE
0x180117a6e  xor     ecx, ecx; string
0x180117a70  call    cs:__imp_WindowsDeleteString
0x180117a76  lea     rdx, [rbp+string]; HSTRING *
0x180117a7a  mov     [rbp+string], 0
0x180117a82  mov     rcx, r15; this
0x180117a85  call    ?GetTarget@CompositionAnimation@Composition@UI@Windows@@QEAAXPEAPEAUHSTRING__@@@Z; Windows::UI::Composition::CompositionAnimation::GetTarget(HSTRING__ * *)
0x180117a8a  mov     rdx, [rbp+string]; this
0x180117a8e  xor     r9d, r9d; struct Windows::UI::Composition::CompositionPropertyAnimator **
0x180117a91  mov     r8, r15; struct Windows::UI::Composition::CompositionAnimation *
0x180117a94  mov     rcx, r14; struct IUnknown *
0x180117a97  call    ?StartAnimationWithIAnimationObject@CompositionObjectFactory@Composition@UI@Windows@@SAJPEAUIAnimationObject@234@PEAUHSTRING__@@PEAVCompositionAnimation@234@PEAPEAVCompositionPropertyAnimator@234@@Z; Windows::UI::Composition::CompositionObjectFactory::StartAnimationWithIAnimationObject(Windows::UI::Composition::IAnimationObject *,HSTRING__ *,Windows::UI::Composition::CompositionAnimation *,Windows::UI::Composition::CompositionPropertyAnimator * *)
0x180117a9c  mov     ebx, eax
0x180117a9e  test    eax, eax
0x180117aa0  js      short loc_180117AAE
0x180117aa2  mov     rcx, [rbp+string]; string
0x180117aa6  call    cs:__imp_WindowsDeleteString
0x180117aac  jmp     short loc_180117B1D
0x180117aae  mov     edx, 5A9h; unsigned int
0x180117ab3  mov     ecx, eax; int
0x180117ab5  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180117aba  mov     rcx, [rbp+string]; string
0x180117abe  call    cs:__imp_WindowsDeleteString
0x180117ac4  mov     [rbp+string], 0
0x180117acc  jmp     short loc_180117B3D
0x180117ace  lea     rcx, [rbp+string]; void *
0x180117ad2  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180117ad7  lea     r9, [rbp+string]; struct Microsoft::WRL2::ContextRuntimeClass **
0x180117adb  mov     [rbp+string], 0
0x180117ae3  lea     r8, ?s_InterfaceType@CompositionAnimationGroup@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x180117aea  mov     rdx, rbx; struct IUnknown *
0x180117aed  mov     rcx, rdi; struct Microsoft::WRL2::ContextSession *
0x180117af0  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x180117af5  mov     rcx, [rbp+string]
0x180117af9  mov     ebx, eax
0x180117afb  mov     [rbp+string], rcx
0x180117aff  test    eax, eax
0x180117b01  js      short loc_180117B28
0x180117b03  xor     r8d, r8d
0x180117b06  mov     rdx, r14
0x180117b09  call    ?StartAnimationGroupWithIAnimationObject@CompositionAnimationGroup@Composition@UI@Windows@@QEAAJPEAUIAnimationObject@234@PEAV?$vector@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@V?$allocator@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@@std@@@std@@@Z; Windows::UI::Composition::CompositionAnimationGroup::StartAnimationGroupWithIAnimationObject(Windows::UI::Composition::IAnimationObject *,std::vector<Windows::UI::Composition::CompositionPropertyAnimator *> *)
0x180117b0e  mov     ebx, eax
0x180117b10  test    eax, eax
0x180117b12  js      short loc_180117B21
0x180117b14  lea     rcx, [rbp+string]; void *
0x180117b18  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180117b1d  xor     ebx, ebx
0x180117b1f  jmp     short loc_180117B3D
0x180117b21  mov     edx, 5B3h
0x180117b26  jmp     short loc_180117B2D
0x180117b28  mov     edx, 5B1h; unsigned int
0x180117b2d  mov     ecx, eax; int
0x180117b2f  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180117b34  lea     rcx, [rbp+string]; void *
0x180117b38  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180117b3d  lea     rcx, [rbp+arg_18]; void *
0x180117b41  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180117b46  mov     rcx, rdi; this
0x180117b49  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180117b4e  mov     rcx, rsi; this
0x180117b51  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180117b56  mov     eax, ebx
0x180117b58  mov     rbx, [rsp+20h+arg_0]
0x180117b5d  add     rsp, 20h
0x180117b61  pop     r15
0x180117b63  pop     r14
0x180117b65  pop     rdi
0x180117b66  pop     rsi
0x180117b67  pop     rbp
0x180117b68  retn
```
