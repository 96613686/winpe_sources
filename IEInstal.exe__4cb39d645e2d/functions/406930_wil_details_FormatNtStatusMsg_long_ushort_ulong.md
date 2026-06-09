# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x406930`
- end: `0x40696e`
- name: `?FormatNtStatusMsg@details@wil@@YGXJPAGK@Z`
- size: `62`
- prototype: `void __stdcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x406930`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x406964`
- `KERNEL32!FormatMessageW` at `0x406964`
- `KERNEL32!GetModuleHandleW` at `0x406943`
- `KERNEL32!GetModuleHandleW` at `0x406943`

## string_xrefs

- `0x40693e`: `ntdll.dll`

## pseudocode

```c
void __stdcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int a4)
{
  HMODULE ModuleHandleW; // eax

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
0x406930  mov     edi, edi
0x406932  push    ebp
0x406933  mov     ebp, esp
0x406935  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x40693a  test    eax, eax
0x40693c  jnz     short loc_40694E
0x40693e  push    offset aNtdllDll; "ntdll.dll"
0x406943  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x406949  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x40694e  push    0; Arguments
0x406950  push    [ebp+nSize]; nSize
0x406953  push    [ebp+lpBuffer]; lpBuffer
0x406956  push    400h; dwLanguageId
0x40695b  push    [ebp+dwMessageId]; dwMessageId
0x40695e  push    eax; lpSource
0x40695f  push    1A00h; dwFlags
0x406964  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x40696a  pop     ebp
0x40696b  retn    0Ch
```
