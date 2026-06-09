# WctInitWinsock(void)

- ea: `0x140036970`
- end: `0x140036b1f`
- name: `?WctInitWinsock@@YAHXZ`
- size: `431`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140036b28`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140036970`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140036af0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140036af0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400369de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036a08`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036a32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036a5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036a82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036aa8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400369de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036a08`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036a32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036a5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036a82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036aa8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400369b8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400369b8`

## string_xrefs

- `0x1400369b1`: `ws2_32.dll`
- `0x140036a7b`: `WSACleanup`

## pseudocode

```c
__int64 WctInitWinsock(void)
{
  HMODULE LibraryW; // rax
  unsigned int v2; // ebx
  _BYTE v3[416]; // [rsp+20h] [rbp-1B8h] BYREF

  memset_0(v3, 0, 0x198u);
  if ( g_ws2_32 )
    return 1;
  LibraryW = LoadLibraryW(L"ws2_32.dll");
  g_ws2_32 = LibraryW;
  if ( !LibraryW )
    goto LABEL_13;
  g_WSAStartup = (int (*)(unsigned __int16, struct WSAData *))GetProcAddress(LibraryW, "WSAStartup");
  if ( !g_WSAStartup
    || (g_getsockopt = (int (*)(unsigned __int64, int, int, char *, int *))GetProcAddress(g_ws2_32, "getsockopt")) == 0
    || (g_getsockname = (int (*)(unsigned __int64, struct sockaddr *, int *))GetProcAddress(g_ws2_32, "getsockname")) == 0
    || (g_getpeername = (int (*)(unsigned __int64, struct sockaddr *, int *))GetProcAddress(g_ws2_32, "getpeername")) == 0
    || (g_WSACleanup = (int (*)(void))GetProcAddress(g_ws2_32, "WSACleanup")) == 0
    || (g_closesocket = (int (*)(unsigned __int64))GetProcAddress(g_ws2_32, "closesocket")) == 0
    || (unsigned int)((__int64 (__fastcall *)(__int64, _BYTE *))g_WSAStartup)(514, v3) )
  {
    LibraryW = g_ws2_32;
LABEL_13:
    v2 = 0;
    if ( LibraryW )
    {
      FreeLibrary(LibraryW);
      g_ws2_32 = 0;
    }
    return v2;
  }
  return 1;
}

```

## disassembly

```asm
0x140036970  push    rbx
0x140036972  sub     rsp, 1D0h
0x140036979  mov     rax, cs:__security_cookie
0x140036980  xor     rax, rsp
0x140036983  mov     [rsp+1D8h+var_18], rax
0x14003698b  xor     edx, edx; Val
0x14003698d  lea     rcx, [rsp+1D8h+var_1B8]; void *
0x140036992  mov     r8d, 198h; Size
0x140036998  call    memset_0
0x14003699d  cmp     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_ws2_32
0x1400369a5  jz      short loc_1400369B1
0x1400369a7  mov     eax, 1
0x1400369ac  jmp     loc_140036B05
0x1400369b1  lea     rcx, aWs232Dll; "ws2_32.dll"
0x1400369b8  call    cs:__imp_LoadLibraryW
0x1400369bf  nop     dword ptr [rax+rax+00h]
0x1400369c4  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_ws2_32
0x1400369cb  test    rax, rax
0x1400369ce  jz      loc_140036AE6
0x1400369d4  lea     rdx, aWsastartup; "WSAStartup"
0x1400369db  mov     rcx, rax; hModule
0x1400369de  call    cs:__imp_GetProcAddress
0x1400369e5  nop     dword ptr [rax+rax+00h]
0x1400369ea  mov     cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA, rax; int (*g_WSAStartup)(ushort,WSAData *)
0x1400369f1  test    rax, rax
0x1400369f4  jz      loc_140036ADF
0x1400369fa  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x140036a01  lea     rdx, aGetsockopt; "getsockopt"
0x140036a08  call    cs:__imp_GetProcAddress
0x140036a0f  nop     dword ptr [rax+rax+00h]
0x140036a14  mov     cs:?g_getsockopt@@3P6AH_KHHPEADPEAH@ZEA, rax; int (*g_getsockopt)(unsigned __int64,int,int,char *,int *)
0x140036a1b  test    rax, rax
0x140036a1e  jz      loc_140036ADF
0x140036a24  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x140036a2b  lea     rdx, aGetsockname; "getsockname"
0x140036a32  call    cs:__imp_GetProcAddress
0x140036a39  nop     dword ptr [rax+rax+00h]
0x140036a3e  mov     cs:?g_getsockname@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getsockname)(unsigned __int64,sockaddr *,int *)
0x140036a45  test    rax, rax
0x140036a48  jz      loc_140036ADF
0x140036a4e  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x140036a55  lea     rdx, aGetpeername; "getpeername"
0x140036a5c  call    cs:__imp_GetProcAddress
0x140036a63  nop     dword ptr [rax+rax+00h]
0x140036a68  mov     cs:?g_getpeername@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getpeername)(unsigned __int64,sockaddr *,int *)
0x140036a6f  test    rax, rax
0x140036a72  jz      short loc_140036ADF
0x140036a74  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x140036a7b  lea     rdx, aWsacleanup; "WSACleanup"
0x140036a82  call    cs:__imp_GetProcAddress
0x140036a89  nop     dword ptr [rax+rax+00h]
0x140036a8e  mov     cs:?g_WSACleanup@@3P6AHXZEA, rax; int (*g_WSACleanup)(void)
0x140036a95  test    rax, rax
0x140036a98  jz      short loc_140036ADF
0x140036a9a  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x140036aa1  lea     rdx, aClosesocket; "closesocket"
0x140036aa8  call    cs:__imp_GetProcAddress
0x140036aaf  nop     dword ptr [rax+rax+00h]
0x140036ab4  mov     cs:?g_closesocket@@3P6AH_K@ZEA, rax; int (*g_closesocket)(unsigned __int64)
0x140036abb  test    rax, rax
0x140036abe  jz      short loc_140036ADF
0x140036ac0  mov     rax, cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA; int (*g_WSAStartup)(ushort,WSAData *)
0x140036ac7  lea     rdx, [rsp+1D8h+var_1B8]
0x140036acc  mov     ecx, 202h
0x140036ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036ad6  test    eax, eax
0x140036ad8  jnz     short loc_140036ADF
0x140036ada  lea     ebx, [rax+1]
0x140036add  jmp     short loc_140036B03
0x140036adf  mov     rax, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_ws2_32
0x140036ae6  xor     ebx, ebx
0x140036ae8  test    rax, rax
0x140036aeb  jz      short loc_140036B03
0x140036aed  mov     rcx, rax; hLibModule
0x140036af0  call    cs:__imp_FreeLibrary
0x140036af7  nop     dword ptr [rax+rax+00h]
0x140036afc  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_ws2_32
0x140036b03  mov     eax, ebx
0x140036b05  mov     rcx, [rsp+1D8h+var_18]
0x140036b0d  xor     rcx, rsp; StackCookie
0x140036b10  call    __security_check_cookie
0x140036b15  add     rsp, 1D0h
0x140036b1c  pop     rbx
0x140036b1d  retn
```
