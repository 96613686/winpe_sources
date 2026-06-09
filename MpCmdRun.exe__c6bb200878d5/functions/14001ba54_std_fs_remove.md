# __std_fs_remove

- ea: `0x14001ba54`
- end: `0x14001bc81`
- name: `__std_fs_remove`
- size: `557`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1400969cc`
- `0x14009ded4`

## callees

- `0x14001b498`
- `0x14001b9fc`
- `0x14001ba54`
- `0x140036780`
- `0x14005d8f4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001bb44`
- `KERNEL32!GetLastError` at `0x14001bb9e`
- `KERNEL32!GetLastError` at `0x14001bc36`
- `KERNEL32!GetLastError` at `0x14001bb44`
- `KERNEL32!GetLastError` at `0x14001bb9e`
- `KERNEL32!GetLastError` at `0x14001bc36`
- `KERNEL32!CloseHandle` at `0x14001bb10`
- `KERNEL32!CloseHandle` at `0x14001bbb4`
- `KERNEL32!CloseHandle` at `0x14001bb10`
- `KERNEL32!CloseHandle` at `0x14001bbb4`
- `KERNEL32!SetFileInformationByHandle` at `0x14001babe`
- `KERNEL32!SetFileInformationByHandle` at `0x14001bbe0`
- `KERNEL32!SetFileInformationByHandle` at `0x14001bc14`
- `KERNEL32!SetFileInformationByHandle` at `0x14001babe`
- `KERNEL32!SetFileInformationByHandle` at `0x14001bbe0`
- `KERNEL32!SetFileInformationByHandle` at `0x14001bc14`
- `KERNEL32!GetFileInformationByHandleEx` at `0x14001bb90`
- `KERNEL32!GetFileInformationByHandleEx` at `0x14001bb90`

## pseudocode

```c
__int64 __fastcall _std_fs_remove(const WCHAR *a1)
{
  char v2; // di
  int v3; // eax
  int v4; // ecx
  HANDLE v5; // rbx
  HANDLE v6; // rcx
  int v7; // eax
  DWORD LastError; // eax
  DWORD v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // [rsp+20h] [rbp-50h]
  HANDLE hFile; // [rsp+28h] [rbp-48h] BYREF
  int FileInformation; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-38h] BYREF
  int v20; // [rsp+58h] [rbp-18h]

  v2 = 0;
  v3 = _std_fs_open_handle(&hFile, a1, 0x10180u, 0x2200000u);
  v4 = v3;
  if ( !v3 )
  {
    v2 = 1;
    goto LABEL_3;
  }
  if ( v3 != 5 )
  {
    LOBYTE(v16) = 0;
    v11 = v3 - 2;
    if ( !v11
      || (v12 = v11 - 1) == 0
      || (v13 = v12 - 50) == 0
      || (v14 = v13 - 11) == 0
      || (v15 = v14 - 59) == 0
      || v15 == 144 )
    {
      v4 = 0;
    }
    HIDWORD(v16) = v4;
LABEL_10:
    v6 = hFile;
    if ( hFile == (HANDLE)-1LL )
      return v16;
LABEL_11:
    if ( !CloseHandle(v6) )
      abort();
    return v16;
  }
  v7 = _std_fs_open_handle(&hFile, a1, 0x10000u, 0x2200000u);
  if ( v7 )
  {
    LOBYTE(v16) = 0;
    HIDWORD(v16) = v7;
    goto LABEL_10;
  }
LABEL_3:
  v5 = hFile;
  FileInformation = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
  {
LABEL_4:
    LOBYTE(v16) = 1;
    HIDWORD(v16) = 0;
LABEL_5:
    if ( v5 == (HANDLE)-1LL )
      return v16;
    v6 = v5;
    goto LABEL_11;
  }
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
    goto LABEL_16;
  LastError = `anonymous namespace'::_Set_delete_flag(v5);
  if ( !LastError )
    goto LABEL_4;
  if ( LastError != 5 || !v2 )
  {
LABEL_16:
    LOBYTE(v16) = 0;
    goto LABEL_17;
  }
  if ( GetFileInformationByHandleEx(v5, FileBasicInfo, v19, 0x28u) )
  {
    if ( (v20 & 1) == 0 )
    {
      LOBYTE(v16) = 0;
      goto LABEL_33;
    }
    v20 ^= 1u;
    if ( !SetFileInformationByHandle(v5, FileBasicInfo, v19, 0x28u) )
      goto LABEL_22;
    v10 = `anonymous namespace'::_Set_delete_flag(v5);
    if ( !v10 )
    {
      LOBYTE(v16) = 1;
      HIDWORD(v16) = 0;
      goto LABEL_24;
    }
    if ( v10 == 5 )
    {
      v20 |= 1u;
      LOBYTE(v16) = 0;
      if ( !SetFileInformationByHandle(v5, FileBasicInfo, v19, 0x28u) )
        goto LABEL_23;
LABEL_33:
      HIDWORD(v16) = 5;
      goto LABEL_24;
    }
    LOBYTE(v16) = 0;
    LastError = GetLastError();
