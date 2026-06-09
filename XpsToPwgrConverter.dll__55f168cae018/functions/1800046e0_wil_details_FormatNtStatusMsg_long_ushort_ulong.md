# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800046e0`
- end: `0x180004750`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800046e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000470a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000470a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000473a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000473a`

## string_xrefs

- `0x180004703`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x1800046e0  mov     [rsp+arg_0], rbx
0x1800046e5  mov     [rsp+arg_8], rsi
0x1800046ea  push    rdi
0x1800046eb  sub     rsp, 40h
0x1800046ef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800046f6  mov     ebx, r8d
0x1800046f9  mov     rdi, rdx
0x1800046fc  mov     esi, ecx
0x1800046fe  test    rax, rax
0x180004701  jnz     short loc_180004717
0x180004703  lea     rcx, ModuleName; "ntdll.dll"
0x18000470a  call    cs:__imp_GetModuleHandleW
0x180004710  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004717  mov     [rsp+48h+Arguments], 0; Arguments
0x180004720  mov     r9d, 400h; dwLanguageId
0x180004726  mov     [rsp+48h+nSize], ebx; nSize
0x18000472a  mov     r8d, esi; dwMessageId
0x18000472d  mov     rdx, rax; lpSource
0x180004730  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004735  mov     ecx, 1A00h; dwFlags
0x18000473a  call    cs:__imp_FormatMessageW
0x180004740  mov     rbx, [rsp+48h+arg_0]
0x180004745  mov     rsi, [rsp+48h+arg_8]
0x18000474a  add     rsp, 40h
0x18000474e  pop     rdi
0x18000474f  retn
```
