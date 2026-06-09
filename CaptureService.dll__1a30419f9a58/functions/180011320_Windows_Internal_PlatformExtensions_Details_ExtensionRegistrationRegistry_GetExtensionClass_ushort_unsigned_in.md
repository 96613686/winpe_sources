# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetExtensionClass(ushort *,unsigned __int64)

- ea: `0x180011320`
- end: `0x180011366`
- name: `?GetExtensionClass@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJPEAG_K@Z`
- size: `70`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000907c`
- `0x1800097c8`
- `0x180011320`

## string_xrefs

- `0x180011346`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

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
0x180011320  push    rbx; int
0x180011322  sub     rsp, 20h
0x180011326  mov     rax, r8
0x180011329  mov     r9, rdx
0x18001132c  lea     r8, [rcx+18h]; unsigned __int16 *
0x180011330  mov     rdx, rax; unsigned __int64
0x180011333  mov     rcx, r9; unsigned __int16 *
0x180011336  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001133b  mov     ebx, eax
0x18001133d  test    eax, eax
0x18001133f  jns     short loc_18001135E
0x180011341  mov     rcx, [rsp+28h]; this
0x180011346  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18001134d  mov     r9d, eax; char *
0x180011350  mov     edx, 100h; void *
0x180011355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001135a  mov     eax, ebx
0x18001135c  jmp     short loc_180011360
0x18001135e  xor     eax, eax
0x180011360  add     rsp, 20h
0x180011364  pop     rbx
0x180011365  retn
```
