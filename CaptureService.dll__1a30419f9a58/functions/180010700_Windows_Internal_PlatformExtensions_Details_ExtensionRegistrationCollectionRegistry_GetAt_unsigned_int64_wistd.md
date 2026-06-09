# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(unsigned __int64,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>> &)

- ea: `0x180010700`
- end: `0x18001086a`
- name: `?GetAt@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJ_KAEAV?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `362`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180002e60`
- `0x18000335c`
- `0x180003bc8`
- `0x18000907c`
- `0x18000e930`
- `0x180010700`
- `0x180012134`
- `0x180014800`
- `0x1800188fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001075d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001075d`

## string_xrefs

- `0x18001076f`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800107f8`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180010834`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

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
        1);
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
0x180010700  push    rbx
0x180010702  push    rsi
0x180010703  push    rdi
0x180010704  sub     rsp, 160h
0x18001070b  mov     rax, cs:__security_cookie
0x180010712  xor     rax, rsp
0x180010715  mov     [rsp+178h+var_28], rax
0x18001071d  mov     [rsp+178h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180010726  lea     r9, [rsp+178h+cchName]; lpcchName
0x18001072b  mov     [rsp+178h+lpcchClass], 0; lpcchClass
0x180010734  mov     rsi, r8
0x180010737  mov     rdi, rcx
0x18001073a  mov     [rsp+178h+lpClass], 0; lpClass
0x180010743  mov     rcx, [rcx+8]; hKey
0x180010747  lea     r8, [rsp+178h+Name]; lpName
0x18001074c  mov     [rsp+178h+lpReserved], 0; int
0x180010755  mov     [rsp+178h+cchName], 80h
0x18001075d  call    cs:__imp_RegEnumKeyExW
0x180010763  test    eax, eax
0x180010765  jz      short loc_180010788
0x180010767  mov     rcx, [rsp+178h]; this
0x18001076f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180010776  mov     r9d, eax; char *
0x180010779  mov     edx, 141h; void *
0x18001077e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010783  jmp     loc_18001084F
0x180010788  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001078f  mov     ecx, 118h; unsigned __int64
0x180010794  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010799  mov     rbx, rax
0x18001079c  test    rax, rax
0x18001079f  jz      loc_18001082C
0x1800107a5  xor     ecx, ecx
0x1800107a7  lea     rax, ??_7ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable'
0x1800107ae  mov     [rbx], rax
0x1800107b1  xor     edx, edx; Val
0x1800107b3  mov     qword ptr [rbx+8], 0
0x1800107bb  mov     r8d, 0FEh; Size
0x1800107c1  mov     [rbx+18h], cx
0x1800107c5  lea     rcx, [rbx+1Ah]; void *
0x1800107c9  mov     byte ptr [rbx+10h], 0
0x1800107cd  mov     dword ptr [rbx+14h], 0
0x1800107d4  call    memset_0
0x1800107d9  mov     rdx, [rdi+8]; HKEY
0x1800107dd  lea     r8, [rsp+178h+Name]; unsigned __int16 *
0x1800107e2  mov     rcx, rbx; this
0x1800107e5  call    ?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)
0x1800107ea  mov     edi, eax
0x1800107ec  test    eax, eax
0x1800107ee  jns     short loc_18001081D
0x1800107f0  mov     rcx, [rsp+178h]; this
0x1800107f8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800107ff  mov     r9d, eax; char *
0x180010802  mov     edx, 144h; void *
0x180010807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001080c  mov     edx, 1; unsigned int
0x180010811  mov     rcx, rbx; this
0x180010814  call    ??_GExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(uint)
0x180010819  mov     eax, edi
0x18001081b  jmp     short loc_18001084F
0x18001081d  mov     rdx, rbx
0x180010820  mov     rcx, rsi
0x180010823  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180010828  xor     eax, eax
0x18001082a  jmp     short loc_18001084F
0x18001082c  mov     rcx, [rsp+178h]; this
0x180010834  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18001083b  mov     ebx, 8007000Eh
0x180010840  mov     edx, 143h; void *
0x180010845  mov     r9d, ebx; char *
0x180010848  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001084d  mov     eax, ebx
0x18001084f  mov     rcx, [rsp+178h+var_28]
0x180010857  xor     rcx, rsp; StackCookie
0x18001085a  call    __security_check_cookie
0x18001085f  add     rsp, 160h
0x180010866  pop     rdi
0x180010867  pop     rsi
0x180010868  pop     rbx
0x180010869  retn
```
