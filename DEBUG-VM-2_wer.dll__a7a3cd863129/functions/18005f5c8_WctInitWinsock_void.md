# WctInitWinsock(void)

- ea: `0x18005f5c8`
- end: `0x18005f742`
- name: `?WctInitWinsock@@YAHXZ`
- size: `378`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005f748`

## callees

- `0x180050db0`
- `0x1800517cc`
- `0x18005f5c8`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f630`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f654`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f678`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f698`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f630`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f654`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f678`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f698`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6d8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005f71a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005f71a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005f610`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005f610`

## string_xrefs

- `0x18005f609`: `ws2_32.dll`
- `0x18005f6b1`: `WSACleanup`

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
0x18005f5c8  push    rbx
0x18005f5ca  sub     rsp, 1D0h
0x18005f5d1  mov     rax, cs:__security_cookie
0x18005f5d8  xor     rax, rsp
0x18005f5db  mov     [rsp+1D8h+var_18], rax
0x18005f5e3  xor     edx, edx; Val
0x18005f5e5  lea     rcx, [rsp+1D8h+var_1B8]; void *
0x18005f5ea  mov     r8d, 198h; Size
0x18005f5f0  call    memset_0
0x18005f5f5  cmp     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_ws2_32
0x18005f5fd  jz      short loc_18005F609
0x18005f5ff  mov     eax, 1
0x18005f604  jmp     loc_18005F729
0x18005f609  lea     rcx, aWs232Dll; "ws2_32.dll"
0x18005f610  call    cs:__imp_LoadLibraryW
0x18005f616  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_ws2_32
0x18005f61d  test    rax, rax
0x18005f620  jz      loc_18005F710
0x18005f626  lea     rdx, aWsastartup; "WSAStartup"
0x18005f62d  mov     rcx, rax; hModule
0x18005f630  call    cs:__imp_GetProcAddress
0x18005f636  mov     cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA, rax; int (*g_WSAStartup)(ushort,WSAData *)
0x18005f63d  test    rax, rax
0x18005f640  jz      loc_18005F709
0x18005f646  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18005f64d  lea     rdx, aGetsockopt; "getsockopt"
0x18005f654  call    cs:__imp_GetProcAddress
0x18005f65a  mov     cs:?g_getsockopt@@3P6AH_KHHPEADPEAH@ZEA, rax; int (*g_getsockopt)(unsigned __int64,int,int,char *,int *)
0x18005f661  test    rax, rax
0x18005f664  jz      loc_18005F709
0x18005f66a  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18005f671  lea     rdx, aGetsockname; "getsockname"
0x18005f678  call    cs:__imp_GetProcAddress
0x18005f67e  mov     cs:?g_getsockname@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getsockname)(unsigned __int64,sockaddr *,int *)
0x18005f685  test    rax, rax
0x18005f688  jz      short loc_18005F709
0x18005f68a  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18005f691  lea     rdx, aGetpeername; "getpeername"
0x18005f698  call    cs:__imp_GetProcAddress
0x18005f69e  mov     cs:?g_getpeername@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getpeername)(unsigned __int64,sockaddr *,int *)
0x18005f6a5  test    rax, rax
0x18005f6a8  jz      short loc_18005F709
0x18005f6aa  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18005f6b1  lea     rdx, aWsacleanup; "WSACleanup"
0x18005f6b8  call    cs:__imp_GetProcAddress
0x18005f6be  mov     cs:?g_WSACleanup@@3P6AHXZEA, rax; int (*g_WSACleanup)(void)
0x18005f6c5  test    rax, rax
0x18005f6c8  jz      short loc_18005F709
0x18005f6ca  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18005f6d1  lea     rdx, aClosesocket; "closesocket"
0x18005f6d8  call    cs:__imp_GetProcAddress
0x18005f6de  mov     cs:?g_closesocket@@3P6AH_K@ZEA, rax; int (*g_closesocket)(unsigned __int64)
0x18005f6e5  test    rax, rax
0x18005f6e8  jz      short loc_18005F709
0x18005f6ea  mov     rax, cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA; int (*g_WSAStartup)(ushort,WSAData *)
0x18005f6f1  lea     rdx, [rsp+1D8h+var_1B8]
0x18005f6f6  mov     ecx, 202h
0x18005f6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f700  test    eax, eax
0x18005f702  jnz     short loc_18005F709
0x18005f704  lea     ebx, [rax+1]
0x18005f707  jmp     short loc_18005F727
0x18005f709  mov     rax, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_ws2_32
0x18005f710  xor     ebx, ebx
0x18005f712  test    rax, rax
0x18005f715  jz      short loc_18005F727
0x18005f717  mov     rcx, rax; hLibModule
0x18005f71a  call    cs:__imp_FreeLibrary
0x18005f720  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_ws2_32
0x18005f727  mov     eax, ebx
0x18005f729  mov     rcx, [rsp+1D8h+var_18]
0x18005f731  xor     rcx, rsp; StackCookie
0x18005f734  call    __security_check_cookie
0x18005f739  add     rsp, 1D0h
0x18005f740  pop     rbx
0x18005f741  retn
```
