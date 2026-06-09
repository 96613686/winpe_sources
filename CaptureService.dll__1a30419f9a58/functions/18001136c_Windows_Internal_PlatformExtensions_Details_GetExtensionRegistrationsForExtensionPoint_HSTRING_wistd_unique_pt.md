# Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(HSTRING__ *,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection>> *)

- ea: `0x18001136c`
- end: `0x180011430`
- name: `?GetExtensionRegistrationsForExtensionPoint@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAV?$unique_ptr@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(HSTRING)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800103c8`

## callees

- `0x18000335c`
- `0x18000907c`
- `0x18000e8f0`
- `0x18001136c`
- `0x180012054`
- `0x1800188fc`

## string_xrefs

- `0x1800113cc`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180011405`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(
        HSTRING a1,
        __int64 a2)
{
  Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
    a2,
    0);
  v4 = (Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *)operator new(
                                                                                                    0x10u,
                                                                                                    (const struct std::nothrow_t *)std::nothrow);
  if ( v4 )
  {
    *(_QWORD *)v4 = &Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`vftable';
    *((_QWORD *)v4 + 1) = 0;
    v5 = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(v4, a1);
    v6 = v5;
    if ( v5 >= 0 )
    {
      wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
        a2,
        v4);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)v5,
        v8);
      Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(
        v4,
        1);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)0x8007000ELL,
      v8);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001136c  mov     [rsp+arg_0], rbx
0x180011371  mov     [rsp+arg_8], rsi
0x180011376  push    rdi; int
0x180011377  sub     rsp, 20h
0x18001137b  mov     rsi, rdx
0x18001137e  mov     rdi, rcx
0x180011381  mov     rcx, rsi
0x180011384  xor     edx, edx
0x180011386  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x18001138b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011392  mov     ecx, 10h; unsigned __int64
0x180011397  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001139c  mov     rbx, rax
0x18001139f  test    rax, rax
0x1800113a2  jz      short loc_180011400
0x1800113a4  lea     rax, ??_7ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`vftable'
0x1800113ab  mov     rdx, rdi; HSTRING
0x1800113ae  mov     [rbx], rax
0x1800113b1  mov     rcx, rbx; this
0x1800113b4  mov     qword ptr [rbx+8], 0
0x1800113bc  call    ?Initialize@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(HSTRING__ *)
0x1800113c1  mov     edi, eax
0x1800113c3  test    eax, eax
0x1800113c5  jns     short loc_1800113F1
0x1800113c7  mov     rcx, [rsp+28h]; this
0x1800113cc  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800113d3  mov     r9d, eax; char *
0x1800113d6  mov     edx, 156h; void *
0x1800113db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800113e0  mov     edx, 1; unsigned int
0x1800113e5  mov     rcx, rbx; this
0x1800113e8  call    ??_GExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(uint)
0x1800113ed  mov     eax, edi
0x1800113ef  jmp     short loc_180011420
0x1800113f1  mov     rdx, rbx
0x1800113f4  mov     rcx, rsi
0x1800113f7  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x1800113fc  xor     eax, eax
0x1800113fe  jmp     short loc_180011420
0x180011400  mov     rcx, [rsp+28h]; this
0x180011405  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18001140c  mov     ebx, 8007000Eh
0x180011411  mov     edx, 155h; void *
0x180011416  mov     r9d, ebx; char *
0x180011419  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001141e  mov     eax, ebx
0x180011420  mov     rbx, [rsp+28h+arg_0]
0x180011425  mov     rsi, [rsp+28h+arg_8]
0x18001142a  add     rsp, 20h
0x18001142e  pop     rdi
0x18001142f  retn
```
