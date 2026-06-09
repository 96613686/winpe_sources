# LoadLibraryFromSystemDirectory

- ea: `0x1800519c4`
- end: `0x180051b20`
- name: `LoadLibraryFromSystemDirectory`
- size: `348`
- prototype: `__int64 __fastcall(__int64, HMODULE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180051b28`
- `0x180055a74`

## callees

- `0x180033e78`
- `0x180046888`
- `0x180049d00`
- `0x18004a71c`
- `0x1800519c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180051a21`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180051a21`
- `KERNEL32!LoadLibraryW` at `0x180051ac4`
- `KERNEL32!LoadLibraryW` at `0x180051ac4`
- `KERNEL32!GetSystemDirectoryW` at `0x180051a6f`
- `KERNEL32!GetSystemDirectoryW` at `0x180051a6f`
- `KERNEL32!GetLastError` at `0x180051ad5`
- `KERNEL32!GetLastError` at `0x180051ad5`

## pseudocode

```c
__int64 __fastcall LoadLibraryFromSystemDirectory(__int64 a1, HMODULE *a2)
{
  HRESULT v3; // ebx
  wchar_t *v4; // rax
  __int64 SystemDirectoryW; // r9
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  size_t pcchLength[2]; // [rsp+20h] [rbp-238h] BYREF
  wchar_t Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  pcchLength[0] = 0;
  if ( a2 )
  {
    v4 = wcsstr(L"winspool.drv", L"\\");
    *a2 = 0;
    if ( v4 )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      v3 = StringCchLengthW(L"winspool.drv", 0x103u, pcchLength);
      if ( v3 >= 0 )
      {
        SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
        if ( (unsigned __int64)(SystemDirectoryW - 1) > 0x101 || SystemDirectoryW + pcchLength[0] >= 0x103 )
        {
          return (unsigned int)-2147467259;
        }
        else
        {
          Buffer[SystemDirectoryW] = 92;
          v3 = StringCchCatW(Buffer, 0x104u, L"winspool.drv");
          if ( v3 >= 0 )
          {
            LibraryW = LoadLibraryW(Buffer);
            if ( LibraryW )
            {
              *a2 = LibraryW;
            }
            else
            {
              LastError = GetLastError();
              v3 = LastError;
              if ( LastError > 0 )
                return (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
      }
    }
  }
  else
  {
    v3 = -2147024809;
    MEMORY[0] = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800519c4  mov     [rsp+arg_0], rbx
0x1800519c9  push    rdi
0x1800519ca  sub     rsp, 250h
0x1800519d1  mov     rax, cs:__security_cookie
0x1800519d8  xor     rax, rsp
0x1800519db  mov     [rsp+258h+var_18], rax
0x1800519e3  mov     rdi, rdx
0x1800519e6  lea     rcx, [rsp+258h+Buffer]; void *
0x1800519eb  xor     edx, edx; Val
0x1800519ed  mov     r8d, 208h; Size
0x1800519f3  call    memset_0
0x1800519f8  mov     [rsp+258h+pcchLength], 0
0x180051a01  test    rdi, rdi
0x180051a04  jnz     short loc_180051A13
0x180051a06  mov     ebx, 80070057h
0x180051a0b  mov     [rdi], rdi
0x180051a0e  jmp     loc_180051AFC
0x180051a13  lea     rdx, asc_180082C18; "\\"
0x180051a1a  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x180051a21  call    cs:__imp_wcsstr
0x180051a28  nop     dword ptr [rax+rax+00h]
0x180051a2d  mov     qword ptr [rdi], 0
0x180051a34  test    rax, rax
0x180051a37  jz      short loc_180051A43
0x180051a39  mov     ebx, 80070057h
0x180051a3e  jmp     loc_180051AFC
0x180051a43  lea     r8, [rsp+258h+pcchLength]; pcchLength
0x180051a48  mov     edx, 103h; cchMax
0x180051a4d  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x180051a54  call    StringCchLengthW
0x180051a59  mov     ebx, eax
0x180051a5b  test    eax, eax
0x180051a5d  js      loc_180051AFC
0x180051a63  mov     ebx, 104h
0x180051a68  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180051a6d  mov     edx, ebx; uSize
0x180051a6f  call    cs:__imp_GetSystemDirectoryW
0x180051a76  nop     dword ptr [rax+rax+00h]
0x180051a7b  mov     r9d, eax
0x180051a7e  lea     rax, [r9-1]
0x180051a82  cmp     rax, 101h
0x180051a88  ja      short loc_180051AF7
0x180051a8a  mov     rcx, [rsp+258h+pcchLength]
0x180051a8f  add     rcx, r9
0x180051a92  cmp     rcx, 103h
0x180051a99  jnb     short loc_180051AF7
0x180051a9b  mov     eax, 5Ch ; '\'
0x180051aa0  lea     r8, aWinspoolDrv_0; "winspool.drv"
0x180051aa7  mov     edx, ebx; cchDest
0x180051aa9  mov     [rsp+r9*2+258h+Buffer], ax
0x180051aaf  lea     rcx, [rsp+258h+Buffer]; pszDest
0x180051ab4  call    StringCchCatW
0x180051ab9  mov     ebx, eax
0x180051abb  test    eax, eax
0x180051abd  js      short loc_180051AFC
0x180051abf  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x180051ac4  call    cs:__imp_LoadLibraryW
0x180051acb  nop     dword ptr [rax+rax+00h]
0x180051ad0  test    rax, rax
0x180051ad3  jnz     short loc_180051AF2
0x180051ad5  call    cs:__imp_GetLastError
0x180051adc  nop     dword ptr [rax+rax+00h]
0x180051ae1  mov     ebx, eax
0x180051ae3  test    eax, eax
0x180051ae5  jle     short loc_180051AFC
0x180051ae7  movzx   ebx, ax
0x180051aea  or      ebx, 80070000h
0x180051af0  jmp     short loc_180051AFC
0x180051af2  mov     [rdi], rax
0x180051af5  jmp     short loc_180051AFC
0x180051af7  mov     ebx, 80004005h
0x180051afc  mov     eax, ebx
0x180051afe  mov     rcx, [rsp+258h+var_18]
0x180051b06  xor     rcx, rsp; StackCookie
0x180051b09  call    __security_check_cookie
0x180051b0e  mov     rbx, [rsp+258h+arg_0]
0x180051b16  add     rsp, 250h
0x180051b1d  pop     rdi
0x180051b1e  retn
```
