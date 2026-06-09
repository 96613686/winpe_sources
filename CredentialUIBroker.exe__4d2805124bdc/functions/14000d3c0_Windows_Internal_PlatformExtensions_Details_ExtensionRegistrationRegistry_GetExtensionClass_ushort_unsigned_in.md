# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetExtensionClass(ushort *,unsigned __int64)

- ea: `0x14000d3c0`
- end: `0x14000d406`
- name: `?GetExtensionClass@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJPEAG_K@Z`
- size: `70`
- prototype: `__int64 __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x14000d3c0`
- `0x1400136fc`
- `0x140016378`

## string_xrefs

- `0x14000d3e6`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetExtensionClass(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this,
        unsigned __int16 *a2,
        unsigned __int64 a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = StringCchCopyW(a2, a3, (const unsigned __int16 *)this + 12);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x100,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14000d3c0  push    rbx; int
0x14000d3c2  sub     rsp, 20h
0x14000d3c6  mov     rax, r8
0x14000d3c9  mov     r9, rdx
0x14000d3cc  lea     r8, [rcx+18h]; unsigned __int16 *
0x14000d3d0  mov     rdx, rax; unsigned __int64
0x14000d3d3  mov     rcx, r9; unsigned __int16 *
0x14000d3d6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000d3db  mov     ebx, eax
0x14000d3dd  test    eax, eax
0x14000d3df  jns     short loc_14000D3FE
0x14000d3e1  mov     rcx, [rsp+28h]; this
0x14000d3e6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000d3ed  mov     r9d, eax; char *
0x14000d3f0  mov     edx, 100h; void *
0x14000d3f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d3fa  mov     eax, ebx
0x14000d3fc  jmp     short loc_14000D400
0x14000d3fe  xor     eax, eax
0x14000d400  add     rsp, 20h
0x14000d404  pop     rbx
0x14000d405  retn
```
