# UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)

- ea: `0x140011a04`
- end: `0x140011b3c`
- name: `?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140012784`
- `0x140032ec4`
- `0x1400422cc`
- `0x140042670`
- `0x140051348`

## callees

- `0x140002490`
- `0x14000ca20`
- `0x14000cd94`
- `0x140011a04`
- `0x140014b9c`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011a3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011a3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011a52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011af4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140011a8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140011a8e`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x140011a76`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x140011a76`

## string_xrefs

- `0x140011a4b`: `GetSystemWow64Directory2W`
- `0x140011a35`: `api-ms-win-core-wow64-l1-1-1.dll`

## pseudocode

```c
signed int __fastcall UtilGetSystemDirectory2(__int64 a1, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  UINT SystemWow64DirectoryW; // eax
  __int64 v7; // rbx
  signed int result; // eax
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
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( Buffer[v7] );
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(a1, v7 + 1);
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            a1,
                            Buffer) )
      return (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                a1,
                                92) == 0
           ? 0x8007000E
           : 0;
    else
      return -2147024882;
  }
  return result;
}

```

## disassembly

```asm
0x140011a04  mov     [rsp+arg_10], rbx
0x140011a09  mov     [rsp+arg_18], rsi
0x140011a0e  push    rdi
0x140011a0f  sub     rsp, 0B0h
0x140011a16  mov     rax, cs:__security_cookie
0x140011a1d  xor     rax, rsp
0x140011a20  mov     [rsp+0B8h+var_18], rax
0x140011a28  xor     esi, esi
0x140011a2a  movzx   ebx, dx
0x140011a2d  mov     rdi, rcx
0x140011a30  test    dx, dx
0x140011a33  jz      short loc_140011A84
0x140011a35  lea     rcx, aApiMsWinCoreWo_1; "api-ms-win-core-wow64-l1-1-1.dll"
0x140011a3c  call    cs:__imp_GetModuleHandleW
0x140011a43  nop     dword ptr [rax+rax+00h]
0x140011a48  mov     rcx, rax; hModule
0x140011a4b  lea     rdx, aGetsystemwow64; "GetSystemWow64Directory2W"
0x140011a52  call    cs:__imp_GetProcAddress
0x140011a59  nop     dword ptr [rax+rax+00h]
0x140011a5e  lea     edx, [rsi+40h]; uSize
0x140011a61  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x140011a66  test    rax, rax
0x140011a69  jz      short loc_140011A76
0x140011a6b  movzx   r8d, bx
0x140011a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a74  jmp     short loc_140011A9A
0x140011a76  call    cs:__imp_GetSystemWow64DirectoryW
0x140011a7d  nop     dword ptr [rax+rax+00h]
0x140011a82  jmp     short loc_140011A9A
0x140011a84  mov     edx, 40h ; '@'; uSize
0x140011a89  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x140011a8e  call    cs:__imp_GetSystemDirectoryW
0x140011a95  nop     dword ptr [rax+rax+00h]
0x140011a9a  dec     eax
0x140011a9c  cmp     eax, 3Fh ; '?'
0x140011a9f  ja      short loc_140011AF4
0x140011aa1  lea     rax, [rsp+0B8h+Buffer]
0x140011aa6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140011aaa  inc     rbx
0x140011aad  cmp     [rax+rbx*2], si
0x140011ab1  jnz     short loc_140011AAA
0x140011ab3  lea     rdx, [rbx+1]
0x140011ab7  mov     rcx, rdi
0x140011aba  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x140011abf  mov     r8, rbx
0x140011ac2  lea     rdx, [rsp+0B8h+Buffer]
0x140011ac7  mov     rcx, rdi
0x140011aca  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140011acf  test    al, al
0x140011ad1  jz      short loc_140011AED
0x140011ad3  mov     edx, 5Ch ; '\'
0x140011ad8  mov     rcx, rdi
0x140011adb  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140011ae0  neg     al
0x140011ae2  sbb     eax, eax
0x140011ae4  not     eax
0x140011ae6  and     eax, 8007000Eh
0x140011aeb  jmp     short loc_140011B16
0x140011aed  mov     eax, 8007000Eh
0x140011af2  jmp     short loc_140011B16
0x140011af4  call    cs:__imp_GetLastError
0x140011afb  nop     dword ptr [rax+rax+00h]
0x140011b00  test    eax, eax
0x140011b02  jle     short loc_140011B0C
0x140011b04  movzx   eax, ax
0x140011b07  or      eax, 80070000h
0x140011b0c  test    eax, eax
0x140011b0e  mov     ecx, 80004005h
0x140011b13  cmovns  eax, ecx
0x140011b16  mov     rcx, [rsp+0B8h+var_18]
0x140011b1e  xor     rcx, rsp; StackCookie
0x140011b21  call    __security_check_cookie
0x140011b26  lea     r11, [rsp+0B8h+var_8]
0x140011b2e  mov     rbx, [r11+20h]
0x140011b32  mov     rsi, [r11+28h]
0x140011b36  mov     rsp, r11
0x140011b39  pop     rdi
0x140011b3a  retn
```
