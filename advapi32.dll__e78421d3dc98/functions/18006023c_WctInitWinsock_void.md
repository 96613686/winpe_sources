# WctInitWinsock(void)

- ea: `0x18006023c`
- end: `0x1800603b6`
- name: `?WctInitWinsock@@YAHXZ`
- size: `378`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800603bc`

## callees

- `0x18006023c`
- `0x18006505a`
- `0x180065090`
- `0x180066010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800602a4`
- `KERNEL32!GetProcAddress` at `0x1800602c8`
- `KERNEL32!GetProcAddress` at `0x1800602ec`
- `KERNEL32!GetProcAddress` at `0x18006030c`
- `KERNEL32!GetProcAddress` at `0x18006032c`
- `KERNEL32!GetProcAddress` at `0x18006034c`
- `KERNEL32!GetProcAddress` at `0x1800602a4`
- `KERNEL32!GetProcAddress` at `0x1800602c8`
- `KERNEL32!GetProcAddress` at `0x1800602ec`
- `KERNEL32!GetProcAddress` at `0x18006030c`
- `KERNEL32!GetProcAddress` at `0x18006032c`
- `KERNEL32!GetProcAddress` at `0x18006034c`
- `KERNEL32!FreeLibrary` at `0x18006038e`
- `KERNEL32!FreeLibrary` at `0x18006038e`
- `KERNEL32!LoadLibraryW` at `0x180060284`
- `KERNEL32!LoadLibraryW` at `0x180060284`

## string_xrefs

- `0x180060325`: `WSACleanup`
- `0x18006027d`: `ws2_32.dll`

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
0x18006023c  push    rbx
0x18006023e  sub     rsp, 1D0h
0x180060245  mov     rax, cs:__security_cookie
0x18006024c  xor     rax, rsp
0x18006024f  mov     [rsp+1D8h+var_18], rax
0x180060257  xor     edx, edx; Val
0x180060259  lea     rcx, [rsp+1D8h+var_1B8]; void *
0x18006025e  mov     r8d, 198h; Size
0x180060264  call    memset_0
0x180060269  cmp     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_ws2_32
0x180060271  jz      short loc_18006027D
0x180060273  mov     eax, 1
0x180060278  jmp     loc_18006039D
0x18006027d  lea     rcx, aWs232Dll; "ws2_32.dll"
0x180060284  call    cs:__imp_LoadLibraryW
0x18006028a  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_ws2_32
0x180060291  test    rax, rax
0x180060294  jz      loc_180060384
0x18006029a  lea     rdx, aWsastartup; "WSAStartup"
0x1800602a1  mov     rcx, rax; hModule
0x1800602a4  call    cs:__imp_GetProcAddress
0x1800602aa  mov     cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA, rax; int (*g_WSAStartup)(ushort,WSAData *)
0x1800602b1  test    rax, rax
0x1800602b4  jz      loc_18006037D
0x1800602ba  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x1800602c1  lea     rdx, aGetsockopt; "getsockopt"
0x1800602c8  call    cs:__imp_GetProcAddress
0x1800602ce  mov     cs:?g_getsockopt@@3P6AH_KHHPEADPEAH@ZEA, rax; int (*g_getsockopt)(unsigned __int64,int,int,char *,int *)
0x1800602d5  test    rax, rax
0x1800602d8  jz      loc_18006037D
0x1800602de  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x1800602e5  lea     rdx, aGetsockname; "getsockname"
0x1800602ec  call    cs:__imp_GetProcAddress
0x1800602f2  mov     cs:?g_getsockname@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getsockname)(unsigned __int64,sockaddr *,int *)
0x1800602f9  test    rax, rax
0x1800602fc  jz      short loc_18006037D
0x1800602fe  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x180060305  lea     rdx, aGetpeername; "getpeername"
0x18006030c  call    cs:__imp_GetProcAddress
0x180060312  mov     cs:?g_getpeername@@3P6AH_KPEAUsockaddr@@PEAH@ZEA, rax; int (*g_getpeername)(unsigned __int64,sockaddr *,int *)
0x180060319  test    rax, rax
0x18006031c  jz      short loc_18006037D
0x18006031e  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x180060325  lea     rdx, aWsacleanup; "WSACleanup"
0x18006032c  call    cs:__imp_GetProcAddress
0x180060332  mov     cs:?g_WSACleanup@@3P6AHXZEA, rax; int (*g_WSACleanup)(void)
0x180060339  test    rax, rax
0x18006033c  jz      short loc_18006037D
0x18006033e  mov     rcx, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; hModule
0x180060345  lea     rdx, aClosesocket; "closesocket"
0x18006034c  call    cs:__imp_GetProcAddress
0x180060352  mov     cs:?g_closesocket@@3P6AH_K@ZEA, rax; int (*g_closesocket)(unsigned __int64)
0x180060359  test    rax, rax
0x18006035c  jz      short loc_18006037D
0x18006035e  mov     rax, cs:?g_WSAStartup@@3P6AHGPEAUWSAData@@@ZEA; int (*g_WSAStartup)(ushort,WSAData *)
0x180060365  lea     rdx, [rsp+1D8h+var_1B8]
0x18006036a  mov     ecx, 202h
0x18006036f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060374  test    eax, eax
0x180060376  jnz     short loc_18006037D
0x180060378  lea     ebx, [rax+1]
0x18006037b  jmp     short loc_18006039B
0x18006037d  mov     rax, cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_ws2_32
0x180060384  xor     ebx, ebx
0x180060386  test    rax, rax
0x180060389  jz      short loc_18006039B
0x18006038b  mov     rcx, rax; hLibModule
0x18006038e  call    cs:__imp_FreeLibrary
0x180060394  mov     cs:?g_ws2_32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_ws2_32
0x18006039b  mov     eax, ebx
0x18006039d  mov     rcx, [rsp+1D8h+var_18]
0x1800603a5  xor     rcx, rsp; StackCookie
0x1800603a8  call    __security_check_cookie
0x1800603ad  add     rsp, 1D0h
0x1800603b4  pop     rbx
0x1800603b5  retn
```
