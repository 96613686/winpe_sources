# wprt::proc::impl::WindowsPrinterProcessor::ReadPrinterData(SmartHstring &,ulong)

- ea: `0x180004b20`
- end: `0x180004d99`
- name: `?ReadPrinterData@WindowsPrinterProcessor@impl@proc@wprt@@UEAA_NAEAVSmartHstring@@K@Z`
- size: `633`
- prototype: `bool __fastcall(wprt::proc::impl::WindowsPrinterProcessor *__hidden this, struct SmartHstring *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180003180`
- `0x180003580`
- `0x180004440`
- `0x1800046b0`
- `0x180004b20`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180004d4f`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180004d4f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004d0f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004d0f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004b55`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004b55`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004c99`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004c99`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004d69`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004d69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004bbd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004cf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004bbd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004cf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004cc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004cc4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004b9c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004c16`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004cdb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004b9c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004c16`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180004cdb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004c7e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004c7e`

## string_xrefs

- `0x180004bb3`: `OpenPrinterW`
- `0x180004c2d`: `ReadPrinter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall wprt::proc::impl::WindowsPrinterProcessor::ReadPrinterData(
        wprt::proc::impl::WindowsPrinterProcessor *this,
        struct SmartHstring *a2,
        unsigned int a3)
{
  int v6; // esi
  void *v7; // r15
  HMODULE v8; // rbx
  void **v9; // rdi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  void *TmpFile; // r12
  int v13; // edi
  int v14; // ebp
  __int64 v15; // r14
  FARPROC v16; // rax
  DWORD v17; // eax
  bool v18; // zf
  __int64 v19; // rdi
  FARPROC v20; // rax
  void *v21; // rcx
  __int64 v23; // [rsp+38h] [rbp-60h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+40h] [rbp-58h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-54h] BYREF
  void *Block[3]; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int64 v27; // [rsp+60h] [rbp-38h]

  v6 = 0;
  v7 = malloc(0x40000u);
  v8 = 0;
  if ( v7 )
  {
    v23 = 0;
    wprt::proc::impl::WindowsPrinterProcessor::CreatePrinterNameWithJob(this, Block, a3);
    v9 = Block;
    if ( v27 >= 8 )
      v9 = (void **)Block[0];
    LibraryW = LoadLibraryW(L"winspool.drv");
    v8 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "OpenPrinterW");
      if ( ProcAddress )
      {
        if ( ((unsigned int (__fastcall *)(void **, __int64 *, _QWORD))ProcAddress)(v9, &v23, 0) )
        {
          TmpFile = wprt::proc::impl::WindowsPrinterProcessor::CreateTmpFile(this, a2);
          if ( TmpFile != (void *)-1LL )
          {
            nNumberOfBytesToWrite = 0;
            v13 = 0;
            v14 = 0;
            do
            {
              v15 = v23;
              if ( !v8 )
              {
                v8 = LoadLibraryW(L"winspool.drv");
                if ( !v8 )
                  break;
              }
              v16 = GetProcAddress(v8, "ReadPrinter");
              if ( !v16
                || !((unsigned int (__fastcall *)(__int64, void *, __int64, DWORD *))v16)(
                      v15,
                      v7,
                      0x40000,
                      &nNumberOfBytesToWrite) )
              {
                break;
              }
              v17 = nNumberOfBytesToWrite;
              v13 += nNumberOfBytesToWrite;
              if ( nNumberOfBytesToWrite )
              {
                NumberOfBytesWritten = 0;
                v18 = !WriteFile(TmpFile, v7, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
                v17 = nNumberOfBytesToWrite;
                if ( !v18 )
                  v14 += NumberOfBytesWritten;
              }
              else if ( !v13 )
              {
                Sleep(5u);
                v17 = nNumberOfBytesToWrite;
              }
            }
            while ( v17 || !v13 );
            if ( v13 == v14 && v13 )
              v6 = 1;
            CloseHandle(TmpFile);
          }
          v19 = v23;
          if ( v8 || (v8 = LoadLibraryW(L"winspool.drv")) != 0 )
          {
            v20 = GetProcAddress(v8, "ClosePrinter");
            if ( v20 )
              ((void (__fastcall *)(__int64))v20)(v19);
          }
        }
      }
    }
    free(v7);
    if ( v27 >= 8 )
    {
      v21 = Block[0];
      if ( 2 * v27 + 2 >= 0x1000 )
      {
        v21 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v21 - 8) > 0x1F )
        {
          _o__invalid_parameter_noinfo_noreturn(v21, 2 * v27 + 41);
          __debugbreak();
        }
      }
      operator delete(v21);
    }
  }
  if ( v8 )
    FreeLibrary(v8);
  return v6 != 0;
}

