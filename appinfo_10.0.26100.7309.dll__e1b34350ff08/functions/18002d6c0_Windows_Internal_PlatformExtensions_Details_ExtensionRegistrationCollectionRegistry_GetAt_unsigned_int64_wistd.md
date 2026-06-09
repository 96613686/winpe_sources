# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(unsigned __int64,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>> &)

- ea: `0x18002d6c0`
- end: `0x18002d821`
- name: `?GetAt@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJ_KAEAV?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180007c78`
- `0x180018530`
- `0x18001bc74`
- `0x180028fa0`
- `0x18002d6c0`
- `0x180033d08`
- `0x180039e54`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002d713`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002d713`

## string_xrefs

- `0x18002d72b`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18002d7a6`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18002d7e2`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(
        __int64 a1,
        DWORD a2,
        __int64 a3)
{
  unsigned int v5; // eax
  _QWORD *v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  unsigned int lpReserved; // [rsp+20h] [rbp-158h]
  DWORD cchName[4]; // [rsp+40h] [rbp-138h] BYREF
  WCHAR Name[128]; // [rsp+50h] [rbp-128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  cchName[0] = 128;
  v5 = RegEnumKeyExW(*(HKEY *)(a1 + 8), a2, Name, cchName, 0, 0, 0, 0);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x141,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
             (const char *)v5,
             lpReserved);
  v7 = operator new(0x118u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
  {
    *v7 = &Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable';
    v7[1] = 0;
    *((_BYTE *)v7 + 16) = 0;
    *((_DWORD *)v7 + 5) = 0;
    *((_WORD *)v7 + 12) = 0;
    memset_0((char *)v7 + 26, 0, 0xFEu);
    v8 = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(
           (Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *)v7,
           *(HKEY *)(a1 + 8),
           Name);
    v9 = v8;
    if ( v8 >= 0 )
    {
      wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
        a3,
        v7);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
        (const char *)(unsigned int)v8,
        lpReserved);
      Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(
        (Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *)v7,
        1u);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
      (const char *)0x8007000ELL,
      lpReserved);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18002d6c0  mov     [rsp+arg_18], rbx
0x18002d6c5  push    rbp
0x18002d6c6  push    rsi
0x18002d6c7  push    rdi
0x18002d6c8  sub     rsp, 160h
0x18002d6cf  mov     rax, cs:__security_cookie
0x18002d6d6  xor     rax, rsp
0x18002d6d9  mov     [rsp+178h+var_28], rax
0x18002d6e1  xor     ebp, ebp
0x18002d6e3  mov     [rsp+178h+cchName], 80h
0x18002d6eb  mov     [rsp+178h+lpftLastWriteTime], rbp; lpftLastWriteTime
0x18002d6f0  lea     r9, [rsp+178h+cchName]; lpcchName
0x18002d6f5  mov     [rsp+178h+lpcchClass], rbp; lpcchClass
0x18002d6fa  mov     rsi, r8
0x18002d6fd  mov     rdi, rcx
0x18002d700  mov     [rsp+178h+lpClass], rbp; lpClass
0x18002d705  mov     rcx, [rcx+8]; hKey
0x18002d709  lea     r8, [rsp+178h+Name]; lpName
0x18002d70e  mov     [rsp+178h+lpReserved], rbp; int
0x18002d713  call    cs:__imp_RegEnumKeyExW
0x18002d71a  nop     dword ptr [rax+rax+00h]
0x18002d71f  test    eax, eax
0x18002d721  jz      short loc_18002D744
0x18002d723  mov     rcx, [rsp+178h]; this
0x18002d72b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18002d732  mov     r9d, eax; char *
0x18002d735  mov     edx, 141h; void *
0x18002d73a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d73f  jmp     loc_18002D7FD
0x18002d744  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d74b  mov     ecx, 118h; unsigned __int64
0x18002d750  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d755  mov     rbx, rax
0x18002d758  test    rax, rax
0x18002d75b  jz      short loc_18002D7DA
0x18002d75d  lea     rax, ??_7ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable'
0x18002d764  xor     edx, edx; Val
0x18002d766  mov     [rbx], rax
0x18002d769  lea     rcx, [rbx+1Ah]; void *
0x18002d76d  mov     [rbx+8], rbp
0x18002d771  mov     r8d, 0FEh; Size
0x18002d777  mov     [rbx+10h], bpl
0x18002d77b  mov     [rbx+14h], ebp
0x18002d77e  mov     [rbx+18h], bp
0x18002d782  call    memset_0
0x18002d787  mov     rdx, [rdi+8]; HKEY
0x18002d78b  lea     r8, [rsp+178h+Name]; unsigned __int16 *
0x18002d790  mov     rcx, rbx; this
0x18002d793  call    ?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)
0x18002d798  mov     edi, eax
0x18002d79a  test    eax, eax
0x18002d79c  jns     short loc_18002D7CB
0x18002d79e  mov     rcx, [rsp+178h]; this
0x18002d7a6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18002d7ad  mov     r9d, eax; char *
0x18002d7b0  mov     edx, 144h; void *
0x18002d7b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d7ba  mov     edx, 1; unsigned int
0x18002d7bf  mov     rcx, rbx; this
0x18002d7c2  call    ??_GExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(uint)
0x18002d7c7  mov     eax, edi
0x18002d7c9  jmp     short loc_18002D7FD
0x18002d7cb  mov     rdx, rbx
0x18002d7ce  mov     rcx, rsi
0x18002d7d1  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x18002d7d6  xor     eax, eax
0x18002d7d8  jmp     short loc_18002D7FD
0x18002d7da  mov     rcx, [rsp+178h]; this
0x18002d7e2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18002d7e9  mov     ebx, 8007000Eh
0x18002d7ee  mov     edx, 143h; void *
0x18002d7f3  mov     r9d, ebx; char *
0x18002d7f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d7fb  mov     eax, ebx
0x18002d7fd  mov     rcx, [rsp+178h+var_28]
0x18002d805  xor     rcx, rsp; StackCookie
0x18002d808  call    __security_check_cookie
0x18002d80d  mov     rbx, [rsp+178h+arg_18]
0x18002d815  add     rsp, 160h
0x18002d81c  pop     rdi
0x18002d81d  pop     rsi
0x18002d81e  pop     rbp
0x18002d81f  retn
```
