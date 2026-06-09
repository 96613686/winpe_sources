# wprt::proc::impl::WindowsPrinterProcessor::SendJobCommand(ulong,ulong)

- ea: `0x180004da0`
- end: `0x180004f71`
- name: `?SendJobCommand@WindowsPrinterProcessor@impl@proc@wprt@@AEAA_NKK@Z`
- size: `465`
- prototype: `bool __fastcall(wprt::proc::impl::WindowsPrinterProcessor *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800050f0`

## callees

- `0x180003180`
- `0x180003580`
- `0x180004da0`
- `0x1800a031b`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180004f49`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180004f49`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004f09`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004f09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ee7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ee7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004e23`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004e79`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004eca`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004e23`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004e79`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004eca`

## string_xrefs

- `0x180004e36`: `OpenPrinterW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall wprt::proc::impl::WindowsPrinterProcessor::SendJobCommand(HSTRING *this, unsigned int a2, int a3)
{
  PCWSTR StringRawBuffer_0; // rax
  unsigned __int64 v6; // r8
  void **v7; // rsi
  int v8; // edi
  HMODULE LibraryW; // rax
  HMODULE v10; // rbx
  FARPROC ProcAddress; // rax
  bool v12; // zf
  __int64 v13; // rsi
  int v14; // edi
  FARPROC v15; // rax
  __int64 v16; // rsi
  FARPROC v17; // rax
  bool v18; // di
  void *v19; // rcx
  __int64 v21; // [rsp+38h] [rbp-60h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v23; // [rsp+50h] [rbp-48h]

  v21 = 0;
  StringRawBuffer_0 = WindowsGetStringRawBuffer_0(this[1], 0);
  *(_OWORD *)Block = 0;
  v23 = 0;
  v6 = -1;
  do
    ++v6;
  while ( StringRawBuffer_0[v6] );
  std::wstring::_Construct<1,wchar_t const *>((char **)Block, StringRawBuffer_0, v6);
  v7 = Block;
  if ( *((_QWORD *)&v23 + 1) >= 8u )
    v7 = (void **)Block[0];
  v8 = 0;
  LibraryW = LoadLibraryW(L"winspool.drv");
  v10 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "OpenPrinterW");
    if ( ProcAddress )
      v8 = ((__int64 (__fastcall *)(void **, __int64 *, _QWORD))ProcAddress)(v7, &v21, 0);
  }
  v12 = v8 == 0;
  if ( v8 )
  {
    v13 = v21;
    v14 = 0;
    if ( v10 || (v10 = LoadLibraryW(L"winspool.drv")) != 0 )
    {
      v15 = GetProcAddress(v10, "SetJobW");
      if ( v15 )
        v14 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, int))v15)(v13, a2, 0, 0, a3);
    }
    v16 = v21;
    if ( v10 || (v10 = LoadLibraryW(L"winspool.drv")) != 0 )
    {
      v17 = GetProcAddress(v10, "ClosePrinter");
      if ( v17 )
        ((void (__fastcall *)(__int64))v17)(v16);
    }
    v12 = v14 == 0;
  }
  v18 = !v12;
  if ( v10 )
    FreeLibrary(v10);
  if ( *((_QWORD *)&v23 + 1) >= 8u )
  {
    v19 = Block[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v23 + 1) + 2) >= 0x1000 )
    {
      v19 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v19 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v19, 2LL * *((_QWORD *)&v23 + 1) + 41);
        __debugbreak();
      }
    }
    operator delete(v19);
  }
  return v18;
}

