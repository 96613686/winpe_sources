# User32DllLoader::Initialize(IRequestContext &)

- ea: `0x180127850`
- end: `0x1801279c8`
- name: `?Initialize@User32DllLoader@@UEAA_NAEAVIRequestContext@@@Z`
- size: `376`
- prototype: `bool __fastcall(User32DllLoader *__hidden this, struct IRequestContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180014990`
- `0x1800870f0`
- `0x180112380`
- `0x180127850`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801278c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801278c7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180127973`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180127990`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180127973`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180127990`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18012794b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18012794b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801278b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801278b4`

## string_xrefs

- `0x180127906`: `user32.dll`
- `0x1801278f9`: `\user32.dll`
- `0x180127989`: `PostThreadMessageW`

## pseudocode

```c
char __fastcall User32DllLoader::Initialize(User32DllLoader *this, struct IRequestContext *a2)
{
  void (__fastcall *v4)(struct IRequestContext *, __int64); // rbx
  __int64 LastError; // rdx
  __int64 v7; // rax
  const unsigned __int16 *v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v13; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_98aa05c4e0903ffb820b490c0a8da906_Traceguids);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_5;
  v7 = -1;
  do
    ++v7;
  while ( Buffer[v7] );
  v8 = L"user32.dll";
  if ( Buffer[v7 - 1] != 92 )
    v8 = L"\\user32.dll";
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
  AutoCleanup<AutoLibrary,HINSTANCE__ *>::operator=((char *)this + 8, Library);
  if ( !*((_QWORD *)this + 1)
    || (ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "PostMessageW"), (*((_QWORD *)this + 2) = ProcAddress) == 0)
    || (v13 = GetProcAddress(*((HMODULE *)this + 1), "PostThreadMessageW"), (*((_QWORD *)this + 3) = v13) == 0) )
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
0x180127850  mov     [rsp+arg_10], rbx
0x180127855  push    rbp
0x180127856  push    rsi
0x180127857  push    rdi
0x180127858  sub     rsp, 240h
0x18012785f  mov     rax, cs:__security_cookie
0x180127866  xor     rax, rsp
0x180127869  mov     [rsp+258h+var_28], rax
0x180127871  mov     rdi, rdx
0x180127874  mov     rbx, rcx
0x180127877  mov     rcx, cs:WPP_GLOBAL_Control
0x18012787e  lea     rax, WPP_GLOBAL_Control
0x180127885  cmp     rcx, rax
0x180127888  jz      short loc_1801278A8
0x18012788a  test    dword ptr [rcx+1Ch], 1000000h
0x180127891  jz      short loc_1801278A8
0x180127893  mov     rcx, [rcx+10h]
0x180127897  lea     r8, WPP_98aa05c4e0903ffb820b490c0a8da906_Traceguids
0x18012789e  mov     edx, 6Ch ; 'l'
0x1801278a3  call    WPP_SF_
0x1801278a8  mov     esi, 104h
0x1801278ad  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1801278b2  mov     edx, esi; uSize
0x1801278b4  call    cs:__imp_GetSystemDirectoryW
0x1801278ba  xor     ebp, ebp
0x1801278bc  test    eax, eax
0x1801278be  jnz     short loc_1801278E1
0x1801278c0  mov     rax, [rdi]
0x1801278c3  mov     rbx, [rax+48h]
0x1801278c7  call    cs:__imp_GetLastError
0x1801278cd  mov     edx, eax
0x1801278cf  mov     rax, rbx
0x1801278d2  mov     rcx, rdi
0x1801278d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801278da  xor     al, al
0x1801278dc  jmp     loc_1801279A5
0x1801278e1  lea     rcx, [rsp+258h+Buffer]
0x1801278e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801278ea  inc     rax
0x1801278ed  cmp     [rcx+rax*2], bp
0x1801278f1  jnz     short loc_1801278EA
0x1801278f3  mov     r9d, 5Ch ; '\'
0x1801278f9  lea     rcx, aUser32Dll; "\\user32.dll"
0x180127900  cmp     r9w, [rsp+rax*2+258h+var_23A]
0x180127906  lea     r8, aUser32Dll_0; "user32.dll"
0x18012790d  mov     rdx, rsi; unsigned __int64
0x180127910  cmovnz  r8, rcx; unsigned __int16 *
0x180127914  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x180127919  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18012791e  mov     edx, eax
0x180127920  test    eax, eax
0x180127922  jns     short loc_180127941
0x180127924  mov     rax, [rdi]
0x180127927  mov     r8, [rax+48h]
0x18012792b  mov     eax, edx
0x18012792d  and     eax, 1FFF0000h
0x180127932  cmp     eax, 70000h
0x180127937  jnz     short loc_18012793C
0x180127939  movzx   edx, dx
0x18012793c  mov     rax, r8
0x18012793f  jmp     short loc_1801278D2
0x180127941  xor     r8d, r8d; dwFlags
0x180127944  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x180127949  xor     edx, edx; hFile
0x18012794b  call    cs:__imp_LoadLibraryExW
0x180127951  lea     rsi, [rbx+8]
0x180127955  mov     rdx, rax
0x180127958  mov     rcx, rsi
0x18012795b  call    ??4?$AutoCleanup@VAutoLibrary@@PEAUHINSTANCE__@@@@QEAAAEAVAutoLibrary@@PEAUHINSTANCE__@@@Z; AutoCleanup<AutoLibrary,HINSTANCE__ *>::operator=(HINSTANCE__ *)
0x180127960  mov     rcx, [rsi]; hModule
0x180127963  test    rcx, rcx
0x180127966  jz      loc_1801278C0
0x18012796c  lea     rdx, aPostmessagew; "PostMessageW"
0x180127973  call    cs:__imp_GetProcAddress
0x180127979  mov     [rbx+10h], rax
0x18012797d  test    rax, rax
0x180127980  jz      loc_1801278C0
0x180127986  mov     rcx, [rsi]; hModule
0x180127989  lea     rdx, aPostthreadmess; "PostThreadMessageW"
0x180127990  call    cs:__imp_GetProcAddress
0x180127996  mov     [rbx+18h], rax
0x18012799a  test    rax, rax
0x18012799d  jz      loc_1801278C0
0x1801279a3  mov     al, 1
0x1801279a5  mov     rcx, [rsp+258h+var_28]
0x1801279ad  xor     rcx, rsp; StackCookie
0x1801279b0  call    __security_check_cookie
0x1801279b5  mov     rbx, [rsp+258h+arg_10]
0x1801279bd  add     rsp, 240h
0x1801279c4  pop     rdi
0x1801279c5  pop     rsi
0x1801279c6  pop     rbp
0x1801279c7  retn
```
