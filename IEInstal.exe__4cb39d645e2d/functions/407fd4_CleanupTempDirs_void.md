# CleanupTempDirs(void)

- ea: `0x407fd4`
- end: `0x40819f`
- name: `?CleanupTempDirs@@YGJXZ`
- size: `459`
- prototype: `int __stdcall()`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x409212`

## callees

- `0x406224`
- `0x406266`
- `0x40646b`
- `0x4072e3`
- `0x407fd4`
- `0x40cb60`

## import_xrefs

- `KERNEL32!SetFileAttributesA` at `0x408136`
- `KERNEL32!SetFileAttributesA` at `0x408136`
- `KERNEL32!FindFirstFileA` at `0x40806e`
- `KERNEL32!FindFirstFileA` at `0x40806e`
- `KERNEL32!FindNextFileA` at `0x408154`
- `KERNEL32!FindNextFileA` at `0x408154`
- `KERNEL32!FindClose` at `0x408182`
- `KERNEL32!FindClose` at `0x408182`
- `KERNEL32!lstrcmpA` at `0x408085`
- `KERNEL32!lstrcmpA` at `0x40809d`
- `KERNEL32!lstrcmpA` at `0x408085`
- `KERNEL32!lstrcmpA` at `0x40809d`
- `KERNEL32!GetTempPath2A` at `0x408001`
- `KERNEL32!GetTempPath2A` at `0x408001`
- `KERNEL32!GetLastError` at `0x40800b`
- `KERNEL32!GetLastError` at `0x408162`
- `KERNEL32!GetLastError` at `0x40816d`
- `KERNEL32!GetLastError` at `0x40800b`
- `KERNEL32!GetLastError` at `0x408162`
- `KERNEL32!GetLastError` at `0x40816d`

## pseudocode

```c
int __stdcall CleanupTempDirs()
{
  signed int LastError; // eax
  signed int v1; // esi
  HANDLE FirstFileA; // edi
  signed int v3; // eax
  unsigned int *v5; // [esp+0h] [ebp-370h]
  unsigned int *v6; // [esp+0h] [ebp-370h]
  unsigned int v7; // [esp+4h] [ebp-36Ch]
  unsigned int v8; // [esp+4h] [ebp-36Ch]
  char v9[4]; // [esp+10h] [ebp-360h] BYREF
  char *v10; // [esp+14h] [ebp-35Ch] BYREF
  struct _WIN32_FIND_DATAA FindFileData; // [esp+18h] [ebp-358h] BYREF
  CHAR FileName[264]; // [esp+158h] [ebp-218h] BYREF
  char cchDest[268]; // [esp+260h] [ebp-110h] BYREF

  if ( !GetTempPath2A(260, cchDest) )
    goto LABEL_2;
  v1 = StringCchCopyA(FileName, 0x104u, (size_t)cchDest);
  if ( v1 < 0 )
    return v1;
  v1 = StringCchCatA(FileName, 0x104u, "IDC*");
  if ( v1 < 0 )
    return v1;
  FirstFileA = FindFirstFileA(FileName, &FindFileData);
  if ( FirstFileA == (HANDLE)-1 )
  {
LABEL_2:
    LastError = GetLastError();
    v1 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return LastError;
  }
  else
  {
    while ( 1 )
    {
      if ( lstrcmpA(FindFileData.cFileName, ".") )
      {
        if ( lstrcmpA(FindFileData.cFileName, "..") )
        {
          *(_DWORD *)v9 = 260;
          v10 = FileName;
          v1 = StringCchCopyExA(cchDest, (unsigned int)&v10, v9, 0, v5, v7);
          if ( v1 < 0 )
            break;
          v1 = StringCchCopyExA("\\", (unsigned int)&v10, v9, 0, v6, v8);
          if ( v1 < 0 )
            break;
          v1 = StringCchCopyA(v10, *(unsigned int *)v9, (size_t)FindFileData.cFileName);
          if ( v1 < 0 )
            break;
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            SetFileAttributesA(FileName, 0x90u);
            v1 = RemoveDirectoryAndChildren((const char *)v5);
            if ( v1 < 0 )
              break;
          }
        }
      }
      if ( !FindNextFileA(FirstFileA, &FindFileData) )
      {
        if ( GetLastError() != 18 )
        {
          v3 = GetLastError();
          v1 = (unsigned __int16)v3 | 0x80070000;
          if ( v3 <= 0 )
            v1 = v3;
        }
        break;
      }
    }
    FindClose(FirstFileA);
  }
  return v1;
}

