# __std_fs_remove(x)

- ea: `0x40c9a0`
- end: `0x40cb40`
- name: `___std_fs_remove@4`
- size: `416`
- prototype: `int __stdcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x408ff9`

## callees

- `0x40b3e3`
- `0x40c40f`
- `0x40c4a8`
- `0x40c96c`
- `0x40c9a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40ca33`
- `KERNEL32!GetLastError` at `0x40ca82`
- `KERNEL32!GetLastError` at `0x40cae0`
- `KERNEL32!GetLastError` at `0x40ca33`
- `KERNEL32!GetLastError` at `0x40ca82`
- `KERNEL32!GetLastError` at `0x40cae0`
- `KERNEL32!SetFileInformationByHandle` at `0x40ca1c`
- `KERNEL32!SetFileInformationByHandle` at `0x40caa1`
- `KERNEL32!SetFileInformationByHandle` at `0x40cacb`
- `KERNEL32!SetFileInformationByHandle` at `0x40ca1c`
- `KERNEL32!SetFileInformationByHandle` at `0x40caa1`
- `KERNEL32!SetFileInformationByHandle` at `0x40cacb`
- `KERNEL32!GetFileInformationByHandleEx` at `0x40ca75`
- `KERNEL32!GetFileInformationByHandleEx` at `0x40ca75`

## pseudocode

```c
int __stdcall __std_fs_remove(LPCWSTR lpFileName)
{
  DWORD v1; // esi
  char v2; // bl
  HANDLE v3; // edi
  DWORD LastError; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  BOOL v7; // eax
  int v8; // esi
  int FileInformation; // [esp+Ch] [ebp-40h] BYREF
  HANDLE hFile; // [esp+10h] [ebp-3Ch] BYREF
  char v12; // [esp+17h] [ebp-35h]
  int v13; // [esp+18h] [ebp-34h]
  _BYTE v14[32]; // [esp+20h] [ebp-2Ch] BYREF
  int v15; // [esp+40h] [ebp-Ch]

  v12 = 0;
  v1 = __std_fs_open_handle(&hFile, lpFileName, 0x10180u, 0x2200000u);
  if ( v1 )
  {
    if ( v1 != 5 )
    {
      LOBYTE(v13) = 0;
      __std_fs_close_handle(hFile);
      return v13;
    }
    if ( __std_fs_open_handle(&hFile, lpFileName, 0x10000u, 0x2200000u) )
    {
      v3 = hFile;
      goto LABEL_27;
    }
    v2 = v12;
  }
  else
  {
    v2 = 1;
  }
  v3 = hFile;
  FileInformation = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
  {
LABEL_8:
    LOBYTE(v13) = 1;
LABEL_28:
    v8 = v13;
    __std_fs_close_handle(v3);
    return v8;
  }
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
    goto LABEL_27;
  v5 = `anonymous namespace'::_Set_delete_flag(v3);
  if ( !v5 )
    goto LABEL_8;
  if ( v5 != 5 || !v2 )
  {
LABEL_27:
    LOBYTE(v13) = 0;
    goto LABEL_28;
  }
  if ( !GetFileInformationByHandleEx(v3, FileBasicInfo, v14, 0x28u) )
    goto LABEL_16;
  if ( (v15 & 1) == 0 )
  {
    LOBYTE(v13) = 0;
    goto LABEL_28;
  }
  v15 ^= 1u;
  if ( !SetFileInformationByHandle(v3, FileBasicInfo, v14, 0x28u) )
  {
LABEL_16:
    LOBYTE(v13) = 0;
LABEL_17:
    GetLastError();
    goto LABEL_28;
  }
  v6 = `anonymous namespace'::_Set_delete_flag(v3);
  if ( !v6 )
  {
    LOBYTE(v13) = 1;
    goto LABEL_28;
  }
  if ( v6 == 5 )
  {
    v15 |= 1u;
    v7 = SetFileInformationByHandle(v3, FileBasicInfo, v14, 0x28u);
    LOBYTE(v13) = 0;
    if ( v7 )
      goto LABEL_28;
    goto LABEL_17;
  }
  LOBYTE(v13) = 0;
  GetLastError();
  __std_fs_close_handle(v3);
  return v13;
}

```