LABEL_17:
    HIDWORD(v16) = LastError;
    goto LABEL_5;
  }
LABEL_22:
  LOBYTE(v16) = 0;
LABEL_23:
  HIDWORD(v16) = GetLastError();
LABEL_24:
  if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
    abort();
  return v16;
}

```

## disassembly

```asm
0x14001ba54  mov     [rsp-8+arg_8], rbx
0x14001ba59  mov     [rsp-8+arg_10], rsi
0x14001ba5e  mov     [rsp-8+arg_18], rdi
0x14001ba63  push    rbp
0x14001ba64  mov     rbp, rsp
0x14001ba67  sub     rsp, 70h
0x14001ba6b  mov     rax, cs:__security_cookie
0x14001ba72  xor     rax, rsp
0x14001ba75  mov     [rbp+var_10], rax
0x14001ba79  mov     rbx, rcx
0x14001ba7c  mov     rdx, rcx
0x14001ba7f  xor     esi, esi
0x14001ba81  lea     rcx, [rbp+hFile]
0x14001ba85  mov     r9d, 2200000h
0x14001ba8b  mov     r8d, 10180h
0x14001ba91  mov     dil, sil
0x14001ba94  call    __std_fs_open_handle
0x14001ba99  mov     ecx, eax
0x14001ba9b  test    eax, eax
0x14001ba9d  jnz     short loc_14001BADA
0x14001ba9f  mov     dil, 1
0x14001baa2  mov     rbx, [rbp+hFile]
0x14001baa6  lea     r8, [rbp+FileInformation]; lpFileInformation
0x14001baaa  mov     r9d, 4; dwBufferSize
0x14001bab0  mov     [rbp+FileInformation], 13h
0x14001bab7  mov     rcx, rbx; hFile
0x14001baba  lea     edx, [r9+11h]; FileInformationClass
0x14001babe  call    cs:SetFileInformationByHandle
0x14001bac4  test    eax, eax
0x14001bac6  jz      short loc_14001BB44
0x14001bac8  mov     byte ptr [rbp+var_50], 1
0x14001bacc  mov     dword ptr [rbp+var_50+4], esi
0x14001bacf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14001bad3  jz      short loc_14001BB1E
0x14001bad5  mov     rcx, rbx
0x14001bad8  jmp     short loc_14001BB10
0x14001bada  cmp     eax, 5
0x14001badd  jnz     loc_14001BC47
0x14001bae3  mov     r9d, 2200000h
0x14001bae9  lea     rcx, [rbp+hFile]
0x14001baed  mov     r8d, 10000h
0x14001baf3  mov     rdx, rbx
0x14001baf6  call    __std_fs_open_handle
0x14001bafb  test    eax, eax
0x14001bafd  jz      short loc_14001BAA2
0x14001baff  mov     byte ptr [rbp+var_50], sil
0x14001bb03  mov     dword ptr [rbp+var_50+4], eax
0x14001bb06  mov     rcx, [rbp+hFile]; hObject
0x14001bb0a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001bb0e  jz      short loc_14001BB1E
0x14001bb10  call    cs:__imp_CloseHandle
0x14001bb16  test    eax, eax
0x14001bb18  jz      loc_14001BC75
0x14001bb1e  mov     rax, [rbp+var_50]
0x14001bb22  mov     rcx, [rbp+var_10]
0x14001bb26  xor     rcx, rsp; StackCookie
0x14001bb29  call    __security_check_cookie
0x14001bb2e  lea     r11, [rsp+70h+var_s0]
0x14001bb33  mov     rbx, [r11+18h]
0x14001bb37  mov     rsi, [r11+20h]
0x14001bb3b  mov     rdi, [r11+28h]
0x14001bb3f  mov     rsp, r11
0x14001bb42  pop     rbp
0x14001bb43  retn
0x14001bb44  call    cs:GetLastError
0x14001bb4a  mov     ecx, eax
0x14001bb4c  sub     ecx, 1
0x14001bb4f  jz      short loc_14001BB67
0x14001bb51  sub     ecx, 31h ; '1'
0x14001bb54  jz      short loc_14001BB67
0x14001bb56  cmp     ecx, 25h ; '%'
0x14001bb59  jz      short loc_14001BB67
0x14001bb5b  mov     byte ptr [rbp+var_50], sil
0x14001bb5f  mov     dword ptr [rbp+var_50+4], eax
0x14001bb62  jmp     loc_14001BACF
0x14001bb67  mov     rcx, rbx
0x14001bb6a  call    ?_Set_delete_flag@?A0x4361391f@@YA?AW4__std_win_error@@W4__std_fs_file_handle@@@Z
0x14001bb6f  test    eax, eax
0x14001bb71  jz      loc_14001BAC8
0x14001bb77  cmp     eax, 5
0x14001bb7a  jnz     short loc_14001BB5B
0x14001bb7c  test    dil, dil
0x14001bb7f  jz      short loc_14001BB5B
0x14001bb81  lea     edi, [rax+23h]
0x14001bb84  xor     edx, edx; FileInformationClass
0x14001bb86  mov     r9d, edi; dwBufferSize
0x14001bb89  lea     r8, [rbp+var_38]; lpFileInformation
0x14001bb8d  mov     rcx, rbx; hFile
0x14001bb90  call    cs:GetFileInformationByHandleEx
0x14001bb96  test    eax, eax
0x14001bb98  jnz     short loc_14001BBC7
0x14001bb9a  mov     byte ptr [rbp+var_50], sil
0x14001bb9e  call    cs:GetLastError
0x14001bba4  mov     dword ptr [rbp+var_50+4], eax
0x14001bba7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14001bbab  jz      loc_14001BB1E
0x14001bbb1  mov     rcx, rbx; hObject
0x14001bbb4  call    cs:__imp_CloseHandle
0x14001bbba  test    eax, eax
0x14001bbbc  jz      loc_14001BC7B
0x14001bbc2  jmp     loc_14001BB1E
0x14001bbc7  mov     eax, [rbp+var_18]
0x14001bbca  test    al, 1
0x14001bbcc  jz      short loc_14001BC41
0x14001bbce  xor     eax, 1
0x14001bbd1  lea     r8, [rbp+var_38]; lpFileInformation
0x14001bbd5  mov     r9d, edi; dwBufferSize
0x14001bbd8  mov     [rbp+var_18], eax
0x14001bbdb  xor     edx, edx; FileInformationClass
0x14001bbdd  mov     rcx, rbx; hFile
0x14001bbe0  call    cs:SetFileInformationByHandle
0x14001bbe6  test    eax, eax
0x14001bbe8  jz      short loc_14001BB9A
0x14001bbea  mov     rcx, rbx
0x14001bbed  call    ?_Set_delete_flag@?A0x4361391f@@YA?AW4__std_win_error@@W4__std_fs_file_handle@@@Z
0x14001bbf2  test    eax, eax
0x14001bbf4  jnz     short loc_14001BBFF
0x14001bbf6  mov     byte ptr [rbp+var_50], 1
0x14001bbfa  mov     dword ptr [rbp+var_50+4], esi
0x14001bbfd  jmp     short loc_14001BBA7
0x14001bbff  cmp     eax, 5
0x14001bc02  jnz     short loc_14001BC32
0x14001bc04  or      [rbp+var_18], 1
0x14001bc08  lea     r8, [rbp+var_38]; lpFileInformation
0x14001bc0c  mov     r9d, edi; dwBufferSize
0x14001bc0f  xor     edx, edx; FileInformationClass
0x14001bc11  mov     rcx, rbx; hFile
0x14001bc14  call    cs:SetFileInformationByHandle
0x14001bc1a  mov     byte ptr [rbp+var_50], sil
0x14001bc1e  test    eax, eax
0x14001bc20  jz      loc_14001BB9E
0x14001bc26  mov     dword ptr [rbp+var_50+4], 5
0x14001bc2d  jmp     loc_14001BBA7
0x14001bc32  mov     byte ptr [rbp+var_50], sil
0x14001bc36  call    cs:GetLastError
0x14001bc3c  jmp     loc_14001BB5F
0x14001bc41  mov     byte ptr [rbp+var_50], sil
0x14001bc45  jmp     short loc_14001BC26
0x14001bc47  mov     byte ptr [rbp+var_50], sil
0x14001bc4b  sub     eax, 2
0x14001bc4e  jz      short loc_14001BC6B
0x14001bc50  sub     eax, 1
0x14001bc53  jz      short loc_14001BC6B
0x14001bc55  sub     eax, 32h ; '2'
0x14001bc58  jz      short loc_14001BC6B
0x14001bc5a  sub     eax, 0Bh
0x14001bc5d  jz      short loc_14001BC6B
0x14001bc5f  sub     eax, 3Bh ; ';'
0x14001bc62  jz      short loc_14001BC6B
0x14001bc64  cmp     eax, 90h
0x14001bc69  jnz     short loc_14001BC6D
0x14001bc6b  mov     ecx, esi
0x14001bc6d  mov     dword ptr [rbp+var_50+4], ecx
0x14001bc70  jmp     loc_14001BB06
0x14001bc75  call    abort
0x14001bc7b  call    abort
```
