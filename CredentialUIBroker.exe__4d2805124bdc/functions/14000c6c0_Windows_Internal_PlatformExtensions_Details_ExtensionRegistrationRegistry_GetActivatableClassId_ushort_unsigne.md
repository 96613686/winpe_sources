# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetActivatableClassId(ushort *,unsigned __int64)

- ea: `0x14000c6c0`
- end: `0x14000c722`
- name: `?GetActivatableClassId@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJPEAG_K@Z`
- size: `98`
- prototype: `int __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x14000c6c0`
- `0x140013720`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14000c6f6`
- `ADVAPI32!RegGetValueW` at `0x14000c6f6`

## string_xrefs

- `0x14000c705`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x14000c6d3`: `ActivatableClassID`

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
0x14000c6c0  mov     r11, rsp
0x14000c6c3  sub     rsp, 48h
0x14000c6c7  mov     rcx, [rcx+8]; hkey
0x14000c6cb  lea     eax, [r8+r8]
0x14000c6cf  mov     [rsp+48h+arg_0], eax
0x14000c6d3  lea     r8, Value; "ActivatableClassID"
0x14000c6da  lea     rax, [r11+8]
0x14000c6de  mov     r9d, 2; dwFlags
0x14000c6e4  mov     [r11-18h], rax
0x14000c6e8  mov     [r11-20h], rdx
0x14000c6ec  xor     edx, edx; lpSubKey
0x14000c6ee  mov     qword ptr [r11-28h], 0
0x14000c6f6  call    cs:__imp_RegGetValueW
0x14000c6fc  test    eax, eax
0x14000c6fe  jz      short loc_14000C71B
0x14000c700  mov     rcx, [rsp+48h]; this
0x14000c705  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000c70c  mov     r9d, eax; char *
0x14000c70f  mov     edx, 107h; void *
0x14000c714  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000c719  jmp     short loc_14000C71D
0x14000c71b  xor     eax, eax
0x14000c71d  add     rsp, 48h
0x14000c721  retn
```