## disassembly

```asm
0x40c9a0  push    ebp
0x40c9a1  mov     ebp, esp
0x40c9a3  sub     esp, 40h
0x40c9a6  mov     eax, ___security_cookie
0x40c9ab  xor     eax, ebp
0x40c9ad  mov     [ebp+var_4], eax
0x40c9b0  push    ebx
0x40c9b1  push    esi
0x40c9b2  push    edi
0x40c9b3  mov     edi, [ebp+lpFileName]
0x40c9b6  lea     eax, [ebp+hFile]
0x40c9b9  push    2200000h; dwFlagsAndAttributes
0x40c9be  push    10180h; dwDesiredAccess
0x40c9c3  push    edi; lpFileName
0x40c9c4  xor     ebx, ebx
0x40c9c6  push    eax; int
0x40c9c7  mov     [ebp+var_35], bl
0x40c9ca  call    ___std_fs_open_handle@16
0x40c9cf  mov     esi, eax
0x40c9d1  push    5
0x40c9d3  pop     eax
0x40c9d4  test    esi, esi
0x40c9d6  jnz     short loc_40C9DC
0x40c9d8  mov     bl, 1
0x40c9da  jmp     short loc_40CA09
0x40c9dc  cmp     esi, eax
0x40c9de  jnz     loc_40CB06
0x40c9e4  push    2200000h; dwFlagsAndAttributes
0x40c9e9  push    10000h; dwDesiredAccess
0x40c9ee  push    edi; lpFileName
0x40c9ef  lea     eax, [ebp+hFile]
0x40c9f2  push    eax; int
0x40c9f3  call    ___std_fs_open_handle@16
0x40c9f8  mov     ebx, eax
0x40c9fa  test    ebx, ebx
0x40c9fc  jz      short loc_40CA06
0x40c9fe  mov     edi, [ebp+hFile]
0x40ca01  jmp     loc_40CAF2
0x40ca06  mov     bl, [ebp+var_35]
0x40ca09  mov     edi, [ebp+hFile]
0x40ca0c  lea     eax, [ebp+FileInformation]
0x40ca0f  push    4; dwBufferSize
0x40ca11  push    eax; lpFileInformation
0x40ca12  push    15h; FileInformationClass
0x40ca14  push    edi; hFile
0x40ca15  mov     [ebp+FileInformation], 13h
0x40ca1c  call    ds:SetFileInformationByHandle
0x40ca22  test    eax, eax
0x40ca24  jz      short loc_40CA33
0x40ca26  xor     ecx, ecx
0x40ca28  mov     byte ptr [ebp+var_34], 1
0x40ca2c  mov     ebx, ecx
0x40ca2e  jmp     loc_40CAF7
0x40ca33  call    ds:GetLastError
0x40ca39  mov     ecx, eax
0x40ca3b  sub     ecx, 1
0x40ca3e  jz      short loc_40CA4E
0x40ca40  sub     ecx, 31h ; '1'
0x40ca43  jz      short loc_40CA4E
0x40ca45  sub     ecx, 25h ; '%'
0x40ca48  jnz     loc_40CAF0
0x40ca4e  push    edi
0x40ca4f  call    ?_Set_delete_flag@?A0xf5c61f79@@YG?AW4__std_win_error@@W4__std_fs_file_handle@@@Z
0x40ca54  test    eax, eax
0x40ca56  jz      short loc_40CA26
0x40ca58  push    5
0x40ca5a  pop     esi
0x40ca5b  cmp     eax, esi
0x40ca5d  jnz     loc_40CAF0
0x40ca63  test    bl, bl
0x40ca65  jz      loc_40CAF0
0x40ca6b  push    28h ; '('; dwBufferSize
0x40ca6d  lea     eax, [ebp+var_2C]
0x40ca70  xor     ebx, ebx
0x40ca72  push    eax; lpFileInformation
0x40ca73  push    ebx; FileInformationClass
0x40ca74  push    edi; hFile
0x40ca75  call    ds:GetFileInformationByHandleEx
0x40ca7b  test    eax, eax
0x40ca7d  jnz     short loc_40CA8C
0x40ca7f  mov     byte ptr [ebp+var_34], bl
0x40ca82  call    ds:GetLastError
0x40ca88  mov     ebx, eax
0x40ca8a  jmp     short loc_40CAF7
0x40ca8c  mov     eax, [ebp+var_C]
0x40ca8f  test    al, 1
0x40ca91  jz      short loc_40CAEB
0x40ca93  xor     eax, 1
0x40ca96  push    28h ; '('; dwBufferSize
0x40ca98  mov     [ebp+var_C], eax
0x40ca9b  lea     eax, [ebp+var_2C]
0x40ca9e  push    eax; lpFileInformation
0x40ca9f  push    ebx; FileInformationClass
0x40caa0  push    edi; hFile
0x40caa1  call    ds:SetFileInformationByHandle
0x40caa7  test    eax, eax
0x40caa9  jz      short loc_40CA7F
0x40caab  push    edi
0x40caac  call    ?_Set_delete_flag@?A0xf5c61f79@@YG?AW4__std_win_error@@W4__std_fs_file_handle@@@Z
0x40cab1  test    eax, eax
0x40cab3  jnz     short loc_40CABB
0x40cab5  mov     byte ptr [ebp+var_34], 1
0x40cab9  jmp     short loc_40CAF7
0x40cabb  cmp     eax, esi
0x40cabd  jnz     short loc_40CADD
0x40cabf  or      [ebp+var_C], 1
0x40cac3  lea     eax, [ebp+var_2C]
0x40cac6  push    28h ; '('; dwBufferSize
0x40cac8  push    eax; lpFileInformation
0x40cac9  push    ebx; FileInformationClass
0x40caca  push    edi; hFile
0x40cacb  call    ds:SetFileInformationByHandle
0x40cad1  mov     byte ptr [ebp+var_34], bl
0x40cad4  test    eax, eax
0x40cad6  jz      short loc_40CA82
0x40cad8  push    5
0x40cada  pop     ebx
0x40cadb  jmp     short loc_40CAF7
0x40cadd  mov     byte ptr [ebp+var_34], bl
0x40cae0  call    ds:GetLastError
0x40cae6  mov     esi, eax
0x40cae8  push    edi
0x40cae9  jmp     short loc_40CB25
0x40caeb  mov     byte ptr [ebp+var_34], bl
0x40caee  jmp     short loc_40CAD8
0x40caf0  mov     ebx, eax
0x40caf2  xor     ecx, ecx
0x40caf4  mov     byte ptr [ebp+var_34], cl
0x40caf7  mov     esi, [ebp+var_34]
0x40cafa  push    edi; hObject
0x40cafb  call    ___std_fs_close_handle@4
0x40cb00  mov     eax, esi
0x40cb02  mov     edx, ebx
0x40cb04  jmp     short loc_40CB2F
0x40cb06  lea     eax, [esi-1]
0x40cb09  mov     byte ptr [ebp+var_34], bl
0x40cb0c  sub     eax, 1
0x40cb0f  jz      short loc_40CB20
0x40cb11  sub     eax, 1
0x40cb14  jz      short loc_40CB20
0x40cb16  sub     eax, 32h ; '2'
0x40cb19  jz      short loc_40CB20
0x40cb1b  sub     eax, 46h ; 'F'
0x40cb1e  jnz     short loc_40CB22
0x40cb20  mov     esi, ebx
0x40cb22  push    [ebp+hFile]; hObject
0x40cb25  call    ___std_fs_close_handle@4
0x40cb2a  mov     eax, [ebp+var_34]
0x40cb2d  mov     edx, esi
0x40cb2f  mov     ecx, [ebp+var_4]
0x40cb32  pop     edi
0x40cb33  pop     esi
0x40cb34  xor     ecx, ebp; StackCookie
0x40cb36  pop     ebx
0x40cb37  call    @__security_check_cookie@4
0x40cb3c  leave
0x40cb3d  retn    4
```
