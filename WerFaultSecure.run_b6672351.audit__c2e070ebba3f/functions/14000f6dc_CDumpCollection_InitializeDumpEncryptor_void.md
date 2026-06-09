# CDumpCollection::_InitializeDumpEncryptor(void)

- ea: `0x14000f6dc`
- end: `0x14000f815`
- name: `?_InitializeDumpEncryptor@CDumpCollection@@AEAAJXZ`
- size: `313`
- prototype: `__int64 __fastcall(CDumpCollection *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000e8c4`

## callees

- `0x1400023d0`
- `0x14000f6dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000f74b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000f74b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f77c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f7e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f77c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f7e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f79c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f7b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f79c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f7b7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000f763`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000f763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f70e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f70e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14000f704`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14000f704`

## string_xrefs

- `0x14000f73a`: `\WerEnc.dll`

## pseudocode

```c
signed int __fastcall CDumpCollection::_InitializeDumpEncryptor(CDumpCollection *this)
{
  UINT SystemDirectoryW; // eax
  signed int result; // eax
  HMODULE Library; // rax
  HMODULE v5; // rcx
  HMODULE v6; // rcx
  FARPROC ProcAddress; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  bool v10; // zf
  HMODULE v11; // rcx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemDirectoryW )
  {
    if ( SystemDirectoryW >= 0x104 || (unsigned int)_o_wcscat_s(Buffer, 260, L"\\WerEnc.dll") )
    {
      return -2147024774;
    }
    else
    {
      Library = LoadLibraryExW(Buffer, 0, 0);
      v5 = (HMODULE)*((_QWORD *)this + 140);
      *((_QWORD *)this + 140) = Library;
      if ( v5 )
        FreeLibrary(v5);
      v6 = (HMODULE)*((_QWORD *)this + 140);
      if ( v6 )
      {
        ProcAddress = GetProcAddress(v6, "EncryptDumpStream");
        v8 = (HMODULE)*((_QWORD *)this + 140);
        *((_QWORD *)this + 141) = ProcAddress;
        v9 = GetProcAddress(v8, "EncryptDumpFile");
        v10 = *((_QWORD *)this + 141) == 0;
        *((_QWORD *)this + 142) = v9;
        if ( !v10 || v9 )
        {
          return 0;
        }
        else
        {
          v11 = (HMODULE)*((_QWORD *)this + 140);
          *((_QWORD *)this + 140) = 0;
          if ( v11 )
            FreeLibrary(v11);
          return -2147024769;
        }
      }
      else
      {
        return -2147024770;
      }
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x14000f6dc  push    rbx
0x14000f6de  sub     rsp, 240h
0x14000f6e5  mov     rax, cs:__security_cookie
0x14000f6ec  xor     rax, rsp
0x14000f6ef  mov     [rsp+248h+var_18], rax
0x14000f6f7  mov     rbx, rcx
0x14000f6fa  mov     edx, 104h; uSize
0x14000f6ff  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x14000f704  call    cs:__imp_GetSystemDirectoryW
0x14000f70a  test    eax, eax
0x14000f70c  jnz     short loc_14000F72F
0x14000f70e  call    cs:__imp_GetLastError
0x14000f714  test    eax, eax
0x14000f716  jle     short loc_14000F720
0x14000f718  movzx   eax, ax
0x14000f71b  or      eax, 80070000h
0x14000f720  test    eax, eax
0x14000f722  mov     ecx, 80004005h
0x14000f727  cmovns  eax, ecx
0x14000f72a  jmp     loc_14000F7FC
0x14000f72f  cmp     eax, 104h
0x14000f734  jnb     loc_14000F7F7
0x14000f73a  lea     r8, aWerencDll; "\\WerEnc.dll"
0x14000f741  mov     edx, 104h
0x14000f746  lea     rcx, [rsp+248h+Buffer]
0x14000f74b  call    cs:__imp__o_wcscat_s
0x14000f751  test    eax, eax
0x14000f753  jnz     loc_14000F7F7
0x14000f759  xor     r8d, r8d; dwFlags
0x14000f75c  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x14000f761  xor     edx, edx; hFile
0x14000f763  call    cs:__imp_LoadLibraryExW
0x14000f769  mov     rcx, [rbx+460h]; hLibModule
0x14000f770  mov     [rbx+460h], rax
0x14000f777  test    rcx, rcx
0x14000f77a  jz      short loc_14000F782
0x14000f77c  call    cs:__imp_FreeLibrary
0x14000f782  mov     rcx, [rbx+460h]; hModule
0x14000f789  test    rcx, rcx
0x14000f78c  jnz     short loc_14000F795
0x14000f78e  mov     eax, 8007007Eh
0x14000f793  jmp     short loc_14000F7FC
0x14000f795  lea     rdx, aEncryptdumpstr; "EncryptDumpStream"
0x14000f79c  call    cs:__imp_GetProcAddress
0x14000f7a2  mov     rcx, [rbx+460h]; hModule
0x14000f7a9  lea     rdx, aEncryptdumpfil; "EncryptDumpFile"
0x14000f7b0  mov     [rbx+468h], rax
0x14000f7b7  call    cs:__imp_GetProcAddress
0x14000f7bd  cmp     qword ptr [rbx+468h], 0
0x14000f7c5  mov     [rbx+470h], rax
0x14000f7cc  jnz     short loc_14000F7F3
0x14000f7ce  test    rax, rax
0x14000f7d1  jnz     short loc_14000F7F3
0x14000f7d3  mov     rcx, [rbx+460h]; hLibModule
0x14000f7da  mov     [rbx+460h], rax
0x14000f7e1  test    rcx, rcx
0x14000f7e4  jz      short loc_14000F7EC
0x14000f7e6  call    cs:__imp_FreeLibrary
0x14000f7ec  mov     eax, 8007007Fh
0x14000f7f1  jmp     short loc_14000F7FC
0x14000f7f3  xor     eax, eax
0x14000f7f5  jmp     short loc_14000F7FC
0x14000f7f7  mov     eax, 8007007Ah
0x14000f7fc  mov     rcx, [rsp+248h+var_18]
0x14000f804  xor     rcx, rsp; StackCookie
0x14000f807  call    __security_check_cookie
0x14000f80c  add     rsp, 240h
0x14000f813  pop     rbx
0x14000f814  retn
```
