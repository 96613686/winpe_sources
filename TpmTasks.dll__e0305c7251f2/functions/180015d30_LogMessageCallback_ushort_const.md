# LogMessageCallback(ushort const *)

- ea: `0x180015d30`
- end: `0x180015eae`
- name: `?LogMessageCallback@@YAXPEBG@Z`
- size: `382`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000bc54`
- `0x18000bcc4`
- `0x180015d30`
- `0x18001be20`
- `0x180023634`
- `0x18002386c`
- `0x180059200`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180015e6d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180015e6d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015e21`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015e21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015e76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015e76`
- `SHELL32!SHGetKnownFolderPath` at `0x180015db3`
- `SHELL32!SHGetKnownFolderPath` at `0x180015db3`

## string_xrefs

- `0x180015de7`: `\Logs\TPMTaskLog.txt`
- `0x180015e32`: `\nTPMTask: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LogMessageCallback(const unsigned __int16 *a1)
{
  __int64 v2; // rbx
  __int64 v3; // r8
  const WCHAR *v4; // rax
  HANDLE FileW; // rdi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPath; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v8[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 Buffer[8192]; // [rsp+70h] [rbp-90h] BYREF

  NumberOfBytesWritten = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  v8[0] = 0;
  v8[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v8[0]) = 0;
  ppszPath = 0;
  if ( SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath) >= 0 )
  {
    v2 = -1;
    v3 = -1;
    do
      ++v3;
    while ( ppszPath[v3] );
    std::wstring::_Assign<unsigned short>(v8, ppszPath);
    std::wstring::_Append<unsigned short>(v8, L"\\Logs\\TPMTaskLog.txt", 20);
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
    FileW = CreateFileW(v4, 4u, 0, 0, 4u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      StringCchPrintfW(Buffer, 0x2000u, L"\nTPMTask: %s", a1);
      do
        ++v2;
      while ( Buffer[v2] );
      WriteFile(FileW, Buffer, 2 * v2, &NumberOfBytesWritten, 0);
      CloseHandle(FileW);
    }
  }
  std::wstring::_Tidy_deallocate(v8);
}

```

## disassembly

```asm
0x180015d30  mov     [rsp-8+arg_8], rbx
0x180015d35  mov     [rsp-8+arg_10], rsi
0x180015d3a  push    rbp
0x180015d3b  push    rdi
0x180015d3c  push    r14
0x180015d3e  lea     rbp, [rsp-3F80h]
0x180015d46  mov     eax, 4080h
0x180015d4b  call    _alloca_probe
0x180015d50  sub     rsp, rax
0x180015d53  mov     rax, cs:__security_cookie
0x180015d5a  xor     rax, rsp
0x180015d5d  mov     [rbp+3F90h+var_20], rax
0x180015d64  mov     rsi, rcx
0x180015d67  xor     r14d, r14d
0x180015d6a  mov     [rsp+4090h+NumberOfBytesWritten], r14d
0x180015d6f  xor     edx, edx; Val
0x180015d71  mov     r8d, 4000h; Size
0x180015d77  lea     rcx, [rsp+4090h+Buffer]; void *
0x180015d7c  call    memset_0
0x180015d81  xorps   xmm0, xmm0
0x180015d84  movups  [rsp+4090h+var_4040], xmm0
0x180015d89  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180015d91  movdqu  [rsp+4090h+var_4030], xmm1
0x180015d97  mov     word ptr [rsp+4090h+var_4040], r14w
0x180015d9d  mov     [rsp+4090h+ppszPath], r14
0x180015da2  lea     r9, [rsp+4090h+ppszPath]; ppszPath
0x180015da7  xor     r8d, r8d; hToken
0x180015daa  xor     edx, edx; dwFlags
0x180015dac  lea     rcx, FOLDERID_Windows; rfid
0x180015db3  call    cs:__imp_SHGetKnownFolderPath
0x180015db9  test    eax, eax
0x180015dbb  js      loc_180015E7D
0x180015dc1  mov     rdx, [rsp+4090h+ppszPath]
0x180015dc6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015dca  mov     r8, rbx
0x180015dcd  inc     r8
0x180015dd0  cmp     [rdx+r8*2], r14w
0x180015dd5  jnz     short loc_180015DCD
0x180015dd7  lea     rcx, [rsp+4090h+var_4040]
0x180015ddc  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180015de1  mov     r8d, 14h
0x180015de7  lea     rdx, aLogsTpmtasklog; "\\Logs\\TPMTaskLog.txt"
0x180015dee  lea     rcx, [rsp+4090h+var_4040]
0x180015df3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180015df8  lea     rcx, [rsp+4090h+var_4040]
0x180015dfd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015e02  mov     rcx, rax; lpFileName
0x180015e05  mov     [rsp+4090h+hTemplateFile], r14; hTemplateFile
0x180015e0a  mov     [rsp+4090h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180015e12  mov     edx, 4; dwDesiredAccess
0x180015e17  mov     [rsp+4090h+dwCreationDisposition], edx; dwCreationDisposition
0x180015e1b  xor     r9d, r9d; lpSecurityAttributes
0x180015e1e  xor     r8d, r8d; dwShareMode
0x180015e21  call    cs:__imp_CreateFileW
0x180015e27  mov     rdi, rax
0x180015e2a  cmp     rax, rbx
0x180015e2d  jz      short loc_180015E7D
0x180015e2f  mov     r9, rsi
0x180015e32  lea     r8, aTpmtaskS; "\nTPMTask: %s"
0x180015e39  mov     edx, 2000h; unsigned __int64
0x180015e3e  lea     rcx, [rsp+4090h+Buffer]; unsigned __int16 *
0x180015e43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015e48  lea     rax, [rsp+4090h+Buffer]
0x180015e4d  inc     rbx
0x180015e50  cmp     [rax+rbx*2], r14w
0x180015e55  jnz     short loc_180015E4D
0x180015e57  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x180015e5b  mov     qword ptr [rsp+4090h+dwCreationDisposition], r14; lpOverlapped
0x180015e60  lea     r9, [rsp+4090h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180015e65  lea     rdx, [rsp+4090h+Buffer]; lpBuffer
0x180015e6a  mov     rcx, rdi; hFile
0x180015e6d  call    cs:__imp_WriteFile
0x180015e73  mov     rcx, rdi; hObject
0x180015e76  call    cs:__imp_CloseHandle
0x180015e7c  nop
0x180015e7d  lea     rcx, [rsp+4090h+var_4040]
0x180015e82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015e87  mov     rcx, [rbp+3F90h+var_20]
0x180015e8e  xor     rcx, rsp; StackCookie
0x180015e91  call    __security_check_cookie
0x180015e96  lea     r11, [rsp+4090h+var_10]
0x180015e9e  mov     rbx, [r11+28h]
0x180015ea2  mov     rsi, [r11+30h]
0x180015ea6  mov     rsp, r11
0x180015ea9  pop     r14
0x180015eab  pop     rdi
0x180015eac  pop     rbp
0x180015ead  retn
```
