# Windows::UI::Composition::ProxyObject::StopAnimationGroup(Windows::UI::Composition::ICompositionAnimationBase *)

- ea: `0x1800c9590`
- end: `0x1800c9699`
- name: `?StopAnimationGroup@ProxyObject@Composition@UI@Windows@@UEAAJPEAUICompositionAnimationBase@234@@Z`
- size: `265`
- prototype: `int(Windows::UI::Composition::ProxyObject *__hidden this, struct Windows::UI::Composition::ICompositionAnimationBase *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000bc00`
- `0x18000f810`
- `0x18001358c`
- `0x180048980`
- `0x180074480`
- `0x1800c9590`
- `0x1800c96a0`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180180f30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180180f82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180180f99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180180f30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180180f82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180180f99`

## string_xrefs

- `0x1800c963b`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtproxyobject.cpp`
- `0x180180f6a`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtproxyobject.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ProxyObject::StopAnimationGroup(
        Windows::UI::Composition::ProxyObject *this,
        struct IUnknown *a2)
{
  struct Microsoft::WRL2::ContextSession *v4; // rcx
  int v5; // eax
  Windows::UI::Composition::CompositionAnimation *v6; // rbx
  struct Microsoft::WRL2::ContextSession *v7; // rcx
  int v8; // eax
  Microsoft::WRL2::NestableRuntimeClass *v9; // rsi
  int v10; // eax
  unsigned int v11; // edi
  unsigned int v13; // ebx
  int v14; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF
  HSTRING v18; // [rsp+50h] [rbp+30h] BYREF

  v18 = 0;
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v18);
  v4 = (struct Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
  string = 0;
  v5 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
         v4,
         a2,
         (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionAnimation::s_InterfaceType,
         (struct Microsoft::WRL2::ContextRuntimeClass **)&string);
  v6 = (Windows::UI::Composition::CompositionAnimation *)string;
  v18 = string;
  if ( v5 >= 0 && string )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    Windows::UI::Composition::CompositionAnimation::GetTarget(v6, &string);
    v14 = (*(__int64 (__fastcall **)(Windows::UI::Composition::ProxyObject *, HSTRING))(*(_QWORD *)this + 176LL))(
            this,
            string);
    v13 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C5,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtproxyobject.cpp",
        (const char *)(unsigned int)v14,
        savedregs);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_10;
    }
    WindowsDeleteString(string);
LABEL_9:
    v13 = 0;
LABEL_10:
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v18);
    return v13;
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
  if ( v8 < 0
    || !string
    || (v10 = Windows::UI::Composition::CompositionAnimationGroup::StopAnimations(
                (Windows::UI::Composition::CompositionAnimationGroup *)string,
                this),
        v11 = v10,
        v10 >= 0) )
  {
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&string);
    goto LABEL_9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2D5,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtproxyobject.cpp",
    (const char *)(unsigned int)v10,
    savedregs);
  Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v9);
  if ( v6 )
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v6);
  return v11;
}

