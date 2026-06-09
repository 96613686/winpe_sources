# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(unsigned __int64,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>> &)

- ea: `0x18002d790`
- end: `0x18002d8f1`
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
- `0x180029070`
- `0x18002d790`
- `0x180033fc8`
- `0x18003a1d4`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002d7e3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002d7e3`

## string_xrefs

- `0x18002d7fb`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18002d876`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18002d8b2`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

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
0x18002d790  mov     [rsp+arg_18], rbx
0x18002d795  push    rbp
0x18002d796  push    rsi
0x18002d797  push    rdi
0x18002d798  sub     rsp, 160h
0x18002d79f  mov     rax, cs:__security_cookie
0x18002d7a6  xor     rax, rsp
0x18002d7a9  mov     [rsp+178h+var_28], rax
0x18002d7b1  xor     ebp, ebp
0x18002d7b3  mov     [rsp+178h+cchName], 80h
0x18002d7bb  mov     [rsp+178h+lpftLastWriteTime], rbp; lpftLastWriteTime
0x18002d7c0  lea     r9, [rsp+178h+cchName]; lpcchName
0x18002d7c5  mov     [rsp+178h+lpcchClass], rbp; lpcchClass
0x18002d7ca  mov     rsi, r8
0x18002d7cd  mov     rdi, rcx
0x18002d7d0  mov     [rsp+178h+lpClass], rbp; lpClass
0x18002d7d5  mov     rcx, [rcx+8]; hKey
0x18002d7d9  lea     r8, [rsp+178h+Name]; lpName
0x18002d7de  mov     [rsp+178h+lpReserved], rbp; int
0x18002d7e3  call    cs:__imp_RegEnumKeyExW
0x18002d7ea  nop     dword ptr [rax+rax+00h]
0x18002d7ef  test    eax, eax
0x18002d7f1  jz      short loc_18002D814
0x18002d7f3  mov     rcx, [rsp+178h]; this
0x18002d7fb  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18002d802  mov     r9d, eax; char *
0x18002d805  mov     edx, 141h; void *
0x18002d80a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d80f  jmp     loc_18002D8CD
0x18002d814  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d81b  mov     ecx, 118h; unsigned __int64
0x18002d820  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d825  mov     rbx, rax
0x18002d828  test    rax, rax
0x18002d82b  jz      short loc_18002D8AA
0x18002d82d  lea     rax, ??_7ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable'
0x18002d834  xor     edx, edx; Val
0x18002d836  mov     [rbx], rax
0x18002d839  lea     rcx, [rbx+1Ah]; void *
0x18002d83d  mov     [rbx+8], rbp
0x18002d841  mov     r8d, 0FEh; Size
0x18002d847  mov     [rbx+10h], bpl
0x18002d84b  mov     [rbx+14h], ebp
0x18002d84e  mov     [rbx+18h], bp
0x18002d852  call    memset_0
0x18002d857  mov     rdx, [rdi+8]; HKEY
0x18002d85b  lea     r8, [rsp+178h+Name]; unsigned __int16 *
0x18002d860  mov     rcx, rbx; this
0x18002d863  call    ?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)
0x18002d868  mov     edi, eax
0x18002d86a  test    eax, eax
0x18002d86c  jns     short loc_18002D89B
0x18002d86e  mov     rcx, [rsp+178h]; this
0x18002d876  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18002d87d  mov     r9d, eax; char *
0x18002d880  mov     edx, 144h; void *
0x18002d885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d88a  mov     edx, 1; unsigned int
0x18002d88f  mov     rcx, rbx; this
0x18002d892  call    ??_GExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(uint)
0x18002d897  mov     eax, edi
0x18002d899  jmp     short loc_18002D8CD
0x18002d89b  mov     rdx, rbx
0x18002d89e  mov     rcx, rsi
0x18002d8a1  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x18002d8a6  xor     eax, eax
0x18002d8a8  jmp     short loc_18002D8CD
0x18002d8aa  mov     rcx, [rsp+178h]; this
0x18002d8b2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18002d8b9  mov     ebx, 8007000Eh
0x18002d8be  mov     edx, 143h; void *
0x18002d8c3  mov     r9d, ebx; char *
0x18002d8c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d8cb  mov     eax, ebx
0x18002d8cd  mov     rcx, [rsp+178h+var_28]
0x18002d8d5  xor     rcx, rsp; StackCookie
0x18002d8d8  call    __security_check_cookie
0x18002d8dd  mov     rbx, [rsp+178h+arg_18]
0x18002d8e5  add     rsp, 160h
0x18002d8ec  pop     rdi
0x18002d8ed  pop     rsi
0x18002d8ee  pop     rbp
0x18002d8ef  retn
```
