# DllRegisterServer

- ea: `0x18006c880`
- end: `0x18006c8b9`
- name: `DllRegisterServer`
- size: `57`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18006c3b0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18006c897`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18006c8a6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18006c897`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18006c8a6`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18006c88a`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18006c88a`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // edi
  HRESULT v1; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = ATL::CAtlModuleT<Windows::Globalization::Spelling::CSpellCheckModule>::RegisterServer();
  SetThreadLocale(ThreadLocale);
  return v1;
}

```

## disassembly

```asm
0x18006c880  mov     [rsp+arg_0], rbx
0x18006c885  push    rdi
0x18006c886  sub     rsp, 20h
0x18006c88a  call    cs:__imp_GetThreadLocale
0x18006c890  mov     ecx, 800h; Locale
0x18006c895  mov     edi, eax
0x18006c897  call    cs:__imp_SetThreadLocale
0x18006c89d  call    ?RegisterServer@?$CAtlModuleT@VCSpellCheckModule@Spelling@Globalization@Windows@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<Windows::Globalization::Spelling::CSpellCheckModule>::RegisterServer(int,_GUID const *)
0x18006c8a2  mov     ecx, edi; Locale
0x18006c8a4  mov     ebx, eax
0x18006c8a6  call    cs:__imp_SetThreadLocale
0x18006c8ac  mov     eax, ebx
0x18006c8ae  mov     rbx, [rsp+28h+arg_0]
0x18006c8b3  add     rsp, 20h
0x18006c8b7  pop     rdi
0x18006c8b8  retn
```
