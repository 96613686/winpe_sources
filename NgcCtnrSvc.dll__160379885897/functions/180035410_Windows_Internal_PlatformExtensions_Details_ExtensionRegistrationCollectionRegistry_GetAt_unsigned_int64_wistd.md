# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(unsigned __int64,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>> &)

- ea: `0x180035410`
- end: `0x180035581`
- name: `?GetAt@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJ_KAEAV?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180017034`
- `0x180019970`
- `0x180023278`
- `0x1800232a0`
- `0x1800286d4`
- `0x18002c640`
- `0x18002ce30`
- `0x18002d518`
- `0x180035410`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003546d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003546d`

## string_xrefs

- `0x180035485`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18003550e`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18003554a`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

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
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
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
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)v9,
        lpReserved);
      Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(
        (Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *)v8,
        1u);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)0x8007000ELL,
      lpReserved);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180035410  push    rbx
0x180035412  push    rsi
0x180035413  push    rdi
0x180035414  sub     rsp, 160h
0x18003541b  mov     rax, cs:__security_cookie
0x180035422  xor     rax, rsp
0x180035425  mov     [rsp+178h+var_28], rax
0x18003542d  mov     [rsp+178h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180035436  lea     r9, [rsp+178h+cchName]; lpcchName
0x18003543b  mov     [rsp+178h+lpcchClass], 0; lpcchClass
0x180035444  mov     rsi, r8
0x180035447  mov     rdi, rcx
0x18003544a  mov     [rsp+178h+lpClass], 0; lpClass
0x180035453  mov     rcx, [rcx+8]; hKey
0x180035457  lea     r8, [rsp+178h+Name]; lpName
0x18003545c  mov     [rsp+178h+lpReserved], 0; int
0x180035465  mov     [rsp+178h+cchName], 80h
0x18003546d  call    cs:__imp_RegEnumKeyExW
0x180035474  nop     dword ptr [rax+rax+00h]
0x180035479  test    eax, eax
0x18003547b  jz      short loc_18003549E
0x18003547d  mov     rcx, [rsp+178h]; this
0x180035485  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18003548c  mov     r9d, eax; char *
0x18003548f  mov     edx, 141h; void *
0x180035494  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035499  jmp     loc_180035565
0x18003549e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800354a5  mov     ecx, 118h; unsigned __int64
0x1800354aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800354af  mov     rbx, rax
0x1800354b2  test    rax, rax
0x1800354b5  jz      loc_180035542
0x1800354bb  xor     ecx, ecx
0x1800354bd  lea     rax, ??_7ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable'
0x1800354c4  mov     [rbx], rax
0x1800354c7  xor     edx, edx; Val
0x1800354c9  mov     qword ptr [rbx+8], 0
0x1800354d1  mov     r8d, 0FEh; Size
0x1800354d7  mov     [rbx+18h], cx
0x1800354db  lea     rcx, [rbx+1Ah]; void *
0x1800354df  mov     byte ptr [rbx+10h], 0
0x1800354e3  mov     dword ptr [rbx+14h], 0
0x1800354ea  call    memset_0
0x1800354ef  mov     rdx, [rdi+8]; HKEY
0x1800354f3  lea     r8, [rsp+178h+Name]; unsigned __int16 *
0x1800354f8  mov     rcx, rbx; this
0x1800354fb  call    ?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)
0x180035500  mov     edi, eax
0x180035502  test    eax, eax
0x180035504  jns     short loc_180035533
0x180035506  mov     rcx, [rsp+178h]; this
0x18003550e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180035515  mov     r9d, eax; char *
0x180035518  mov     edx, 144h; void *
0x18003551d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035522  mov     edx, 1; unsigned int
0x180035527  mov     rcx, rbx; this
0x18003552a  call    ??_GExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(uint)
0x18003552f  mov     eax, edi
0x180035531  jmp     short loc_180035565
0x180035533  mov     rdx, rbx
0x180035536  mov     rcx, rsi
0x180035539  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x18003553e  xor     eax, eax
0x180035540  jmp     short loc_180035565
0x180035542  mov     rcx, [rsp+178h]; this
0x18003554a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180035551  mov     ebx, 8007000Eh
0x180035556  mov     edx, 143h; void *
0x18003555b  mov     r9d, ebx; char *
0x18003555e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035563  mov     eax, ebx
0x180035565  mov     rcx, [rsp+178h+var_28]
0x18003556d  xor     rcx, rsp; StackCookie
0x180035570  call    __security_check_cookie
0x180035575  add     rsp, 160h
0x18003557c  pop     rdi
0x18003557d  pop     rsi
0x18003557e  pop     rbx
0x18003557f  retn
```
