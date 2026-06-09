# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetCount(unsigned __int64 *)

- ea: `0x180010bf0`
- end: `0x180010c8f`
- name: `?GetCount@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJPEA_K@Z`
- size: `159`
- prototype: `__int64 __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180010bf0`
- `0x180014800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010c5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010c5b`

## string_xrefs

- `0x180010c6a`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetCount(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *this,
        unsigned __int64 *a2)
{
  HKEY v3; // rcx
  unsigned int v4; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD v8; // [rsp+70h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = (HKEY)*((_QWORD *)this + 1);
  if ( v3 )
  {
    v8 = 0;
    v4 = RegQueryInfoKeyW(v3, 0, 0, 0, &v8, 0, 0, 0, 0, 0, 0, 0);
    if ( v4 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x137,
               (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
               (const char *)v4,
               lpcSubKeys);
    *a2 = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180010bf0  mov     rax, rsp
0x180010bf3  push    rbx
0x180010bf4  sub     rsp, 60h
0x180010bf8  mov     qword ptr [rdx], 0
0x180010bff  mov     rbx, rdx
0x180010c02  mov     rcx, [rcx+8]; hKey
0x180010c06  test    rcx, rcx
0x180010c09  jz      short loc_180010C87
0x180010c0b  mov     qword ptr [rax-10h], 0
0x180010c13  xor     r9d, r9d; lpReserved
0x180010c16  mov     qword ptr [rax-18h], 0
0x180010c1e  xor     r8d, r8d; lpcchClass
0x180010c21  mov     qword ptr [rax-20h], 0
0x180010c29  xor     edx, edx; lpClass
0x180010c2b  mov     qword ptr [rax-28h], 0
0x180010c33  mov     qword ptr [rax-30h], 0
0x180010c3b  mov     qword ptr [rax-38h], 0
0x180010c43  mov     qword ptr [rax-40h], 0
0x180010c4b  mov     dword ptr [rax+8], 0
0x180010c52  lea     rax, [rax+8]
0x180010c56  mov     qword ptr [rsp+68h+lpcSubKeys], rax; unsigned int
0x180010c5b  call    cs:__imp_RegQueryInfoKeyW
0x180010c61  test    eax, eax
0x180010c63  jz      short loc_180010C80
0x180010c65  mov     rcx, [rsp+68h]; this
0x180010c6a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180010c71  mov     r9d, eax; char *
0x180010c74  mov     edx, 137h; void *
0x180010c79  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010c7e  jmp     short loc_180010C89
0x180010c80  mov     eax, [rsp+68h+arg_0]
0x180010c84  mov     [rbx], rax
0x180010c87  xor     eax, eax
0x180010c89  add     rsp, 60h
0x180010c8d  pop     rbx
0x180010c8e  retn
```