```

## disassembly

```asm
0x1800c9590  mov     [rsp-18h+arg_8], rbx
0x1800c9595  push    rbp
0x1800c9596  push    rsi
0x1800c9597  push    rdi; int
0x1800c9598  mov     rbp, rsp
0x1800c959b  sub     rsp, 20h
0x1800c959f  mov     rdi, rcx
0x1800c95a2  mov     [rbp+arg_10], 0
0x1800c95aa  lea     rcx, [rbp+arg_10]; void *
0x1800c95ae  mov     rsi, rdx
0x1800c95b1  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800c95b6  mov     rcx, [rdi+18h]; struct Microsoft::WRL2::ContextSession *
0x1800c95ba  lea     r9, [rbp+string]; struct Microsoft::WRL2::ContextRuntimeClass **
0x1800c95be  lea     r8, ?s_InterfaceType@CompositionAnimation@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x1800c95c5  mov     [rbp+string], 0
0x1800c95cd  mov     rdx, rsi; struct IUnknown *
0x1800c95d0  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x1800c95d5  mov     rbx, [rbp+string]
0x1800c95d9  mov     [rbp+arg_10], rbx
0x1800c95dd  test    eax, eax
0x1800c95df  jns     loc_1800C968B
0x1800c95e5  lea     rcx, [rbp+string]; void *
0x1800c95e9  mov     [rbp+string], 0
0x1800c95f1  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800c95f6  mov     rcx, [rdi+18h]; struct Microsoft::WRL2::ContextSession *
0x1800c95fa  lea     r9, [rbp+string]; struct Microsoft::WRL2::ContextRuntimeClass **
0x1800c95fe  lea     r8, ?s_InterfaceType@CompositionAnimationGroup@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x1800c9605  mov     [rbp+string], 0
0x1800c960d  mov     rdx, rsi; struct IUnknown *
0x1800c9610  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x1800c9615  mov     rsi, [rbp+string]
0x1800c9619  mov     [rbp+string], rsi
0x1800c961d  test    eax, eax
0x1800c961f  js      short loc_1800C9673
0x1800c9621  test    rsi, rsi
0x1800c9624  jz      short loc_1800C9673
0x1800c9626  mov     rdx, rdi; struct Windows::UI::Composition::CompositionObject *
0x1800c9629  mov     rcx, rsi; this
0x1800c962c  call    ?StopAnimations@CompositionAnimationGroup@Composition@UI@Windows@@QEAAJPEAVCompositionObject@234@@Z; Windows::UI::Composition::CompositionAnimationGroup::StopAnimations(Windows::UI::Composition::CompositionObject *)
0x1800c9631  mov     edi, eax
0x1800c9633  test    eax, eax
0x1800c9635  jns     short loc_1800C9673
0x1800c9637  mov     rcx, [rbp+18h]; this
0x1800c963b  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800c9642  mov     r9d, eax; char *
0x1800c9645  mov     edx, 2D5h; void *
0x1800c964a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c964f  mov     rcx, rsi; this
0x1800c9652  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800c9657  test    rbx, rbx
0x1800c965a  jz      short loc_1800C9664
0x1800c965c  mov     rcx, rbx; this
0x1800c965f  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800c9664  mov     eax, edi
0x1800c9666  mov     rbx, [rsp+20h+arg_8]
0x1800c966b  add     rsp, 20h
0x1800c966f  pop     rdi
0x1800c9670  pop     rsi
0x1800c9671  pop     rbp
0x1800c9672  retn
0x1800c9673  lea     rcx, [rbp+string]; void *
0x1800c9677  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800c967c  xor     ebx, ebx
0x1800c967e  lea     rcx, [rbp+arg_10]; void *
0x1800c9682  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800c9687  mov     eax, ebx
0x1800c9689  jmp     short loc_1800C9666
0x1800c968b  test    rbx, rbx
0x1800c968e  jz      loc_1800C95E5
0x1800c9694  jmp     loc_180180F26
0x180180f26  xor     ecx, ecx; string
0x180180f28  mov     [rbp+string], 0
0x180180f30  call    cs:__imp_WindowsDeleteString
0x180180f36  lea     rdx, [rbp+string]; HSTRING *
0x180180f3a  mov     [rbp+string], 0
0x180180f42  mov     rcx, rbx; this
0x180180f45  call    ?GetTarget@CompositionAnimation@Composition@UI@Windows@@QEAAXPEAPEAUHSTRING__@@@Z; Windows::UI::Composition::CompositionAnimation::GetTarget(HSTRING__ * *)
0x180180f4a  mov     rax, [rdi]
0x180180f4d  mov     rcx, rdi
0x180180f50  mov     rdx, [rbp+string]
0x180180f54  mov     rax, [rax+0B0h]
0x180180f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180f60  mov     ebx, eax
0x180180f62  test    eax, eax
0x180180f64  jns     short loc_180180F95
0x180180f66  mov     rcx, [rbp+18h]; this
0x180180f6a  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180180f71  mov     r9d, eax; char *
0x180180f74  mov     edx, 2C5h; void *
0x180180f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180180f7e  mov     rcx, [rbp+string]; string
0x180180f82  call    cs:__imp_WindowsDeleteString
0x180180f88  mov     [rbp+string], 0
0x180180f90  jmp     loc_1800C967E
0x180180f95  mov     rcx, [rbp+string]; string
0x180180f99  call    cs:__imp_WindowsDeleteString
0x180180f9f  nop
0x180180fa0  jmp     loc_1800C967C
```