```

## disassembly

```asm
0x407fd4  mov     edi, edi
0x407fd6  push    ebp
0x407fd7  mov     ebp, esp
0x407fd9  and     esp, 0FFFFFFF8h
0x407fdc  sub     esp, 364h
0x407fe2  mov     eax, ___security_cookie
0x407fe7  xor     eax, esp
0x407fe9  mov     [esp+364h+var_4], eax
0x407ff0  push    ebx
0x407ff1  push    esi; unsigned int
0x407ff2  push    edi; char *
0x407ff3  lea     eax, [esp+370h+cchDest]
0x407ffa  mov     ebx, 104h
0x407fff  push    eax
0x408000  push    ebx
0x408001  call    ds:__imp__GetTempPath2A@8; GetTempPath2A(x,x)
0x408007  test    eax, eax
0x408009  jnz     short loc_408024
0x40800b  call    ds:__imp__GetLastError@0; GetLastError()
0x408011  movzx   esi, ax
0x408014  or      esi, 80070000h
0x40801a  test    eax, eax
0x40801c  cmovle  esi, eax
0x40801f  jmp     loc_408188
0x408024  lea     eax, [esp+370h+cchDest]
0x40802b  push    eax; cchDest
0x40802c  push    ebx; unsigned int
0x40802d  lea     eax, [esp+378h+FileName]
0x408034  push    eax; char *
0x408035  call    ?StringCchCopyA@@YGJPADIPBD@Z; StringCchCopyA(char *,uint,char const *)
0x40803a  mov     esi, eax
0x40803c  test    esi, esi
0x40803e  js      loc_408188
0x408044  push    offset aIdc; "IDC*"
0x408049  push    ebx; unsigned int
0x40804a  lea     eax, [esp+378h+FileName]
0x408051  push    eax; char *
0x408052  call    ?StringCchCatA@@YGJPADIPBD@Z; StringCchCatA(char *,uint,char const *)
0x408057  mov     esi, eax
0x408059  test    esi, esi
0x40805b  js      loc_408188
0x408061  lea     eax, [esp+370h+FindFileData]
0x408065  push    eax; lpFindFileData
0x408066  lea     eax, [esp+374h+FileName]
0x40806d  push    eax; lpFileName
0x40806e  call    ds:__imp__FindFirstFileA@8; FindFirstFileA(x,x)
0x408074  mov     edi, eax
0x408076  cmp     edi, 0FFFFFFFFh
0x408079  jz      short loc_40800B
0x40807b  push    offset String2; "."
0x408080  lea     eax, [esp+374h+FindFileData.cFileName]
0x408084  push    eax; lpString1
0x408085  call    ds:__imp__lstrcmpA@8; lstrcmpA(x,x)
0x40808b  test    eax, eax
0x40808d  jz      loc_40814E
0x408093  push    offset asc_4019F4; ".."
0x408098  lea     eax, [esp+374h+FindFileData.cFileName]
0x40809c  push    eax; lpString1
0x40809d  call    ds:__imp__lstrcmpA@8; lstrcmpA(x,x)
0x4080a3  test    eax, eax
0x4080a5  jz      loc_40814E
0x4080ab  lea     eax, [esp+370h+FileName]
0x4080b2  mov     dword ptr [esp+370h+var_360], ebx
0x4080b6  mov     [esp+370h+var_35C], eax
0x4080ba  lea     ecx, [esp+370h+FileName]
0x4080c1  push    0; char **
0x4080c3  lea     eax, [esp+374h+var_360]
0x4080c7  mov     edx, ebx
0x4080c9  push    eax; char *
0x4080ca  lea     eax, [esp+378h+var_35C]
0x4080ce  push    eax; unsigned int
0x4080cf  lea     eax, [esp+37Ch+cchDest]
0x4080d6  push    eax; char *
0x4080d7  call    ?StringCchCopyExA@@YGJPADIPBDPAPADPAIK@Z; StringCchCopyExA(char *,uint,char const *,char * *,uint *,ulong)
0x4080dc  mov     esi, eax
0x4080de  test    esi, esi
0x4080e0  js      loc_408181
0x4080e6  mov     edx, dword ptr [esp+370h+var_360]
0x4080ea  lea     eax, [esp+370h+var_360]
0x4080ee  mov     ecx, [esp+370h+var_35C]
0x4080f2  push    0; char **
0x4080f4  push    eax; char *
0x4080f5  lea     eax, [esp+378h+var_35C]
0x4080f9  push    eax; unsigned int
0x4080fa  push    offset asc_401A5C; "\\"
0x4080ff  call    ?StringCchCopyExA@@YGJPADIPBDPAPADPAIK@Z; StringCchCopyExA(char *,uint,char const *,char * *,uint *,ulong)
0x408104  mov     esi, eax
0x408106  test    esi, esi
0x408108  js      short loc_408181
0x40810a  lea     eax, [esp+370h+FindFileData.cFileName]
0x40810e  push    eax; cchDest
0x40810f  push    dword ptr [esp+374h+var_360]; unsigned int
0x408113  push    [esp+378h+var_35C]; char *
0x408117  call    ?StringCchCopyA@@YGJPADIPBD@Z; StringCchCopyA(char *,uint,char const *)
0x40811c  mov     esi, eax
0x40811e  test    esi, esi
0x408120  js      short loc_408181
0x408122  test    byte ptr [esp+370h+FindFileData.dwFileAttributes], 10h
0x408127  jz      short loc_40814E
0x408129  push    90h; dwFileAttributes
0x40812e  lea     eax, [esp+374h+FileName]
0x408135  push    eax; lpFileName
0x408136  call    ds:__imp__SetFileAttributesA@8; SetFileAttributesA(x,x)
0x40813c  lea     ecx, [esp+370h+FileName]
0x408143  call    ?RemoveDirectoryAndChildren@@YGJPBD@Z; RemoveDirectoryAndChildren(char const *)
0x408148  mov     esi, eax
0x40814a  test    esi, esi
0x40814c  js      short loc_408181
0x40814e  lea     eax, [esp+370h+FindFileData]
0x408152  push    eax; lpFindFileData
0x408153  push    edi; hFindFile
0x408154  call    ds:__imp__FindNextFileA@8; FindNextFileA(x,x)
0x40815a  test    eax, eax
0x40815c  jnz     loc_40807B
0x408162  call    ds:__imp__GetLastError@0; GetLastError()
0x408168  cmp     eax, 12h
0x40816b  jz      short loc_408181
0x40816d  call    ds:__imp__GetLastError@0; GetLastError()
0x408173  movzx   esi, ax
0x408176  or      esi, 80070000h
0x40817c  test    eax, eax
0x40817e  cmovle  esi, eax
0x408181  push    edi; hFindFile
0x408182  call    ds:__imp__FindClose@4; FindClose(x)
0x408188  mov     ecx, [esp+370h+var_4]
0x40818f  mov     eax, esi
0x408191  pop     edi
0x408192  pop     esi
0x408193  pop     ebx
0x408194  xor     ecx, esp; StackCookie
0x408196  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40819b  mov     esp, ebp
0x40819d  pop     ebp
0x40819e  retn
```
