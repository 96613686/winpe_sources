# UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)

- ea: `0x1400112cc`
- end: `0x1400113e5`
- name: `?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z`
- size: `281`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140011f24`
- `0x140030cd8`
- `0x14003f768`
- `0x14003faf8`
- `0x14004dd88`

## callees

- `0x140002470`
- `0x14000c8a0`
- `0x14000cb24`
- `0x1400112cc`
- `0x140014104`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011304`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011304`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011314`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400113a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400113a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140011344`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140011344`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x140011332`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x140011332`

## string_xrefs

- `0x14001130d`: `GetSystemWow64Directory2W`
- `0x1400112fd`: `api-ms-win-core-wow64-l1-1-1.dll`

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
                            Buffer,
                            v7) )
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
0x1400112cc  mov     [rsp+arg_10], rbx
0x1400112d1  mov     [rsp+arg_18], rsi
0x1400112d6  push    rdi
0x1400112d7  sub     rsp, 0B0h
0x1400112de  mov     rax, cs:__security_cookie
0x1400112e5  xor     rax, rsp
0x1400112e8  mov     [rsp+0B8h+var_18], rax
0x1400112f0  xor     esi, esi
0x1400112f2  movzx   ebx, dx
0x1400112f5  mov     rdi, rcx
0x1400112f8  test    dx, dx
0x1400112fb  jz      short loc_14001133A
0x1400112fd  lea     rcx, aApiMsWinCoreWo_1; "api-ms-win-core-wow64-l1-1-1.dll"
0x140011304  call    cs:__imp_GetModuleHandleW
0x14001130a  mov     rcx, rax; hModule
0x14001130d  lea     rdx, aGetsystemwow64; "GetSystemWow64Directory2W"
0x140011314  call    cs:__imp_GetProcAddress
0x14001131a  lea     edx, [rsi+40h]; uSize
0x14001131d  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x140011322  test    rax, rax
0x140011325  jz      short loc_140011332
0x140011327  movzx   r8d, bx
0x14001132b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011330  jmp     short loc_14001134A
0x140011332  call    cs:__imp_GetSystemWow64DirectoryW
0x140011338  jmp     short loc_14001134A
0x14001133a  mov     edx, 40h ; '@'; uSize
0x14001133f  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x140011344  call    cs:__imp_GetSystemDirectoryW
0x14001134a  dec     eax
0x14001134c  cmp     eax, 3Fh ; '?'
0x14001134f  ja      short loc_1400113A4
0x140011351  lea     rax, [rsp+0B8h+Buffer]
0x140011356  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14001135a  inc     rbx
0x14001135d  cmp     [rax+rbx*2], si
0x140011361  jnz     short loc_14001135A
0x140011363  lea     rdx, [rbx+1]
0x140011367  mov     rcx, rdi
0x14001136a  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x14001136f  mov     r8, rbx
0x140011372  lea     rdx, [rsp+0B8h+Buffer]
0x140011377  mov     rcx, rdi
0x14001137a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14001137f  test    al, al
0x140011381  jz      short loc_14001139D
0x140011383  mov     edx, 5Ch ; '\'
0x140011388  mov     rcx, rdi
0x14001138b  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140011390  neg     al
0x140011392  sbb     eax, eax
0x140011394  not     eax
0x140011396  and     eax, 8007000Eh
0x14001139b  jmp     short loc_1400113C0
0x14001139d  mov     eax, 8007000Eh
0x1400113a2  jmp     short loc_1400113C0
0x1400113a4  call    cs:__imp_GetLastError
0x1400113aa  test    eax, eax
0x1400113ac  jle     short loc_1400113B6
0x1400113ae  movzx   eax, ax
0x1400113b1  or      eax, 80070000h
0x1400113b6  test    eax, eax
0x1400113b8  mov     ecx, 80004005h
0x1400113bd  cmovns  eax, ecx
0x1400113c0  mov     rcx, [rsp+0B8h+var_18]
0x1400113c8  xor     rcx, rsp; StackCookie
0x1400113cb  call    __security_check_cookie
0x1400113d0  lea     r11, [rsp+0B8h+var_8]
0x1400113d8  mov     rbx, [r11+20h]
0x1400113dc  mov     rsi, [r11+28h]
0x1400113e0  mov     rsp, r11
0x1400113e3  pop     rdi
0x1400113e4  retn
```
