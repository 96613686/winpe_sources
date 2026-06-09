# DllMain

- ea: `0x180006b5c`
- end: `0x180006c19`
- name: `DllMain`
- size: `189`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180005974`

## callees

- `0x180001008`
- `0x180006b5c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180006be9`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180006c0b`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180006be9`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180006c0b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006bc7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006bc7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180006b7b`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180006b7b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006b8e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006b8e`

## string_xrefs

- `0x180006b83`: `PhoneServiceRes.dll`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // ebx
  REGHANDLE v4; // rcx
  REGHANDLE v5; // rcx

  v3 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      g_hInstRes = LoadLibraryExW(L"PhoneServiceRes.dll", 0, 2u);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800B3200);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800B3238);
      return !ATL::CAtlBaseModule::m_bInitFailed;
    }
  }
  else
  {
    FreeLibrary(g_hInstRes);
    v4 = RegHandle;
    dword_1800B3200 = 0;
    RegHandle = 0;
    EventUnregister(v4);
    v5 = qword_1800B3258;
    dword_1800B3238 = 0;
    qword_1800B3258 = 0;
    EventUnregister(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180006b5c  push    rbx
0x180006b5e  sub     rsp, 20h
0x180006b62  mov     eax, edx
0x180006b64  mov     ebx, 1
0x180006b69  test    edx, edx
0x180006b6b  jz      short loc_180006BC0
0x180006b6d  cmp     eax, ebx
0x180006b6f  jz      short loc_180006B7B
0x180006b71  cmp     edx, ebx
0x180006b73  jnz     loc_180006C11
0x180006b79  jmp     short loc_180006BB3
0x180006b7b  call    cs:__imp_DisableThreadLibraryCalls
0x180006b81  xor     edx, edx; hFile
0x180006b83  lea     rcx, LibFileName; "PhoneServiceRes.dll"
0x180006b8a  lea     r8d, [rdx+2]; dwFlags
0x180006b8e  call    cs:__imp_LoadLibraryExW
0x180006b94  lea     rcx, dword_1800B3200; CallbackContext
0x180006b9b  mov     cs:?g_hInstRes@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRes
0x180006ba2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180006ba7  lea     rcx, dword_1800B3238; CallbackContext
0x180006bae  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180006bb3  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180006bba  jz      short loc_180006C11
0x180006bbc  xor     ebx, ebx
0x180006bbe  jmp     short loc_180006C11
0x180006bc0  mov     rcx, cs:?g_hInstRes@@3PEAUHINSTANCE__@@EA; hLibModule
0x180006bc7  call    cs:__imp_FreeLibrary
0x180006bcd  mov     rcx, cs:RegHandle; RegHandle
0x180006bd4  mov     cs:dword_1800B3200, 0
0x180006bde  mov     cs:RegHandle, 0
0x180006be9  call    cs:__imp_EventUnregister
0x180006bef  mov     rcx, cs:qword_1800B3258; RegHandle
0x180006bf6  mov     cs:dword_1800B3238, 0
0x180006c00  mov     cs:qword_1800B3258, 0
0x180006c0b  call    cs:__imp_EventUnregister
0x180006c11  mov     eax, ebx
0x180006c13  add     rsp, 20h
0x180006c17  pop     rbx
0x180006c18  retn
```
