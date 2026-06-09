# IsResetDevicePresent(void)

- ea: `0x18003d1f0`
- end: `0x18003d2ce`
- name: `?IsResetDevicePresent@@YAHXZ`
- size: `222`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180022f7c`

## callees

- `0x18002c640`
- `0x18003d148`
- `0x18003d1f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d28c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d28c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003d21f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003d21f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003d267`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003d267`
- `api-ms-win-core-libraryloader-l2-1-0!QueryOptionalDelayLoadedAPI` at `0x18003d249`
- `api-ms-win-core-libraryloader-l2-1-0!QueryOptionalDelayLoadedAPI` at `0x18003d249`

## string_xrefs

- `0x18003d242`: `UpdateAPI.dll`
- `0x18003d260`: `UpdateAPI.dll`

## pseudocode

```c
_BOOL8 IsResetDevicePresent(void)
{
  HMODULE LibraryW; // rax
  BOOL v2; // ebx
  HMODULE v3; // [rsp+20h] [rbp-28h] BYREF
  HMODULE phModule; // [rsp+28h] [rbp-20h] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(6u, (LPCWSTR)IsResetDevicePresent, &phModule) )
  {
    if ( (unsigned int)QueryOptionalDelayLoadedAPI(phModule, "UpdateAPI.dll", "ResetDevice", 0) )
      return 1;
    LibraryW = LoadLibraryW(L"UpdateAPI.dll");
    v3 = LibraryW;
    if ( (unsigned __int64)LibraryW - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v2 = GetProcAddress(LibraryW, "ResetDevice") != 0;
      `IsResetDevicePresent'::`2'::AutoHDll::~AutoHDll(&v3);
      return v2;
    }
    `IsResetDevicePresent'::`2'::AutoHDll::~AutoHDll(&v3);
  }
  return 0;
}

```

## disassembly

```asm
0x18003d1f0  push    rbx
0x18003d1f2  sub     rsp, 40h
0x18003d1f6  mov     rax, cs:__security_cookie
0x18003d1fd  xor     rax, rsp
0x18003d200  mov     [rsp+48h+var_18], rax
0x18003d205  lea     r8, [rsp+48h+phModule]; phModule
0x18003d20a  mov     [rsp+48h+phModule], 0
0x18003d213  lea     rdx, ?IsResetDevicePresent@@YAHXZ; lpModuleName
0x18003d21a  mov     ecx, 6; dwFlags
0x18003d21f  call    cs:__imp_GetModuleHandleExW
0x18003d226  nop     dword ptr [rax+rax+00h]
0x18003d22b  test    eax, eax
0x18003d22d  jz      loc_18003D2B8
0x18003d233  mov     rcx, [rsp+48h+phModule]
0x18003d238  lea     r8, aResetdevice_0; "ResetDevice"
0x18003d23f  xor     r9d, r9d
0x18003d242  lea     rdx, aUpdateapiDll_1; "UpdateAPI.dll"
0x18003d249  call    cs:__imp_QueryOptionalDelayLoadedAPI
0x18003d250  nop     dword ptr [rax+rax+00h]
0x18003d255  test    eax, eax
0x18003d257  jz      short loc_18003D260
0x18003d259  mov     eax, 1
0x18003d25e  jmp     short loc_18003D2BA
0x18003d260  lea     rcx, LibFileName; "UpdateAPI.dll"
0x18003d267  call    cs:__imp_LoadLibraryW
0x18003d26e  nop     dword ptr [rax+rax+00h]
0x18003d273  mov     [rsp+48h+var_28], rax
0x18003d278  lea     rcx, [rax-1]
0x18003d27c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003d280  ja      short loc_18003D2AE
0x18003d282  lea     rdx, aResetdevice_0; "ResetDevice"
0x18003d289  mov     rcx, rax; hModule
0x18003d28c  call    cs:__imp_GetProcAddress
0x18003d293  nop     dword ptr [rax+rax+00h]
0x18003d298  xor     ebx, ebx
0x18003d29a  lea     rcx, [rsp+48h+var_28]
0x18003d29f  test    rax, rax
0x18003d2a2  setnz   bl
0x18003d2a5  call    ??1AutoHDll@?1??IsResetDevicePresent@@YAHXZ@QEAA@XZ; `IsResetDevicePresent(void)'::`2'::AutoHDll::~AutoHDll(void)
0x18003d2aa  mov     eax, ebx
0x18003d2ac  jmp     short loc_18003D2BA
0x18003d2ae  lea     rcx, [rsp+48h+var_28]
0x18003d2b3  call    ??1AutoHDll@?1??IsResetDevicePresent@@YAHXZ@QEAA@XZ; `IsResetDevicePresent(void)'::`2'::AutoHDll::~AutoHDll(void)
0x18003d2b8  xor     eax, eax
0x18003d2ba  mov     rcx, [rsp+48h+var_18]
0x18003d2bf  xor     rcx, rsp; StackCookie
0x18003d2c2  call    __security_check_cookie
0x18003d2c7  add     rsp, 40h
0x18003d2cb  pop     rbx
0x18003d2cc  retn
```
