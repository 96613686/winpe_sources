# UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)

- ea: `0x180038bd4`
- end: `0x180038cde`
- name: `?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z`
- size: `266`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180038668`
- `0x180038b38`
- `0x1800666c0`
- `0x180077bc4`
- `0x18008dec8`

## callees

- `0x18000716c`
- `0x18000bfbc`
- `0x18000d75c`
- `0x180013a20`
- `0x180038bd4`
- `0x180050db0`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038c0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038c0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038c1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038c1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180038c4c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180038c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038cac`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180038c3a`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180038c3a`

## string_xrefs

- `0x180038c15`: `GetSystemWow64Directory2W`
- `0x180038c05`: `api-ms-win-core-wow64-l1-1-1.dll`

## pseudocode

```c
__int64 __fastcall UtilGetSystemDirectory2(void *a1, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  UINT SystemWow64DirectoryW; // eax
  __int64 v7; // rbx
  DWORD LastError; // eax
  WCHAR Buffer[64]; // [rsp+20h] [rbp-98h] BYREF

  if ( a2 )
  {
    ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-wow64-l1-1-1.dll");
    ProcAddress = GetProcAddress(ModuleHandleW, "GetSystemWow64Directory2W");
    if ( ProcAddress )
      SystemWow64DirectoryW = ((__int64 (__fastcall *)(WCHAR *, __int64, _QWORD))ProcAddress)(Buffer, 64, a2);
    else
      SystemWow64DirectoryW = GetSystemWow64DirectoryW(Buffer, 0x40u);
  }
  else
  {
    SystemWow64DirectoryW = GetSystemDirectoryW(Buffer, 0x40u);
  }
  if ( SystemWow64DirectoryW - 1 > 0x3F )
  {
    LastError = GetLastError();
    return ERROR_HR_FROM_WIN32(LastError);
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( Buffer[v7] );
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(a1);
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            a1,
                            Buffer,
                            v7) )
      return (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                a1,
                                92) == 0
           ? 0x8007000E
           : 0;
    else
      return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180038bd4  mov     [rsp+arg_10], rbx
0x180038bd9  mov     [rsp+arg_18], rsi
0x180038bde  push    rdi
0x180038bdf  sub     rsp, 0B0h
0x180038be6  mov     rax, cs:__security_cookie
0x180038bed  xor     rax, rsp
0x180038bf0  mov     [rsp+0B8h+var_18], rax
0x180038bf8  xor     esi, esi
0x180038bfa  movzx   ebx, dx
0x180038bfd  mov     rdi, rcx
0x180038c00  test    dx, dx
0x180038c03  jz      short loc_180038C42
0x180038c05  lea     rcx, aApiMsWinCoreWo_1; "api-ms-win-core-wow64-l1-1-1.dll"
0x180038c0c  call    cs:__imp_GetModuleHandleW
0x180038c12  mov     rcx, rax; hModule
0x180038c15  lea     rdx, aGetsystemwow64; "GetSystemWow64Directory2W"
0x180038c1c  call    cs:__imp_GetProcAddress
0x180038c22  lea     edx, [rsi+40h]; uSize
0x180038c25  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x180038c2a  test    rax, rax
0x180038c2d  jz      short loc_180038C3A
0x180038c2f  movzx   r8d, bx
0x180038c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c38  jmp     short loc_180038C52
0x180038c3a  call    cs:__imp_GetSystemWow64DirectoryW
0x180038c40  jmp     short loc_180038C52
0x180038c42  mov     edx, 40h ; '@'; uSize
0x180038c47  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x180038c4c  call    cs:__imp_GetSystemDirectoryW
0x180038c52  dec     eax
0x180038c54  cmp     eax, 3Fh ; '?'
0x180038c57  ja      short loc_180038CAC
0x180038c59  lea     rax, [rsp+0B8h+Buffer]
0x180038c5e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180038c62  inc     rbx
0x180038c65  cmp     [rax+rbx*2], si
0x180038c69  jnz     short loc_180038C62
0x180038c6b  lea     rdx, [rbx+1]
0x180038c6f  mov     rcx, rdi
0x180038c72  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x180038c77  mov     r8, rbx
0x180038c7a  lea     rdx, [rsp+0B8h+Buffer]
0x180038c7f  mov     rcx, rdi
0x180038c82  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180038c87  test    al, al
0x180038c89  jz      short loc_180038CA5
0x180038c8b  mov     edx, 5Ch ; '\'
0x180038c90  mov     rcx, rdi
0x180038c93  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180038c98  neg     al
0x180038c9a  sbb     eax, eax
0x180038c9c  not     eax
0x180038c9e  and     eax, 8007000Eh
0x180038ca3  jmp     short loc_180038CB9
0x180038ca5  mov     eax, 8007000Eh
0x180038caa  jmp     short loc_180038CB9
0x180038cac  call    cs:__imp_GetLastError
0x180038cb2  mov     ecx, eax; unsigned int
0x180038cb4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180038cb9  mov     rcx, [rsp+0B8h+var_18]
0x180038cc1  xor     rcx, rsp; StackCookie
0x180038cc4  call    __security_check_cookie
0x180038cc9  lea     r11, [rsp+0B8h+var_8]
0x180038cd1  mov     rbx, [r11+20h]
0x180038cd5  mov     rsi, [r11+28h]
0x180038cd9  mov     rsp, r11
0x180038cdc  pop     rdi
0x180038cdd  retn
```
