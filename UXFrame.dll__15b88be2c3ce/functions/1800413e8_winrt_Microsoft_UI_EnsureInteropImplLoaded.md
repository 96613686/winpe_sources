# winrt::Microsoft::UI::EnsureInteropImplLoaded

- ea: `0x1800413e8`
- end: `0x18004154d`
- name: `winrt::Microsoft::UI::EnsureInteropImplLoaded`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043d40`
- `0x180043dbc`

## callees

- `0x18003bfac`
- `0x1800413e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041439`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041450`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041467`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004147e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041495`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800414ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041439`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041450`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041467`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004147e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041495`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800414ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041408`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041408`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004141d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004141d`

## string_xrefs

- `0x180041401`: `Microsoft.Internal.FrameworkUdk.dll`
- `0x180041416`: `Microsoft.Internal.FrameworkUdk.dll`

## pseudocode

```c
__int64 winrt::Microsoft::UI::EnsureInteropImplLoaded()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rax
  __int64 v2; // rcx
  int v4; // [rsp+20h] [rbp-28h] BYREF
  __int128 v5; // [rsp+28h] [rbp-20h]

  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&winrt::Microsoft::UI::s_module, 0, 0) )
  {
    ModuleHandleW = GetModuleHandleW(L"Microsoft.Internal.FrameworkUdk.dll");
    if ( ModuleHandleW || (ModuleHandleW = LoadLibraryW(L"Microsoft.Internal.FrameworkUdk.dll")) != 0 )
    {
      winrt::Microsoft::UI::s_impl = GetProcAddress(ModuleHandleW, "Windowing_GetWindowIdFromWindow");
      qword_180072F10 = (__int64)GetProcAddress(ModuleHandleW, "Windowing_GetWindowFromWindowId");
      qword_180072F18 = (__int64)GetProcAddress(ModuleHandleW, "Windowing_GetDisplayIdFromMonitor");
      qword_180072F20 = (__int64)GetProcAddress(ModuleHandleW, "Windowing_GetMonitorFromDisplayId");
      qword_180072F28 = (__int64)GetProcAddress(ModuleHandleW, "Windowing_GetIconIdFromIcon");
      ProcAddress = GetProcAddress(ModuleHandleW, "Windowing_GetIconFromIconId");
      v5 = 0;
      qword_180072F30 = (__int64)ProcAddress;
      v4 = 0;
      if ( winrt::Microsoft::UI::s_impl
        && qword_180072F10
        && qword_180072F18
        && qword_180072F20
        && qword_180072F28
        && ProcAddress )
      {
        LOBYTE(v2) = 1;
      }
      else
      {
        v2 = 0;
      }
      winrt::check_bool<bool>(v2, &v4);
      _InterlockedCompareExchange64(
        (volatile signed __int64 *)&winrt::Microsoft::UI::s_module,
        (signed __int64)ModuleHandleW,
        0);
    }
  }
  v4 = 0;
  v5 = 0;
  return winrt::check_bool<bool>(
           _InterlockedCompareExchange64((volatile signed __int64 *)&winrt::Microsoft::UI::s_module, 0, 0) != 0,
           &v4);
}

