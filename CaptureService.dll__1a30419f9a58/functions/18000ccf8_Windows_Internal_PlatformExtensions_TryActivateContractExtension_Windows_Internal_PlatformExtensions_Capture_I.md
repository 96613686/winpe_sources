# Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2>(HSTRING__ *,Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2 * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId)

- ea: `0x18000ccf8`
- end: `0x18000cd3d`
- name: `??$TryActivateContractExtension@UICaptureItemProvider2@Capture@PlatformExtensions@Internal@Windows@@@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAPEAUICaptureItemProvider2@Capture@012@UWindowId@WindowManagement@ApplicationModel@12@@Z`
- size: `69`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180016540`
- `0x1800167e0`

## callees

- `0x18000907c`
- `0x18000ccf8`
- `0x180015d0c`

## string_xrefs

- `0x18000cd1d`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2>(
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
         &GUID_3db98853_0e44_4cd5_90fe_192571881978,
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
0x18000ccf8  push    rbx; int
0x18000ccfa  sub     rsp, 20h
0x18000ccfe  mov     eax, r8d
0x18000cd01  mov     r9, rdx
0x18000cd04  mov     edx, eax
0x18000cd06  lea     r8, _GUID_3db98853_0e44_4cd5_90fe_192571881978
0x18000cd0d  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x18000cd12  mov     ebx, eax
0x18000cd14  test    eax, eax
0x18000cd16  jns     short loc_18000CD35
0x18000cd18  mov     rcx, [rsp+28h]; this
0x18000cd1d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000cd24  mov     r9d, eax; char *
0x18000cd27  mov     edx, 299h; void *
0x18000cd2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd31  mov     eax, ebx
0x18000cd33  jmp     short loc_18000CD37
0x18000cd35  xor     eax, eax
0x18000cd37  add     rsp, 20h
0x18000cd3b  pop     rbx
0x18000cd3c  retn
```
