# CTpLogger::CreateLoggingDirectory(wchar_t *,ulong)

- ea: `0x1800372d8`
- end: `0x18003742b`
- name: `?CreateLoggingDirectory@CTpLogger@@AEAAJPEA_WK@Z`
- size: `339`
- prototype: `int(CTpLogger *__hidden this, wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004485c`
- `0x1800a0418`

## callees

- `0x1800372d8`
- `0x1800376a8`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800373c7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800373c7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800372f7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800372f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003734d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003734d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037367`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003740a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003740a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800373f3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800373f3`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180037389`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180037389`

## string_xrefs

- `0x180037346`: `kernelbase.dll`
- `0x18003735d`: `GetTempPath2W`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CTpLogger::CreateLoggingDirectory(CTpLogger *this, wchar_t *a2)
{
  __int64 v3; // rax
  int result; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  WCHAR *v7; // rdx
  DWORD TempPathW; // eax
  signed int LastError; // eax
  unsigned int v10; // ebx
  HMODULE v11; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 6) == *((_QWORD *)this + 7) )
  {
    Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
    v11 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetTempPath2W");
      v7 = a2;
      if ( ProcAddress )
      {
        TempPathW = ((__int64 (__fastcall *)(__int64, wchar_t *))ProcAddress)(260, a2);
        goto LABEL_14;
      }
    }
    else
    {
      v7 = a2;
    }
    TempPathW = GetTempPathW(0x104u, v7);
LABEL_14:
    if ( TempPathW )
    {
      if ( TempPathW < 0x104 )
      {
        if ( !(unsigned int)_o_wcscat_s(a2, 260, L"TpLogger\\") )
        {
          tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v11);
          goto LABEL_23;
        }
        v10 = -2147467259;
      }
      else
      {
        v10 = -2147024774;
      }
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v11);
    return v10;
  }
  if ( (unsigned int)_o_wcscpy_s(a2, 260) )
    return -2147024774;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( a2[(int)v3 - 1] != 92 )
  {
    if ( (unsigned int)(v3 + 1) < 0x104 )
    {
      *(_DWORD *)&a2[(int)v3] = 92;
      goto LABEL_23;
    }
    return -2147024774;
  }
LABEL_23:
  if ( CreateDirectoryW(a2, 0) || GetLastError() == 183 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800372d8  mov     [rsp+arg_8], rbx
0x1800372dd  push    rdi
0x1800372de  sub     rsp, 20h
0x1800372e2  mov     rbx, rdx
0x1800372e5  mov     r8, [rcx+30h]
0x1800372e9  cmp     r8, [rcx+38h]
0x1800372ed  jz      short loc_18003733E
0x1800372ef  mov     edx, 104h
0x1800372f4  mov     rcx, rbx
0x1800372f7  call    cs:__imp__o_wcscpy_s
0x1800372fd  xor     edi, edi
0x1800372ff  test    eax, eax
0x180037301  jnz     short loc_180037334
0x180037303  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037307  inc     rax
0x18003730a  cmp     [rbx+rax*2], di
0x18003730e  jnz     short loc_180037307
0x180037310  movsxd  rcx, eax
0x180037313  mov     edx, 5Ch ; '\'
0x180037318  cmp     [rbx+rcx*2-2], dx
0x18003731d  jz      loc_1800373EE
0x180037323  inc     eax
0x180037325  cmp     eax, 104h
0x18003732a  jnb     short loc_180037334
0x18003732c  mov     [rbx+rcx*2], edx
0x18003732f  jmp     loc_1800373EE
0x180037334  mov     eax, 8007007Ah
0x180037339  jmp     loc_180037420
0x18003733e  xor     edx, edx; hFile
0x180037340  mov     r8d, 800h; dwFlags
0x180037346  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003734d  call    cs:__imp_LoadLibraryExW
0x180037353  mov     [rsp+28h+arg_0], rax
0x180037358  test    rax, rax
0x18003735b  jz      short loc_180037381
0x18003735d  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x180037364  mov     rcx, rax; hModule
0x180037367  call    cs:__imp_GetProcAddress
0x18003736d  mov     rdx, rbx
0x180037370  mov     ecx, 104h
0x180037375  test    rax, rax
0x180037378  jz      short loc_180037389
0x18003737a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003737f  jmp     short loc_18003738F
0x180037381  mov     rdx, rbx; lpBuffer
0x180037384  mov     ecx, 104h; nBufferLength
0x180037389  call    cs:__imp_GetTempPathW
0x18003738f  test    eax, eax
0x180037391  jnz     short loc_1800373AA
0x180037393  call    cs:__imp_GetLastError
0x180037399  mov     ebx, eax
0x18003739b  test    eax, eax
0x18003739d  jle     short loc_1800373D6
0x18003739f  movzx   ebx, ax
0x1800373a2  or      ebx, 80070000h
0x1800373a8  jmp     short loc_1800373D6
0x1800373aa  cmp     eax, 104h
0x1800373af  jb      short loc_1800373B8
0x1800373b1  mov     ebx, 8007007Ah
0x1800373b6  jmp     short loc_1800373D6
0x1800373b8  lea     r8, aTplogger; "TpLogger\\"
0x1800373bf  mov     edx, 104h
0x1800373c4  mov     rcx, rbx
0x1800373c7  call    cs:__imp__o_wcscat_s
0x1800373cd  test    eax, eax
0x1800373cf  jz      short loc_1800373E4
0x1800373d1  mov     ebx, 80004005h
0x1800373d6  lea     rcx, [rsp+28h+arg_0]
0x1800373db  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x1800373e0  mov     eax, ebx
0x1800373e2  jmp     short loc_180037420
0x1800373e4  lea     rcx, [rsp+28h+arg_0]
0x1800373e9  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x1800373ee  xor     edx, edx; lpSecurityAttributes
0x1800373f0  mov     rcx, rbx; lpPathName
0x1800373f3  call    cs:__imp_CreateDirectoryW
0x1800373f9  test    eax, eax
0x1800373fb  jnz     short loc_18003741E
0x1800373fd  call    cs:__imp_GetLastError
0x180037403  cmp     eax, 0B7h
0x180037408  jz      short loc_18003741E
0x18003740a  call    cs:__imp_GetLastError
0x180037410  test    eax, eax
0x180037412  jle     short loc_180037420
0x180037414  movzx   eax, ax
0x180037417  or      eax, 80070000h
0x18003741c  jmp     short loc_180037420
0x18003741e  xor     eax, eax
0x180037420  mov     rbx, [rsp+28h+arg_8]
0x180037425  add     rsp, 20h
0x180037429  pop     rdi
0x18003742a  retn
```