```

## disassembly

```asm
0x180004da0  push    rbx
0x180004da2  push    rbp
0x180004da3  push    rsi
0x180004da4  push    rdi
0x180004da5  push    r14
0x180004da7  sub     rsp, 70h
0x180004dab  mov     rax, cs:__security_cookie
0x180004db2  xor     rax, rsp
0x180004db5  mov     [rsp+98h+var_38], rax
0x180004dba  mov     r14d, r8d
0x180004dbd  mov     ebp, edx
0x180004dbf  mov     [rsp+98h+var_60], 0
0x180004dc8  xor     edx, edx; length
0x180004dca  mov     rcx, [rcx+8]; string
0x180004dce  call    WindowsGetStringRawBuffer_0
0x180004dd3  xorps   xmm0, xmm0
0x180004dd6  movups  xmmword ptr [rsp+98h+Block], xmm0
0x180004ddb  xorps   xmm1, xmm1
0x180004dde  movdqu  [rsp+98h+var_48], xmm1
0x180004de4  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180004deb  nop     dword ptr [rax+rax+00h]
0x180004df0  inc     r8
0x180004df3  cmp     word ptr [rax+r8*2], 0
0x180004df9  jnz     short loc_180004DF0
0x180004dfb  mov     rdx, rax
0x180004dfe  lea     rcx, [rsp+98h+Block]
0x180004e03  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004e08  nop
0x180004e09  lea     rsi, [rsp+98h+Block]
0x180004e0e  cmp     qword ptr [rsp+98h+var_48+8], 8
0x180004e14  cmovnb  rsi, [rsp+98h+Block]
0x180004e1a  xor     edi, edi
0x180004e1c  lea     rcx, LibFileName; "winspool.drv"
0x180004e23  call    cs:__imp_LoadLibraryW
0x180004e29  mov     rbx, rax
0x180004e2c  mov     [rsp+98h+var_68], rax
0x180004e31  test    rax, rax
0x180004e34  jz      short loc_180004E5E
0x180004e36  lea     rdx, ProcName; "OpenPrinterW"
0x180004e3d  mov     rcx, rax; hModule
0x180004e40  call    cs:__imp_GetProcAddress
0x180004e46  test    rax, rax
0x180004e49  jz      short loc_180004E5E
0x180004e4b  xor     r8d, r8d
0x180004e4e  lea     rdx, [rsp+98h+var_60]
0x180004e53  mov     rcx, rsi
0x180004e56  call    cs:__guard_dispatch_icall_fptr
0x180004e5c  mov     edi, eax
0x180004e5e  test    edi, edi
0x180004e60  jz      loc_180004EFD
0x180004e66  mov     rsi, [rsp+98h+var_60]
0x180004e6b  xor     edi, edi
0x180004e6d  test    rbx, rbx
0x180004e70  jnz     short loc_180004E8C
0x180004e72  lea     rcx, LibFileName; "winspool.drv"
0x180004e79  call    cs:__imp_LoadLibraryW
0x180004e7f  mov     rbx, rax
0x180004e82  mov     [rsp+98h+var_68], rax
0x180004e87  test    rax, rax
0x180004e8a  jz      short loc_180004EB9
0x180004e8c  lea     rdx, aSetjobw; "SetJobW"
0x180004e93  mov     rcx, rbx; hModule
0x180004e96  call    cs:__imp_GetProcAddress
0x180004e9c  test    rax, rax
0x180004e9f  jz      short loc_180004EB9
0x180004ea1  mov     [rsp+98h+var_78], r14d
0x180004ea6  xor     r9d, r9d
0x180004ea9  xor     r8d, r8d
0x180004eac  mov     edx, ebp
0x180004eae  mov     rcx, rsi
0x180004eb1  call    cs:__guard_dispatch_icall_fptr
0x180004eb7  mov     edi, eax
0x180004eb9  mov     rsi, [rsp+98h+var_60]
0x180004ebe  test    rbx, rbx
0x180004ec1  jnz     short loc_180004EDD
0x180004ec3  lea     rcx, LibFileName; "winspool.drv"
0x180004eca  call    cs:__imp_LoadLibraryW
0x180004ed0  mov     rbx, rax
0x180004ed3  mov     [rsp+98h+var_68], rax
0x180004ed8  test    rax, rax
0x180004edb  jz      short loc_180004EFB
0x180004edd  lea     rdx, aCloseprinter; "ClosePrinter"
0x180004ee4  mov     rcx, rbx; hModule
0x180004ee7  call    cs:__imp_GetProcAddress
0x180004eed  test    rax, rax
0x180004ef0  jz      short loc_180004EFB
0x180004ef2  mov     rcx, rsi
0x180004ef5  call    cs:__guard_dispatch_icall_fptr
0x180004efb  test    edi, edi
0x180004efd  setnz   dil
0x180004f01  test    rbx, rbx
0x180004f04  jz      short loc_180004F10
0x180004f06  mov     rcx, rbx; hLibModule
0x180004f09  call    cs:__imp_FreeLibrary
0x180004f0f  nop
0x180004f10  mov     rdx, qword ptr [rsp+98h+var_48+8]
0x180004f15  cmp     rdx, 8
0x180004f19  jb      short loc_180004F55
0x180004f1b  lea     rdx, ds:2[rdx*2]
0x180004f23  mov     rcx, [rsp+98h+Block]; Block
0x180004f28  mov     rax, rcx
0x180004f2b  cmp     rdx, 1000h
0x180004f32  jb      short loc_180004F50
0x180004f34  add     rdx, 27h ; '''
0x180004f38  mov     rcx, [rcx-8]
0x180004f3c  sub     rax, rcx
0x180004f3f  add     rax, 0FFFFFFFFFFFFFFF8h
0x180004f43  cmp     rax, 1Fh
0x180004f47  jbe     short loc_180004F50
0x180004f49  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180004f4f  int     3; Trap to Debugger
0x180004f50  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004f55  movzx   eax, dil
0x180004f59  mov     rcx, [rsp+98h+var_38]
0x180004f5e  xor     rcx, rsp; StackCookie
0x180004f61  call    __security_check_cookie
0x180004f66  add     rsp, 70h
0x180004f6a  pop     r14
0x180004f6c  pop     rdi
0x180004f6d  pop     rsi
0x180004f6e  pop     rbp
0x180004f6f  pop     rbx
0x180004f70  retn
```
