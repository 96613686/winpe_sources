# IpHlpApiDllLoader::Initialize(IRequestContext &)

- ea: `0x180127370`
- end: `0x180127505`
- name: `?Initialize@IpHlpApiDllLoader@@UEAA_NAEAVIRequestContext@@@Z`
- size: `405`
- prototype: `char __fastcall(IpHlpApiDllLoader *this, struct IRequestContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180014990`
- `0x1800870f0`
- `0x180112380`
- `0x180127370`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801273e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801273e7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180127493`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801274b0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801274cd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180127493`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801274b0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801274cd`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18012746b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18012746b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801273d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801273d4`

## string_xrefs

- `0x180127426`: `IpHlpApi.dll`
- `0x180127419`: `\IpHlpApi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
char __fastcall IpHlpApiDllLoader::Initialize(IpHlpApiDllLoader *this, struct IRequestContext *a2)
{
  void (__fastcall *v4)(struct IRequestContext *, __int64); // rbx
  __int64 LastError; // rdx
  __int64 v7; // rax
  const unsigned __int16 *v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  HMODULE Library; // rax
  HMODULE *v12; // rsi
  FARPROC ProcAddress; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_98aa05c4e0903ffb820b490c0a8da906_Traceguids);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_5;
  v7 = -1;
  do
    ++v7;
  while ( Buffer[v7] );
  v8 = L"IpHlpApi.dll";
  if ( Buffer[v7 - 1] != 92 )
    v8 = L"\\IpHlpApi.dll";
  v9 = StringCchCatW(Buffer, 0x104u, v8);
  v10 = (unsigned int)v9;
  if ( v9 < 0 )
  {
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v10 = (unsigned __int16)v9;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v10);
    return 0;
  }
  Library = LoadLibraryExW(Buffer, 0, 0);
  v12 = (HMODULE *)((char *)this + 8);
  AutoCleanup<AutoLibrary,HINSTANCE__ *>::operator=((char *)this + 8, Library);
  if ( !*((_QWORD *)this + 1)
    || (ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "CancelMibChangeNotify2"),
        (*((_QWORD *)this + 2) = ProcAddress) == 0)
    || (v14 = GetProcAddress(*v12, "GetAdaptersAddresses"), (*((_QWORD *)this + 3) = v14) == 0)
    || (v15 = GetProcAddress(*v12, "NotifyUnicastIpAddressChange"), (*((_QWORD *)this + 4) = v15) == 0) )
  {
LABEL_5:
    v4 = *(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL);
    LastError = GetLastError();
    v4(a2, LastError);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180127370  mov     [rsp+arg_10], rbx
0x180127375  push    rbp
0x180127376  push    rsi
0x180127377  push    rdi
0x180127378  sub     rsp, 240h
0x18012737f  mov     rax, cs:__security_cookie
0x180127386  xor     rax, rsp
0x180127389  mov     [rsp+258h+var_28], rax
0x180127391  mov     rdi, rdx
0x180127394  mov     rbx, rcx
0x180127397  mov     rcx, cs:WPP_GLOBAL_Control
0x18012739e  lea     rax, WPP_GLOBAL_Control
0x1801273a5  cmp     rcx, rax
0x1801273a8  jz      short loc_1801273C8
0x1801273aa  test    dword ptr [rcx+1Ch], 1000000h
0x1801273b1  jz      short loc_1801273C8
0x1801273b3  mov     rcx, [rcx+10h]
0x1801273b7  lea     r8, WPP_98aa05c4e0903ffb820b490c0a8da906_Traceguids
0x1801273be  mov     edx, 6Dh ; 'm'
0x1801273c3  call    WPP_SF_
0x1801273c8  mov     esi, 104h
0x1801273cd  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1801273d2  mov     edx, esi; uSize
0x1801273d4  call    cs:__imp_GetSystemDirectoryW
0x1801273da  xor     ebp, ebp
0x1801273dc  test    eax, eax
0x1801273de  jnz     short loc_180127401
0x1801273e0  mov     rax, [rdi]
0x1801273e3  mov     rbx, [rax+48h]
0x1801273e7  call    cs:__imp_GetLastError
0x1801273ed  mov     edx, eax
0x1801273ef  mov     rax, rbx
0x1801273f2  mov     rcx, rdi
0x1801273f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801273fa  xor     al, al
0x1801273fc  jmp     loc_1801274E2
0x180127401  lea     rcx, [rsp+258h+Buffer]
0x180127406  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012740a  inc     rax
0x18012740d  cmp     [rcx+rax*2], bp
0x180127411  jnz     short loc_18012740A
0x180127413  mov     r9d, 5Ch ; '\'
0x180127419  lea     rcx, aIphlpapiDll; "\\IpHlpApi.dll"
0x180127420  cmp     r9w, [rsp+rax*2+258h+var_23A]
0x180127426  lea     r8, aIphlpapiDll_0; "IpHlpApi.dll"
0x18012742d  mov     rdx, rsi; unsigned __int64
0x180127430  cmovnz  r8, rcx; unsigned __int16 *
0x180127434  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x180127439  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18012743e  mov     edx, eax
0x180127440  test    eax, eax
0x180127442  jns     short loc_180127461
0x180127444  mov     rax, [rdi]
0x180127447  mov     r8, [rax+48h]
0x18012744b  mov     eax, edx
0x18012744d  and     eax, 1FFF0000h
0x180127452  cmp     eax, 70000h
0x180127457  jnz     short loc_18012745C
0x180127459  movzx   edx, dx
0x18012745c  mov     rax, r8
0x18012745f  jmp     short loc_1801273F2
0x180127461  xor     r8d, r8d; dwFlags
0x180127464  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x180127469  xor     edx, edx; hFile
0x18012746b  call    cs:__imp_LoadLibraryExW
0x180127471  lea     rsi, [rbx+8]
0x180127475  mov     rdx, rax
0x180127478  mov     rcx, rsi
0x18012747b  call    ??4?$AutoCleanup@VAutoLibrary@@PEAUHINSTANCE__@@@@QEAAAEAVAutoLibrary@@PEAUHINSTANCE__@@@Z; AutoCleanup<AutoLibrary,HINSTANCE__ *>::operator=(HINSTANCE__ *)
0x180127480  mov     rcx, [rsi]; hModule
0x180127483  test    rcx, rcx
0x180127486  jz      loc_1801273E0
0x18012748c  lea     rdx, aCancelmibchang; "CancelMibChangeNotify2"
0x180127493  call    cs:__imp_GetProcAddress
0x180127499  mov     [rbx+10h], rax
0x18012749d  test    rax, rax
0x1801274a0  jz      loc_1801273E0
0x1801274a6  mov     rcx, [rsi]; hModule
0x1801274a9  lea     rdx, aGetadaptersadd_0; "GetAdaptersAddresses"
0x1801274b0  call    cs:__imp_GetProcAddress
0x1801274b6  mov     [rbx+18h], rax
0x1801274ba  test    rax, rax
0x1801274bd  jz      loc_1801273E0
0x1801274c3  mov     rcx, [rsi]; hModule
0x1801274c6  lea     rdx, aNotifyunicasti; "NotifyUnicastIpAddressChange"
0x1801274cd  call    cs:__imp_GetProcAddress
0x1801274d3  mov     [rbx+20h], rax
0x1801274d7  test    rax, rax
0x1801274da  jz      loc_1801273E0
0x1801274e0  mov     al, 1
0x1801274e2  mov     rcx, [rsp+258h+var_28]
0x1801274ea  xor     rcx, rsp; StackCookie
0x1801274ed  call    __security_check_cookie
0x1801274f2  mov     rbx, [rsp+258h+arg_10]
0x1801274fa  add     rsp, 240h
0x180127501  pop     rdi
0x180127502  pop     rsi
0x180127503  pop     rbp
0x180127504  retn
```
