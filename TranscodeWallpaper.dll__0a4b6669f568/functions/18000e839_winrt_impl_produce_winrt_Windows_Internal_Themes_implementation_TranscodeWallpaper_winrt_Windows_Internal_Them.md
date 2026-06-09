# _winrt::impl::produce_winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper_winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics_::get_ProcessId_::_1_::catch$0

- ea: `0x18000e839`
- end: `0x18000e865`
- name: `_winrt::impl::produce_winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper_winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics_::get_ProcessId_::_1_::catch$0`
- size: `44`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000d4ac`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper_winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics_::get_ProcessId_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 48) = *winrt::to_hresult((_DWORD *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x18000e839  mov     [rsp+arg_8], rdx
0x18000e83e  push    rbp
0x18000e83f  sub     rsp, 20h
0x18000e843  mov     rbp, rdx
0x18000e846  lea     rcx, [rbp+30h]
0x18000e84a  call    ?to_hresult@winrt@@YA?AUhresult@1@XZ; winrt::to_hresult(void)
0x18000e84f  mov     ecx, [rax]
0x18000e851  mov     [rbp+30h], ecx
0x18000e854  mov     rax, 0
0x18000e85e  add     rsp, 20h
0x18000e862  pop     rbp
0x18000e863  retn
```
