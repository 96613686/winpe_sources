# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(unsigned __int64,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>> &)

- ea: `0x18002ece0`
- end: `0x18002ee41`
- name: `?GetAt@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJ_KAEAV?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180007c78`
- `0x180018280`
- `0x18001b8a4`
- `0x18002a5e0`
- `0x18002ece0`
- `0x180033c58`
- `0x1800396a0`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002ed33`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002ed33`

## string_xrefs

- `0x18002ed4b`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18002edc6`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18002ee02`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

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
0x18002ece0  mov     [rsp+arg_18], rbx
0x18002ece5  push    rbp
0x18002ece6  push    rsi
0x18002ece7  push    rdi
0x18002ece8  sub     rsp, 160h
0x18002ecef  mov     rax, cs:__security_cookie
0x18002ecf6  xor     rax, rsp
0x18002ecf9  mov     [rsp+178h+var_28], rax
0x18002ed01  xor     ebp, ebp
0x18002ed03  mov     [rsp+178h+cchName], 80h
0x18002ed0b  mov     [rsp+178h+lpftLastWriteTime], rbp; lpftLastWriteTime
0x18002ed10  lea     r9, [rsp+178h+cchName]; lpcchName
0x18002ed15  mov     [rsp+178h+lpcchClass], rbp; lpcchClass
0x18002ed1a  mov     rsi, r8
0x18002ed1d  mov     rdi, rcx
0x18002ed20  mov     [rsp+178h+lpClass], rbp; lpClass
0x18002ed25  mov     rcx, [rcx+8]; hKey
0x18002ed29  lea     r8, [rsp+178h+Name]; lpName
0x18002ed2e  mov     [rsp+178h+lpReserved], rbp; int
0x18002ed33  call    cs:__imp_RegEnumKeyExW
0x18002ed3a  nop     dword ptr [rax+rax+00h]
0x18002ed3f  test    eax, eax
0x18002ed41  jz      short loc_18002ED64
0x18002ed43  mov     rcx, [rsp+178h]; this
0x18002ed4b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18002ed52  mov     r9d, eax; char *
0x18002ed55  mov     edx, 141h; void *
0x18002ed5a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002ed5f  jmp     loc_18002EE1D
0x18002ed64  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ed6b  mov     ecx, 118h; unsigned __int64
0x18002ed70  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ed75  mov     rbx, rax
0x18002ed78  test    rax, rax
0x18002ed7b  jz      short loc_18002EDFA
0x18002ed7d  lea     rax, ??_7ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable'
0x18002ed84  xor     edx, edx; Val
0x18002ed86  mov     [rbx], rax
0x18002ed89  lea     rcx, [rbx+1Ah]; void *
0x18002ed8d  mov     [rbx+8], rbp
0x18002ed91  mov     r8d, 0FEh; Size
0x18002ed97  mov     [rbx+10h], bpl
0x18002ed9b  mov     [rbx+14h], ebp
0x18002ed9e  mov     [rbx+18h], bp
0x18002eda2  call    memset_0
0x18002eda7  mov     rdx, [rdi+8]; HKEY
0x18002edab  lea     r8, [rsp+178h+Name]; unsigned __int16 *
0x18002edb0  mov     rcx, rbx; this
0x18002edb3  call    ?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)
0x18002edb8  mov     edi, eax
0x18002edba  test    eax, eax
0x18002edbc  jns     short loc_18002EDEB
0x18002edbe  mov     rcx, [rsp+178h]; this
0x18002edc6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18002edcd  mov     r9d, eax; char *
0x18002edd0  mov     edx, 144h; void *
0x18002edd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002edda  mov     edx, 1; unsigned int
0x18002eddf  mov     rcx, rbx; this
0x18002ede2  call    ??_GExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(uint)
0x18002ede7  mov     eax, edi
0x18002ede9  jmp     short loc_18002EE1D
0x18002edeb  mov     rdx, rbx
0x18002edee  mov     rcx, rsi
0x18002edf1  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x18002edf6  xor     eax, eax
0x18002edf8  jmp     short loc_18002EE1D
0x18002edfa  mov     rcx, [rsp+178h]; this
0x18002ee02  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18002ee09  mov     ebx, 8007000Eh
0x18002ee0e  mov     edx, 143h; void *
0x18002ee13  mov     r9d, ebx; char *
0x18002ee16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ee1b  mov     eax, ebx
0x18002ee1d  mov     rcx, [rsp+178h+var_28]
0x18002ee25  xor     rcx, rsp; StackCookie
0x18002ee28  call    __security_check_cookie
0x18002ee2d  mov     rbx, [rsp+178h+arg_18]
0x18002ee35  add     rsp, 160h
0x18002ee3c  pop     rdi
0x18002ee3d  pop     rsi
0x18002ee3e  pop     rbp
0x18002ee3f  retn
```