```

## disassembly

```asm
0x1800413e8  push    rbx
0x1800413ea  sub     rsp, 40h
0x1800413ee  xor     ecx, ecx
0x1800413f0  xor     eax, eax
0x1800413f2  lock cmpxchg cs:?s_module@UI@Microsoft@winrt@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * winrt::Microsoft::UI::s_module
0x1800413fb  jnz     loc_18004151C
0x180041401  lea     rcx, aMicrosoftInter; "Microsoft.Internal.FrameworkUdk.dll"
0x180041408  call    cs:__imp_GetModuleHandleW
0x18004140e  mov     rbx, rax
0x180041411  test    rax, rax
0x180041414  jnz     short loc_18004142F
0x180041416  lea     rcx, aMicrosoftInter; "Microsoft.Internal.FrameworkUdk.dll"
0x18004141d  call    cs:__imp_LoadLibraryW
0x180041423  mov     rbx, rax
0x180041426  test    rax, rax
0x180041429  jz      loc_18004151C
0x18004142f  lea     rdx, aWindowingGetwi_0; "Windowing_GetWindowIdFromWindow"
0x180041436  mov     rcx, rbx; hModule
0x180041439  call    cs:__imp_GetProcAddress
0x18004143f  lea     rdx, aWindowingGetwi; "Windowing_GetWindowFromWindowId"
0x180041446  mov     rcx, rbx; hModule
0x180041449  mov     cs:?s_impl@UI@Microsoft@winrt@@3U_InteropImpl@123@A, rax; winrt::Microsoft::UI::_InteropImpl winrt::Microsoft::UI::s_impl
0x180041450  call    cs:__imp_GetProcAddress
0x180041456  lea     rdx, aWindowingGetdi; "Windowing_GetDisplayIdFromMonitor"
0x18004145d  mov     rcx, rbx; hModule
0x180041460  mov     cs:qword_180072F10, rax
0x180041467  call    cs:__imp_GetProcAddress
0x18004146d  lea     rdx, aWindowingGetmo; "Windowing_GetMonitorFromDisplayId"
0x180041474  mov     rcx, rbx; hModule
0x180041477  mov     cs:qword_180072F18, rax
0x18004147e  call    cs:__imp_GetProcAddress
0x180041484  lea     rdx, aWindowingGetic; "Windowing_GetIconIdFromIcon"
0x18004148b  mov     rcx, rbx; hModule
0x18004148e  mov     cs:qword_180072F20, rax
0x180041495  call    cs:__imp_GetProcAddress
0x18004149b  lea     rdx, aWindowingGetic_0; "Windowing_GetIconFromIconId"
0x1800414a2  mov     rcx, rbx; hModule
0x1800414a5  mov     cs:qword_180072F28, rax
0x1800414ac  call    cs:__imp_GetProcAddress
0x1800414b2  cmp     cs:?s_impl@UI@Microsoft@winrt@@3U_InteropImpl@123@A, 0; winrt::Microsoft::UI::_InteropImpl winrt::Microsoft::UI::s_impl
0x1800414ba  xorps   xmm0, xmm0
0x1800414bd  movdqu  [rsp+48h+var_20], xmm0
0x1800414c3  mov     cs:qword_180072F30, rax
0x1800414ca  mov     [rsp+48h+var_28], 0
0x1800414d2  jz      short loc_180041505
0x1800414d4  cmp     cs:qword_180072F10, 0
0x1800414dc  jz      short loc_180041505
0x1800414de  cmp     cs:qword_180072F18, 0
0x1800414e6  jz      short loc_180041505
0x1800414e8  cmp     cs:qword_180072F20, 0
0x1800414f0  jz      short loc_180041505
0x1800414f2  cmp     cs:qword_180072F28, 0
0x1800414fa  jz      short loc_180041505
0x1800414fc  test    rax, rax
0x1800414ff  jz      short loc_180041505
0x180041501  mov     cl, 1
0x180041503  jmp     short loc_180041507
0x180041505  xor     ecx, ecx
0x180041507  lea     rdx, [rsp+48h+var_28]
0x18004150c  call    ??$check_bool@_N@winrt@@YA_N_NAEBUslim_source_location@impl@0@@Z; winrt::check_bool<bool>(bool,winrt::impl::slim_source_location const &)
0x180041511  xor     eax, eax
0x180041513  lock cmpxchg cs:?s_module@UI@Microsoft@winrt@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * winrt::Microsoft::UI::s_module
0x18004151c  xorps   xmm0, xmm0
0x18004151f  mov     [rsp+48h+var_28], 0
0x180041527  xor     ecx, ecx
0x180041529  movdqu  [rsp+48h+var_20], xmm0
0x18004152f  xor     eax, eax
0x180041531  lock cmpxchg cs:?s_module@UI@Microsoft@winrt@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * winrt::Microsoft::UI::s_module
0x18004153a  setnz   cl
0x18004153d  lea     rdx, [rsp+48h+var_28]
0x180041542  call    ??$check_bool@_N@winrt@@YA_N_NAEBUslim_source_location@impl@0@@Z; winrt::check_bool<bool>(bool,winrt::impl::slim_source_location const &)
0x180041547  add     rsp, 40h
0x18004154b  pop     rbx
0x18004154c  retn
```
