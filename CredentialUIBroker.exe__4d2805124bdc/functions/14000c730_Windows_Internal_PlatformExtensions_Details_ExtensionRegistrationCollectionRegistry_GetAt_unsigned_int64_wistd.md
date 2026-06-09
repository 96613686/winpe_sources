# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(unsigned __int64,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>> &)

- ea: `0x14000c730`
- end: `0x14000c89a`
- name: `?GetAt@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJ_KAEAV?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `362`
- prototype: `int __fastcall(__int64, DWORD, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x140003620`
- `0x140003644`
- `0x1400042c4`
- `0x14000a4e0`
- `0x14000c730`
- `0x14000e760`
- `0x1400136fc`
- `0x140013720`
- `0x14001af00`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x14000c78d`
- `ADVAPI32!RegEnumKeyExW` at `0x14000c78d`

## string_xrefs

- `0x14000c79f`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x14000c828`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x14000c864`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(
        __int64 a1,
        DWORD a2,
        __int64 a3)
{
  HKEY v5; // rcx
  unsigned int v6; // eax
  _QWORD *v8; // rbx
  int v9; // eax
  int v10; // edi
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
  v8 = operator new(0x118u, (const struct std::nothrow_t *)&std::nothrow);
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
    return -2147024882;
  }
}

```

## disassembly

```asm
0x14000c730  push    rbx
0x14000c732  push    rsi
0x14000c733  push    rdi
0x14000c734  sub     rsp, 160h
0x14000c73b  mov     rax, cs:__security_cookie
0x14000c742  xor     rax, rsp
0x14000c745  mov     [rsp+178h+var_28], rax
0x14000c74d  mov     [rsp+178h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14000c756  lea     r9, [rsp+178h+cchName]; lpcchName
0x14000c75b  mov     [rsp+178h+lpcchClass], 0; lpcchClass
0x14000c764  mov     rsi, r8
0x14000c767  mov     rdi, rcx
0x14000c76a  mov     [rsp+178h+lpClass], 0; lpClass
0x14000c773  mov     rcx, [rcx+8]; hKey
0x14000c777  lea     r8, [rsp+178h+Name]; lpName
0x14000c77c  mov     [rsp+178h+lpReserved], 0; int
0x14000c785  mov     [rsp+178h+cchName], 80h
0x14000c78d  call    cs:__imp_RegEnumKeyExW
0x14000c793  test    eax, eax
0x14000c795  jz      short loc_14000C7B8
0x14000c797  mov     rcx, [rsp+178h]; this
0x14000c79f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000c7a6  mov     r9d, eax; char *
0x14000c7a9  mov     edx, 141h; void *
0x14000c7ae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000c7b3  jmp     loc_14000C87F
0x14000c7b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c7bf  mov     ecx, 118h; unsigned __int64
0x14000c7c4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000c7c9  mov     rbx, rax
0x14000c7cc  test    rax, rax
0x14000c7cf  jz      loc_14000C85C
0x14000c7d5  xor     ecx, ecx
0x14000c7d7  lea     rax, ??_7ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable'
0x14000c7de  mov     [rbx], rax
0x14000c7e1  xor     edx, edx; Val
0x14000c7e3  mov     qword ptr [rbx+8], 0
0x14000c7eb  mov     r8d, 0FEh; Size
0x14000c7f1  mov     [rbx+18h], cx
0x14000c7f5  lea     rcx, [rbx+1Ah]; void *
0x14000c7f9  mov     byte ptr [rbx+10h], 0
0x14000c7fd  mov     dword ptr [rbx+14h], 0
0x14000c804  call    memset_0
0x14000c809  mov     rdx, [rdi+8]; HKEY
0x14000c80d  lea     r8, [rsp+178h+Name]; unsigned __int16 *
0x14000c812  mov     rcx, rbx; this
0x14000c815  call    ?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)
0x14000c81a  mov     edi, eax
0x14000c81c  test    eax, eax
0x14000c81e  jns     short loc_14000C84D
0x14000c820  mov     rcx, [rsp+178h]; this
0x14000c828  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000c82f  mov     r9d, eax; char *
0x14000c832  mov     edx, 144h; void *
0x14000c837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c83c  mov     edx, 1; unsigned int
0x14000c841  mov     rcx, rbx; this
0x14000c844  call    ??_GExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(uint)
0x14000c849  mov     eax, edi
0x14000c84b  jmp     short loc_14000C87F
0x14000c84d  mov     rdx, rbx
0x14000c850  mov     rcx, rsi
0x14000c853  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x14000c858  xor     eax, eax
0x14000c85a  jmp     short loc_14000C87F
0x14000c85c  mov     rcx, [rsp+178h]; this
0x14000c864  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000c86b  mov     ebx, 8007000Eh
0x14000c870  mov     edx, 143h; void *
0x14000c875  mov     r9d, ebx; char *
0x14000c878  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c87d  mov     eax, ebx
0x14000c87f  mov     rcx, [rsp+178h+var_28]
0x14000c887  xor     rcx, rsp; StackCookie
0x14000c88a  call    __security_check_cookie
0x14000c88f  add     rsp, 160h
0x14000c896  pop     rdi
0x14000c897  pop     rsi
0x14000c898  pop     rbx
0x14000c899  retn
```
