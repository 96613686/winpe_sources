# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(unsigned __int64,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>> &)

- ea: `0x180031e20`
- end: `0x180031f8a`
- name: `?GetAt@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJ_KAEAV?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `362`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x18000720c`
- `0x180018dbc`
- `0x18001ef98`
- `0x18002cd10`
- `0x180031e20`
- `0x180037060`
- `0x18003c67c`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031e7d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031e7d`

## string_xrefs

- `0x180031e8f`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180031f18`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180031f54`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(
        __int64 a1,
        DWORD a2,
        __int64 a3)
{
  HKEY v5; // rcx
  unsigned int v6; // eax
  _QWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  unsigned int lpReserved; // [rsp+20h] [rbp-158h]
  DWORD cchName[4]; // [rsp+40h] [rbp-138h] BYREF
  WCHAR Name[128]; // [rsp+50h] [rbp-128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v5 = *(HKEY *)(a1 + 8);
  cchName[0] = 128;
  v6 = RegEnumKeyExW(v5, a2, Name, cchName, 0, 0, 0, 0);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x141,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
             (const char *)v6,
             lpReserved);
  v8 = operator new(0x118u, (const struct std::nothrow_t *)std::nothrow);
  if ( v8 )
  {
    *v8 = &Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable';
    v8[1] = 0;
    *((_WORD *)v8 + 12) = 0;
    *((_BYTE *)v8 + 16) = 0;
    *((_DWORD *)v8 + 5) = 0;
    memset_0((char *)v8 + 26, 0, 0xFEu);
    v9 = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(
           (Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *)v8,
           *(HKEY *)(a1 + 8),
           Name);
    v10 = v9;
    if ( v9 >= 0 )
    {
      wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
        a3,
        v8);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
        (const char *)(unsigned int)v9,
        lpReserved);
      Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(
        (Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *)v8,
        1);
      return v10;
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
0x180031e20  push    rbx
0x180031e22  push    rsi
0x180031e23  push    rdi
0x180031e24  sub     rsp, 160h
0x180031e2b  mov     rax, cs:__security_cookie
0x180031e32  xor     rax, rsp
0x180031e35  mov     [rsp+178h+var_28], rax
0x180031e3d  mov     [rsp+178h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180031e46  lea     r9, [rsp+178h+cchName]; lpcchName
0x180031e4b  mov     [rsp+178h+lpcchClass], 0; lpcchClass
0x180031e54  mov     rsi, r8
0x180031e57  mov     rdi, rcx
0x180031e5a  mov     [rsp+178h+lpClass], 0; lpClass
0x180031e63  mov     rcx, [rcx+8]; hKey
0x180031e67  lea     r8, [rsp+178h+Name]; lpName
0x180031e6c  mov     [rsp+178h+lpReserved], 0; int
0x180031e75  mov     [rsp+178h+cchName], 80h
0x180031e7d  call    cs:__imp_RegEnumKeyExW
0x180031e83  test    eax, eax
0x180031e85  jz      short loc_180031EA8
0x180031e87  mov     rcx, [rsp+178h]; this
0x180031e8f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180031e96  mov     r9d, eax; char *
0x180031e99  mov     edx, 141h; void *
0x180031e9e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031ea3  jmp     loc_180031F6F
0x180031ea8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031eaf  mov     ecx, 118h; unsigned __int64
0x180031eb4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031eb9  mov     rbx, rax
0x180031ebc  test    rax, rax
0x180031ebf  jz      loc_180031F4C
0x180031ec5  xor     ecx, ecx
0x180031ec7  lea     rax, ??_7ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable'
0x180031ece  mov     [rbx], rax
0x180031ed1  xor     edx, edx; Val
0x180031ed3  mov     qword ptr [rbx+8], 0
0x180031edb  mov     r8d, 0FEh; Size
0x180031ee1  mov     [rbx+18h], cx
0x180031ee5  lea     rcx, [rbx+1Ah]; void *
0x180031ee9  mov     byte ptr [rbx+10h], 0
0x180031eed  mov     dword ptr [rbx+14h], 0
0x180031ef4  call    memset_0
0x180031ef9  mov     rdx, [rdi+8]; HKEY
0x180031efd  lea     r8, [rsp+178h+Name]; unsigned __int16 *
0x180031f02  mov     rcx, rbx; this
0x180031f05  call    ?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)
0x180031f0a  mov     edi, eax
0x180031f0c  test    eax, eax
0x180031f0e  jns     short loc_180031F3D
0x180031f10  mov     rcx, [rsp+178h]; this
0x180031f18  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180031f1f  mov     r9d, eax; char *
0x180031f22  mov     edx, 144h; void *
0x180031f27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031f2c  mov     edx, 1; unsigned int
0x180031f31  mov     rcx, rbx; this
0x180031f34  call    ??_GExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(uint)
0x180031f39  mov     eax, edi
0x180031f3b  jmp     short loc_180031F6F
0x180031f3d  mov     rdx, rbx
0x180031f40  mov     rcx, rsi
0x180031f43  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180031f48  xor     eax, eax
0x180031f4a  jmp     short loc_180031F6F
0x180031f4c  mov     rcx, [rsp+178h]; this
0x180031f54  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180031f5b  mov     ebx, 8007000Eh
0x180031f60  mov     edx, 143h; void *
0x180031f65  mov     r9d, ebx; char *
0x180031f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031f6d  mov     eax, ebx
0x180031f6f  mov     rcx, [rsp+178h+var_28]
0x180031f77  xor     rcx, rsp; StackCookie
0x180031f7a  call    __security_check_cookie
0x180031f7f  add     rsp, 160h
0x180031f86  pop     rdi
0x180031f87  pop     rsi
0x180031f88  pop     rbx
0x180031f89  retn
```