```

## disassembly

```asm
0x180004b20  mov     [rsp+arg_10], rbx
0x180004b25  mov     [rsp+arg_18], rbp
0x180004b2a  push    rsi
0x180004b2b  push    rdi
0x180004b2c  push    r12
0x180004b2e  push    r14
0x180004b30  push    r15
0x180004b32  sub     rsp, 70h
0x180004b36  mov     rax, cs:__security_cookie
0x180004b3d  xor     rax, rsp
0x180004b40  mov     [rsp+98h+var_30], rax
0x180004b45  mov     edi, r8d
0x180004b48  mov     r14, rdx
0x180004b4b  mov     rbp, rcx
0x180004b4e  xor     esi, esi
0x180004b50  mov     ecx, 40000h; Size
0x180004b55  call    cs:__imp_malloc
0x180004b5b  mov     r15, rax
0x180004b5e  mov     ebx, esi
0x180004b60  mov     [rsp+98h+var_68], rbx
0x180004b65  test    rax, rax
0x180004b68  jz      loc_180004D5B
0x180004b6e  mov     [rsp+98h+var_60], rsi
0x180004b73  mov     r8d, edi
0x180004b76  lea     rdx, [rsp+98h+Block]
0x180004b7b  mov     rcx, rbp
0x180004b7e  call    ?CreatePrinterNameWithJob@WindowsPrinterProcessor@impl@proc@wprt@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; wprt::proc::impl::WindowsPrinterProcessor::CreatePrinterNameWithJob(ulong)
0x180004b83  nop
0x180004b84  lea     rdi, [rsp+98h+Block]
0x180004b89  cmp     [rsp+98h+var_38], 8
0x180004b8f  cmovnb  rdi, [rsp+98h+Block]
0x180004b95  lea     rcx, LibFileName; "winspool.drv"
0x180004b9c  call    cs:__imp_LoadLibraryW
0x180004ba2  mov     rbx, rax
0x180004ba5  mov     [rsp+98h+var_68], rax
0x180004baa  test    rax, rax
0x180004bad  jz      loc_180004D0C
0x180004bb3  lea     rdx, ProcName; "OpenPrinterW"
0x180004bba  mov     rcx, rax; hModule
0x180004bbd  call    cs:__imp_GetProcAddress
0x180004bc3  test    rax, rax
0x180004bc6  jz      loc_180004D0C
0x180004bcc  xor     r8d, r8d
0x180004bcf  lea     rdx, [rsp+98h+var_60]
0x180004bd4  mov     rcx, rdi
0x180004bd7  call    cs:__guard_dispatch_icall_fptr
0x180004bdd  test    eax, eax
0x180004bdf  jz      loc_180004D0C
0x180004be5  mov     rdx, r14; struct SmartHstring *
0x180004be8  mov     rcx, rbp; this
0x180004beb  call    ?CreateTmpFile@WindowsPrinterProcessor@impl@proc@wprt@@AEAAPEAXAEAVSmartHstring@@@Z; wprt::proc::impl::WindowsPrinterProcessor::CreateTmpFile(SmartHstring &)
0x180004bf0  mov     r12, rax
0x180004bf3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004bf7  jz      loc_180004CCA
0x180004bfd  mov     [rsp+98h+nNumberOfBytesToWrite], esi
0x180004c01  mov     edi, esi
0x180004c03  mov     ebp, esi
0x180004c05  mov     r14, [rsp+98h+var_60]
0x180004c0a  test    rbx, rbx
0x180004c0d  jnz     short loc_180004C2D
0x180004c0f  lea     rcx, LibFileName; "winspool.drv"
0x180004c16  call    cs:__imp_LoadLibraryW
0x180004c1c  mov     rbx, rax
0x180004c1f  mov     [rsp+98h+var_68], rax
0x180004c24  test    rax, rax
0x180004c27  jz      loc_180004CB3
0x180004c2d  lea     rdx, aReadprinter; "ReadPrinter"
0x180004c34  mov     rcx, rbx; hModule
0x180004c37  call    cs:__imp_GetProcAddress
0x180004c3d  test    rax, rax
0x180004c40  jz      short loc_180004CB3
0x180004c42  lea     r9, [rsp+98h+nNumberOfBytesToWrite]
0x180004c47  mov     r8d, 40000h
0x180004c4d  mov     rdx, r15
0x180004c50  mov     rcx, r14
0x180004c53  call    cs:__guard_dispatch_icall_fptr
0x180004c59  test    eax, eax
0x180004c5b  jz      short loc_180004CB3
0x180004c5d  mov     eax, [rsp+98h+nNumberOfBytesToWrite]
0x180004c61  add     edi, eax
0x180004c63  test    eax, eax
0x180004c65  jz      short loc_180004C92
0x180004c67  mov     [rsp+98h+NumberOfBytesWritten], esi
0x180004c6b  mov     [rsp+98h+lpOverlapped], rsi; lpOverlapped
0x180004c70  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180004c75  mov     r8d, eax; nNumberOfBytesToWrite
0x180004c78  mov     rdx, r15; lpBuffer
0x180004c7b  mov     rcx, r12; hFile
0x180004c7e  call    cs:__imp_WriteFile
0x180004c84  test    eax, eax
0x180004c86  mov     eax, [rsp+98h+nNumberOfBytesToWrite]
0x180004c8a  jz      short loc_180004CA3
0x180004c8c  add     ebp, [rsp+98h+NumberOfBytesWritten]
0x180004c90  jmp     short loc_180004CA3
0x180004c92  test    edi, edi
0x180004c94  jnz     short loc_180004CA3
0x180004c96  lea     ecx, [rdi+5]; dwMilliseconds
0x180004c99  call    cs:__imp_Sleep
0x180004c9f  mov     eax, [rsp+98h+nNumberOfBytesToWrite]
0x180004ca3  test    eax, eax
0x180004ca5  jnz     loc_180004C05
0x180004cab  test    edi, edi
0x180004cad  jz      loc_180004C05
0x180004cb3  cmp     edi, ebp
0x180004cb5  jnz     short loc_180004CC1
0x180004cb7  mov     eax, 1
0x180004cbc  test    edi, edi
0x180004cbe  cmovnz  esi, eax
0x180004cc1  mov     rcx, r12; hObject
0x180004cc4  call    cs:__imp_CloseHandle
0x180004cca  mov     rdi, [rsp+98h+var_60]
0x180004ccf  test    rbx, rbx
0x180004cd2  jnz     short loc_180004CEE
0x180004cd4  lea     rcx, LibFileName; "winspool.drv"
0x180004cdb  call    cs:__imp_LoadLibraryW
0x180004ce1  mov     rbx, rax
0x180004ce4  mov     [rsp+98h+var_68], rax
0x180004ce9  test    rax, rax
0x180004cec  jz      short loc_180004D0C
0x180004cee  lea     rdx, aCloseprinter; "ClosePrinter"
0x180004cf5  mov     rcx, rbx; hModule
0x180004cf8  call    cs:__imp_GetProcAddress
0x180004cfe  test    rax, rax
0x180004d01  jz      short loc_180004D0C
0x180004d03  mov     rcx, rdi
0x180004d06  call    cs:__guard_dispatch_icall_fptr
0x180004d0c  mov     rcx, r15; Block
0x180004d0f  call    cs:__imp_free
0x180004d15  nop
0x180004d16  mov     rdx, [rsp+98h+var_38]
0x180004d1b  cmp     rdx, 8
0x180004d1f  jb      short loc_180004D5B
0x180004d21  lea     rdx, ds:2[rdx*2]
0x180004d29  mov     rcx, [rsp+98h+Block]; Block
0x180004d2e  mov     rax, rcx
0x180004d31  cmp     rdx, 1000h
0x180004d38  jb      short loc_180004D56
0x180004d3a  add     rdx, 27h ; '''
0x180004d3e  mov     rcx, [rcx-8]
0x180004d42  sub     rax, rcx
0x180004d45  add     rax, 0FFFFFFFFFFFFFFF8h
0x180004d49  cmp     rax, 1Fh
0x180004d4d  jbe     short loc_180004D56
0x180004d4f  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180004d55  int     3; Trap to Debugger
0x180004d56  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004d5b  test    esi, esi
0x180004d5d  setnz   dil
0x180004d61  test    rbx, rbx
0x180004d64  jz      short loc_180004D6F
0x180004d66  mov     rcx, rbx; hLibModule
0x180004d69  call    cs:__imp_FreeLibrary
0x180004d6f  movzx   eax, dil
0x180004d73  mov     rcx, [rsp+98h+var_30]
0x180004d78  xor     rcx, rsp; StackCookie
0x180004d7b  call    __security_check_cookie
0x180004d80  lea     r11, [rsp+98h+var_28]
0x180004d85  mov     rbx, [r11+40h]
0x180004d89  mov     rbp, [r11+48h]
0x180004d8d  mov     rsp, r11
0x180004d90  pop     r15
0x180004d92  pop     r14
0x180004d94  pop     r12
0x180004d96  pop     rdi
0x180004d97  pop     rsi
0x180004d98  retn
```
