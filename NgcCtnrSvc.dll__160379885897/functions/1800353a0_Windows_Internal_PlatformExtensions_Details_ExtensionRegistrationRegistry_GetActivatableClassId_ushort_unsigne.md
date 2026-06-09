# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetActivatableClassId(ushort *,unsigned __int64)

- ea: `0x1800353a0`
- end: `0x180035409`
- name: `?GetActivatableClassId@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJPEAG_K@Z`
- size: `105`
- prototype: `__int64 __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x1800232a0`
- `0x1800353a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800353d6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800353d6`

## string_xrefs

- `0x1800353eb`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800353b3`: `ActivatableClassID`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetActivatableClassId(
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
0x1800353a0  mov     r11, rsp
0x1800353a3  sub     rsp, 48h
0x1800353a7  mov     rcx, [rcx+8]; hkey
0x1800353ab  lea     eax, [r8+r8]
0x1800353af  mov     [rsp+48h+arg_0], eax
0x1800353b3  lea     r8, aActivatablecla; "ActivatableClassID"
0x1800353ba  lea     rax, [r11+8]
0x1800353be  mov     r9d, 2; dwFlags
0x1800353c4  mov     [r11-18h], rax
0x1800353c8  mov     [r11-20h], rdx
0x1800353cc  xor     edx, edx; lpSubKey
0x1800353ce  mov     qword ptr [r11-28h], 0
0x1800353d6  call    cs:__imp_RegGetValueW
0x1800353dd  nop     dword ptr [rax+rax+00h]
0x1800353e2  test    eax, eax
0x1800353e4  jz      short loc_180035401
0x1800353e6  mov     rcx, [rsp+48h]; this
0x1800353eb  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800353f2  mov     r9d, eax; char *
0x1800353f5  mov     edx, 107h; void *
0x1800353fa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800353ff  jmp     short loc_180035403
0x180035401  xor     eax, eax
0x180035403  add     rsp, 48h
0x180035407  retn
```
