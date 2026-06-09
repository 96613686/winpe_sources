# Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider>(HSTRING__ *,Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId)

- ea: `0x18000cd44`
- end: `0x18000cd89`
- name: `??$TryActivateContractExtension@UICaptureItemProvider@Capture@PlatformExtensions@Internal@Windows@@@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAPEAUICaptureItemProvider@Capture@012@UWindowId@WindowManagement@ApplicationModel@12@@Z`
- size: `69`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800169d8`
- `0x180016dc4`

## callees

- `0x18000907c`
- `0x18000cd44`
- `0x180015d0c`

## string_xrefs

- `0x18000cd69`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider>(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
         a1,
         a3,
         &GUID_37cdd3c9_2727_4268_a562_b56da52d270a,
         a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x299,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000cd44  push    rbx; int
0x18000cd46  sub     rsp, 20h
0x18000cd4a  mov     eax, r8d
0x18000cd4d  mov     r9, rdx
0x18000cd50  mov     edx, eax
0x18000cd52  lea     r8, _GUID_37cdd3c9_2727_4268_a562_b56da52d270a
0x18000cd59  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x18000cd5e  mov     ebx, eax
0x18000cd60  test    eax, eax
0x18000cd62  jns     short loc_18000CD81
0x18000cd64  mov     rcx, [rsp+28h]; this
0x18000cd69  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000cd70  mov     r9d, eax; char *
0x18000cd73  mov     edx, 299h; void *
0x18000cd78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd7d  mov     eax, ebx
0x18000cd7f  jmp     short loc_18000CD83
0x18000cd81  xor     eax, eax
0x18000cd83  add     rsp, 20h
0x18000cd87  pop     rbx
0x18000cd88  retn
```
