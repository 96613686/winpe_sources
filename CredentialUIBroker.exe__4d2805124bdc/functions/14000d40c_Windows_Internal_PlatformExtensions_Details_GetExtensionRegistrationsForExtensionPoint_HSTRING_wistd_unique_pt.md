# Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(HSTRING__ *,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection>> *)

- ea: `0x14000d40c`
- end: `0x14000d4d0`
- name: `?GetExtensionRegistrationsForExtensionPoint@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAV?$unique_ptr@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(HSTRING, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c458`

## callees

- `0x140003644`
- `0x14000a4a0`
- `0x14000d40c`
- `0x14000e680`
- `0x1400136fc`
- `0x14001af00`

## string_xrefs

- `0x14000d46c`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x14000d4a5`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

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
                                                                                                    (const struct std::nothrow_t *)&std::nothrow);
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
0x14000d40c  mov     [rsp+arg_0], rbx
0x14000d411  mov     [rsp+arg_8], rsi
0x14000d416  push    rdi; int
0x14000d417  sub     rsp, 20h
0x14000d41b  mov     rsi, rdx
0x14000d41e  mov     rdi, rcx
0x14000d421  mov     rcx, rsi
0x14000d424  xor     edx, edx
0x14000d426  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x14000d42b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d432  mov     ecx, 10h; unsigned __int64
0x14000d437  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000d43c  mov     rbx, rax
0x14000d43f  test    rax, rax
0x14000d442  jz      short loc_14000D4A0
0x14000d444  lea     rax, ??_7ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`vftable'
0x14000d44b  mov     rdx, rdi; HSTRING
0x14000d44e  mov     [rbx], rax
0x14000d451  mov     rcx, rbx; this
0x14000d454  mov     qword ptr [rbx+8], 0
0x14000d45c  call    ?Initialize@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(HSTRING__ *)
0x14000d461  mov     edi, eax
0x14000d463  test    eax, eax
0x14000d465  jns     short loc_14000D491
0x14000d467  mov     rcx, [rsp+28h]; this
0x14000d46c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000d473  mov     r9d, eax; char *
0x14000d476  mov     edx, 156h; void *
0x14000d47b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d480  mov     edx, 1; unsigned int
0x14000d485  mov     rcx, rbx; this
0x14000d488  call    ??_GExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(uint)
0x14000d48d  mov     eax, edi
0x14000d48f  jmp     short loc_14000D4C0
0x14000d491  mov     rdx, rbx
0x14000d494  mov     rcx, rsi
0x14000d497  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x14000d49c  xor     eax, eax
0x14000d49e  jmp     short loc_14000D4C0
0x14000d4a0  mov     rcx, [rsp+28h]; this
0x14000d4a5  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000d4ac  mov     ebx, 8007000Eh
0x14000d4b1  mov     edx, 155h; void *
0x14000d4b6  mov     r9d, ebx; char *
0x14000d4b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d4be  mov     eax, ebx
0x14000d4c0  mov     rbx, [rsp+28h+arg_0]
0x14000d4c5  mov     rsi, [rsp+28h+arg_8]
0x14000d4ca  add     rsp, 20h
0x14000d4ce  pop     rdi
0x14000d4cf  retn
```
