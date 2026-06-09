# WctInitWinsock(void)

- ea: `0x18006cb98`
- end: `0x18006cd47`
- name: `?WctInitWinsock@@YAHXZ`
- size: `431`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006cd50`

## callees

- `0x18006cb98`
- `0x18007205a`
- `0x1800720b0`
- `0x180074010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18006cc06`
- `KERNEL32!GetProcAddress` at `0x18006cc30`
- `KERNEL32!GetProcAddress` at `0x18006cc5a`
- `KERNEL32!GetProcAddress` at `0x18006cc84`
- `KERNEL32!GetProcAddress` at `0x18006ccaa`
- `KERNEL32!GetProcAddress` at `0x18006ccd0`
- `KERNEL32!GetProcAddress` at `0x18006cc06`
- `KERNEL32!GetProcAddress` at `0x18006cc30`
- `KERNEL32!GetProcAddress` at `0x18006cc5a`
- `KERNEL32!GetProcAddress` at `0x18006cc84`
- `KERNEL32!GetProcAddress` at `0x18006ccaa`
- `KERNEL32!GetProcAddress` at `0x18006ccd0`
- `KERNEL32!FreeLibrary` at `0x18006cd18`
- `KERNEL32!FreeLibrary` at `0x18006cd18`
- `KERNEL32!LoadLibraryW` at `0x18006cbe0`
- `KERNEL32!LoadLibraryW` at `0x18006cbe0`

## string_xrefs

- `0x18006cbd9`: `ws2_32.dll`
- `0x18006cca3`: `WSACleanup`

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
0x18006cb98  push    rbx
0x18006cb9a  sub     rsp, 1D0h
0x18006cba1  mov     rax, cs:__security_cookie
0x18006cba8  xor     rax, rsp
0x18006cbab  mov     [rsp+1D8h+var_18], rax
0x18006cbb3  xor     edx, edx; Val
0x18006cbb5  lea     rcx, [rsp+1D8h+var_1B8]; void *
0x18006cbba  mov     r8d, 198h; Size
0x18006cbc0  call    memset_0
0x18006cbc5  cmp     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_ws2_32
0x18006cbcd  jz      short loc_18006CBD9
0x18006cbcf  mov     eax, 1
0x18006cbd4  jmp     loc_18006CD2D
0x18006cbd9  lea     rcx, aWs232Dll; "ws2_32.dll"
0x18006cbe0  call    cs:__imp_LoadLibraryW
0x18006cbe7  nop     dword ptr [rax+rax+00h]
0x18006cbec  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_ws2_32
0x18006cbf3  test    rax, rax
0x18006cbf6  jz      loc_18006CD0E
0x18006cbfc  lea     rdx, aWsastartup; "WSAStartup"
0x18006cc03  mov     rcx, rax; hModule
0x18006cc06  call    cs:__imp_GetProcAddress
0x18006cc0d  nop     dword ptr [rax+rax+00h]
0x18006cc12  mov     cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA, rax; int (*g_WSAStartup)(ushort,WSAData *)
0x18006cc19  test    rax, rax
0x18006cc1c  jz      loc_18006CD07
0x18006cc22  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18006cc29  lea     rdx, aGetsockopt; "getsockopt"
0x18006cc30  call    cs:__imp_GetProcAddress
0x18006cc37  nop     dword ptr [rax+rax+00h]
0x18006cc3c  mov     cs:?g_getsockopt@@3P6AH_KHHPEADPEAH@ZEA, rax; int (*g_getsockopt)(unsigned __int64,int,int,char *,int *)
0x18006cc43  test    rax, rax
0x18006cc46  jz      loc_18006CD07
0x18006cc4c  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18006cc53  lea     rdx, aGetsockname; "getsockname"
0x18006cc5a  call    cs:__imp_GetProcAddress
0x18006cc61  nop     dword ptr [rax+rax+00h]
0x18006cc66  mov     cs:?g_getsockname@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getsockname)(unsigned __int64,sockaddr *,int *)
0x18006cc6d  test    rax, rax
0x18006cc70  jz      loc_18006CD07
0x18006cc76  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18006cc7d  lea     rdx, aGetpeername; "getpeername"
0x18006cc84  call    cs:__imp_GetProcAddress
0x18006cc8b  nop     dword ptr [rax+rax+00h]
0x18006cc90  mov     cs:?g_getpeername@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getpeername)(unsigned __int64,sockaddr *,int *)
0x18006cc97  test    rax, rax
0x18006cc9a  jz      short loc_18006CD07
0x18006cc9c  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18006cca3  lea     rdx, aWsacleanup; "WSACleanup"
0x18006ccaa  call    cs:__imp_GetProcAddress
0x18006ccb1  nop     dword ptr [rax+rax+00h]
0x18006ccb6  mov     cs:?g_WSACleanup@@3P6AHXZEA, rax; int (*g_WSACleanup)(void)
0x18006ccbd  test    rax, rax
0x18006ccc0  jz      short loc_18006CD07
0x18006ccc2  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x18006ccc9  lea     rdx, aClosesocket; "closesocket"
0x18006ccd0  call    cs:__imp_GetProcAddress
0x18006ccd7  nop     dword ptr [rax+rax+00h]
0x18006ccdc  mov     cs:?g_closesocket@@3P6AH_K@ZEA, rax; int (*g_closesocket)(unsigned __int64)
0x18006cce3  test    rax, rax
0x18006cce6  jz      short loc_18006CD07
0x18006cce8  mov     rax, cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA; int (*g_WSAStartup)(ushort,WSAData *)
0x18006ccef  lea     rdx, [rsp+1D8h+var_1B8]
0x18006ccf4  mov     ecx, 202h
0x18006ccf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ccfe  test    eax, eax
0x18006cd00  jnz     short loc_18006CD07
0x18006cd02  lea     ebx, [rax+1]
0x18006cd05  jmp     short loc_18006CD2B
0x18006cd07  mov     rax, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_ws2_32
0x18006cd0e  xor     ebx, ebx
0x18006cd10  test    rax, rax
0x18006cd13  jz      short loc_18006CD2B
0x18006cd15  mov     rcx, rax; hLibModule
0x18006cd18  call    cs:__imp_FreeLibrary
0x18006cd1f  nop     dword ptr [rax+rax+00h]
0x18006cd24  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_ws2_32
0x18006cd2b  mov     eax, ebx
0x18006cd2d  mov     rcx, [rsp+1D8h+var_18]
0x18006cd35  xor     rcx, rsp; StackCookie
0x18006cd38  call    __security_check_cookie
0x18006cd3d  add     rsp, 1D0h
0x18006cd44  pop     rbx
0x18006cd45  retn
```
