# winrt::impl::produce<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper,winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics>::get_ProcessId(uint *)

- ea: `0x18000d0f0`
- end: `0x18000d114`
- name: `?get_ProcessId@?$produce@UTranscodeWallpaper@implementation@Themes@Internal@Windows@winrt@@UITranscodeWallpaperStatics@3456@@impl@winrt@@UEAAHPEAI@Z`
- size: `36`
- prototype: `__int64 __fastcall(__int64, DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000d0f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d0fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d0fd`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper,winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics>::get_ProcessId(
        __int64 a1,
        DWORD *a2)
{
  *a2 = GetCurrentProcessId();
  return 0;
}

```

## disassembly

```asm
0x18000d0f0  mov     [rsp+arg_0], rcx
0x18000d0f5  push    rbx
0x18000d0f6  sub     rsp, 20h
0x18000d0fa  mov     rbx, rdx
0x18000d0fd  call    cs:__imp_GetCurrentProcessId
0x18000d103  mov     [rbx], eax
0x18000d105  xor     eax, eax
0x18000d107  jmp     short loc_18000D10D
0x18000d109  mov     eax, dword ptr [rsp+28h+arg_0]
0x18000d10d  add     rsp, 20h
0x18000d111  pop     rbx
0x18000d112  retn
```
