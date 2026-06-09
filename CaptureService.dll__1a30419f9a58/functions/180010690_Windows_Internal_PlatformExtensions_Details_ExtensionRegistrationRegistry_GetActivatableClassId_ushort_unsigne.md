# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetActivatableClassId(ushort *,unsigned __int64)

- ea: `0x180010690`
- end: `0x1800106f2`
- name: `?GetActivatableClassId@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJPEAG_K@Z`
- size: `98`
- prototype: `__int64 __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180010690`
- `0x180014800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800106c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800106c6`

## string_xrefs

- `0x1800106a3`: `ActivatableClassID`
- `0x1800106d5`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetActivatableClassId(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this,
        unsigned __int16 *a2,
        int a3)
{
  HKEY v3; // rcx
  unsigned int ValueW; // eax
  unsigned int v6; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v3 = (HKEY)*((_QWORD *)this + 1);
  v8 = 2 * a3;
  ValueW = RegGetValueW(v3, 0, L"ActivatableClassID", 2u, 0, a2, (LPDWORD)&v8);
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x107,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
             (const char *)ValueW,
             v6);
  else
    return 0;
}

```

## disassembly

```asm
0x180010690  mov     r11, rsp
0x180010693  sub     rsp, 48h
0x180010697  mov     rcx, [rcx+8]; hkey
0x18001069b  lea     eax, [r8+r8]
0x18001069f  mov     [rsp+48h+arg_0], eax
0x1800106a3  lea     r8, Value; "ActivatableClassID"
0x1800106aa  lea     rax, [r11+8]
0x1800106ae  mov     r9d, 2; dwFlags
0x1800106b4  mov     [r11-18h], rax
0x1800106b8  mov     [r11-20h], rdx
0x1800106bc  xor     edx, edx; lpSubKey
0x1800106be  mov     qword ptr [r11-28h], 0
0x1800106c6  call    cs:__imp_RegGetValueW
0x1800106cc  test    eax, eax
0x1800106ce  jz      short loc_1800106EB
0x1800106d0  mov     rcx, [rsp+48h]; this
0x1800106d5  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800106dc  mov     r9d, eax; char *
0x1800106df  mov     edx, 107h; void *
0x1800106e4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800106e9  jmp     short loc_1800106ED
0x1800106eb  xor     eax, eax
0x1800106ed  add     rsp, 48h
0x1800106f1  retn
```
