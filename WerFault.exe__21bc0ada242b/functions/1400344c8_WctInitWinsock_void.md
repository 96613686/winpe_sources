# WctInitWinsock(void)

- ea: `0x1400344c8`
- end: `0x140034642`
- name: `?WctInitWinsock@@YAHXZ`
- size: `378`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140034648`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x1400344c8`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003461a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003461a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140034530`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140034554`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140034578`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140034598`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400345b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400345d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140034530`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140034554`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140034578`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140034598`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400345b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400345d8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140034510`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140034510`

## string_xrefs

- `0x140034509`: `ws2_32.dll`
- `0x1400345b1`: `WSACleanup`

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
0x1400344c8  push    rbx
0x1400344ca  sub     rsp, 1D0h
0x1400344d1  mov     rax, cs:__security_cookie
0x1400344d8  xor     rax, rsp
0x1400344db  mov     [rsp+1D8h+var_18], rax
0x1400344e3  xor     edx, edx; Val
0x1400344e5  lea     rcx, [rsp+1D8h+var_1B8]; void *
0x1400344ea  mov     r8d, 198h; Size
0x1400344f0  call    memset_0
0x1400344f5  cmp     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_ws2_32
0x1400344fd  jz      short loc_140034509
0x1400344ff  mov     eax, 1
0x140034504  jmp     loc_140034629
0x140034509  lea     rcx, aWs232Dll; "ws2_32.dll"
0x140034510  call    cs:__imp_LoadLibraryW
0x140034516  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_ws2_32
0x14003451d  test    rax, rax
0x140034520  jz      loc_140034610
0x140034526  lea     rdx, aWsastartup; "WSAStartup"
0x14003452d  mov     rcx, rax; hModule
0x140034530  call    cs:__imp_GetProcAddress
0x140034536  mov     cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA, rax; int (*g_WSAStartup)(ushort,WSAData *)
0x14003453d  test    rax, rax
0x140034540  jz      loc_140034609
0x140034546  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x14003454d  lea     rdx, aGetsockopt; "getsockopt"
0x140034554  call    cs:__imp_GetProcAddress
0x14003455a  mov     cs:?g_getsockopt@@3P6AH_KHHPEADPEAH@ZEA, rax; int (*g_getsockopt)(unsigned __int64,int,int,char *,int *)
0x140034561  test    rax, rax
0x140034564  jz      loc_140034609
0x14003456a  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x140034571  lea     rdx, aGetsockname; "getsockname"
0x140034578  call    cs:__imp_GetProcAddress
0x14003457e  mov     cs:?g_getsockname@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getsockname)(unsigned __int64,sockaddr *,int *)
0x140034585  test    rax, rax
0x140034588  jz      short loc_140034609
0x14003458a  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x140034591  lea     rdx, aGetpeername; "getpeername"
0x140034598  call    cs:__imp_GetProcAddress
0x14003459e  mov     cs:?g_getpeername@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getpeername)(unsigned __int64,sockaddr *,int *)
0x1400345a5  test    rax, rax
0x1400345a8  jz      short loc_140034609
0x1400345aa  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x1400345b1  lea     rdx, aWsacleanup; "WSACleanup"
0x1400345b8  call    cs:__imp_GetProcAddress
0x1400345be  mov     cs:?g_WSACleanup@@3P6AHXZEA, rax; int (*g_WSACleanup)(void)
0x1400345c5  test    rax, rax
0x1400345c8  jz      short loc_140034609
0x1400345ca  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x1400345d1  lea     rdx, aClosesocket; "closesocket"
0x1400345d8  call    cs:__imp_GetProcAddress
0x1400345de  mov     cs:?g_closesocket@@3P6AH_K@ZEA, rax; int (*g_closesocket)(unsigned __int64)
0x1400345e5  test    rax, rax
0x1400345e8  jz      short loc_140034609
0x1400345ea  mov     rax, cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA; int (*g_WSAStartup)(ushort,WSAData *)
0x1400345f1  lea     rdx, [rsp+1D8h+var_1B8]
0x1400345f6  mov     ecx, 202h
0x1400345fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034600  test    eax, eax
0x140034602  jnz     short loc_140034609
0x140034604  lea     ebx, [rax+1]
0x140034607  jmp     short loc_140034627
0x140034609  mov     rax, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_ws2_32
0x140034610  xor     ebx, ebx
0x140034612  test    rax, rax
0x140034615  jz      short loc_140034627
0x140034617  mov     rcx, rax; hLibModule
0x14003461a  call    cs:__imp_FreeLibrary
0x140034620  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_ws2_32
0x140034627  mov     eax, ebx
0x140034629  mov     rcx, [rsp+1D8h+var_18]
0x140034631  xor     rcx, rsp; StackCookie
0x140034634  call    __security_check_cookie
0x140034639  add     rsp, 1D0h
0x140034640  pop     rbx
0x140034641  retn
```
