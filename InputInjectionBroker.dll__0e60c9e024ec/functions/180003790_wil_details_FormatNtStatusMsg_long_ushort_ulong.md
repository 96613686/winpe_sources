# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003790`
- end: `0x180003800`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003790`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800037ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800037ba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800037ea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800037ea`

## string_xrefs

- `0x1800037b3`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  FormatMessageW(0x1A00u, ModuleHandleW, dwMessageId, 0x400u, lpBuffer, nSize, 0);
}

```

## disassembly

```asm
0x180003790  mov     [rsp+arg_0], rbx
0x180003795  mov     [rsp+arg_8], rsi
0x18000379a  push    rdi
0x18000379b  sub     rsp, 40h
0x18000379f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800037a6  mov     ebx, r8d
0x1800037a9  mov     rdi, rdx
0x1800037ac  mov     esi, ecx
0x1800037ae  test    rax, rax
0x1800037b1  jnz     short loc_1800037C7
0x1800037b3  lea     rcx, ModuleName; "ntdll.dll"
0x1800037ba  call    cs:__imp_GetModuleHandleW
0x1800037c0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800037c7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800037d0  mov     r9d, 400h; dwLanguageId
0x1800037d6  mov     [rsp+48h+nSize], ebx; nSize
0x1800037da  mov     r8d, esi; dwMessageId
0x1800037dd  mov     rdx, rax; lpSource
0x1800037e0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800037e5  mov     ecx, 1A00h; dwFlags
0x1800037ea  call    cs:__imp_FormatMessageW
0x1800037f0  mov     rbx, [rsp+48h+arg_0]
0x1800037f5  mov     rsi, [rsp+48h+arg_8]
0x1800037fa  add     rsp, 40h
0x1800037fe  pop     rdi
0x1800037ff  retn
```
