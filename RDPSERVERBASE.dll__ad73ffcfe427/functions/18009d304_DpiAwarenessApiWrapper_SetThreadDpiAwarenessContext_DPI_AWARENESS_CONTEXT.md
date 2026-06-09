# DpiAwarenessApiWrapper::SetThreadDpiAwarenessContext(DPI_AWARENESS_CONTEXT__ *)

- ea: `0x18009d304`
- end: `0x18009d35d`
- name: `?SetThreadDpiAwarenessContext@DpiAwarenessApiWrapper@@SAPEAUDPI_AWARENESS_CONTEXT__@@PEAU2@@Z`
- size: `89`
- prototype: `struct DPI_AWARENESS_CONTEXT__ *__fastcall(struct DPI_AWARENESS_CONTEXT__ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18009f840`

## callees

- `0x18009d304`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009d32f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009d32f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009d349`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009d349`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009d317`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009d317`

## string_xrefs

- `0x18009d30e`: `ext-ms-win-rtcore-ntuser-dpi-l1-2-0.dll`
- `0x18009d325`: `SetThreadDpiAwarenessContext`

## pseudocode

```c
struct DPI_AWARENESS_CONTEXT__ *__fastcall DpiAwarenessApiWrapper::SetThreadDpiAwarenessContext(
        struct DPI_AWARENESS_CONTEXT__ *a1)
{
  __int64 v1; // rdi
  HMODULE LibraryW; // rax
  HMODULE v3; // rbx
  FARPROC ProcAddress; // rax

  v1 = 0;
  LibraryW = LoadLibraryW(L"ext-ms-win-rtcore-ntuser-dpi-l1-2-0.dll");
  v3 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "SetThreadDpiAwarenessContext");
    if ( ProcAddress )
      v1 = ((__int64 (__fastcall *)(__int64))ProcAddress)(-3);
    FreeLibrary(v3);
  }
  return (struct DPI_AWARENESS_CONTEXT__ *)v1;
}

```

## disassembly

```asm
0x18009d304  mov     [rsp+arg_0], rbx
0x18009d309  push    rdi
0x18009d30a  sub     rsp, 20h
0x18009d30e  lea     rcx, aExtMsWinRtcore; "ext-ms-win-rtcore-ntuser-dpi-l1-2-0.dll"
0x18009d315  xor     edi, edi
0x18009d317  call    cs:__imp_LoadLibraryW
0x18009d31d  mov     rbx, rax
0x18009d320  test    rax, rax
0x18009d323  jz      short loc_18009D34F
0x18009d325  lea     rdx, aSetthreaddpiaw; "SetThreadDpiAwarenessContext"
0x18009d32c  mov     rcx, rax; hModule
0x18009d32f  call    cs:__imp_GetProcAddress
0x18009d335  test    rax, rax
0x18009d338  jz      short loc_18009D346
0x18009d33a  lea     rcx, [rdi-3]
0x18009d33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d343  mov     rdi, rax
0x18009d346  mov     rcx, rbx; hLibModule
0x18009d349  call    cs:__imp_FreeLibrary
0x18009d34f  mov     rbx, [rsp+28h+arg_0]
0x18009d354  mov     rax, rdi
0x18009d357  add     rsp, 20h
0x18009d35b  pop     rdi
0x18009d35c  retn
```
