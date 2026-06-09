# __std_fs_remove

- ea: `0x1403e3fec`
- end: `0x1403e4216`
- name: `__std_fs_remove`
- size: `554`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1401e8fdc`
- `0x1404e634c`
- `0x1404e64f0`
- `0x1406d6384`
- `0x1406deddc`

## callees

- `0x1403e1680`
- `0x1403e3270`
- `0x1403e3ed4`
- `0x1403e3fec`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1403e40a8`
- `KERNEL32!CloseHandle` at `0x1403e414c`
- `KERNEL32!CloseHandle` at `0x1403e40a8`
- `KERNEL32!CloseHandle` at `0x1403e414c`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1403e4128`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1403e4128`
- `KERNEL32!SetFileInformationByHandle` at `0x1403e4056`
- `KERNEL32!SetFileInformationByHandle` at `0x1403e417a`
- `KERNEL32!SetFileInformationByHandle` at `0x1403e41ae`
- `KERNEL32!SetFileInformationByHandle` at `0x1403e4056`
- `KERNEL32!SetFileInformationByHandle` at `0x1403e417a`
- `KERNEL32!SetFileInformationByHandle` at `0x1403e41ae`
- `KERNEL32!GetLastError` at `0x1403e40dc`
- `KERNEL32!GetLastError` at `0x1403e4136`
- `KERNEL32!GetLastError` at `0x1403e41d0`
- `KERNEL32!GetLastError` at `0x1403e40dc`
- `KERNEL32!GetLastError` at `0x1403e4136`
- `KERNEL32!GetLastError` at `0x1403e41d0`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1403e415a`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1403e420f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1403e415a`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1403e420f`

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
0x1403e3fec  mov     [rsp-8+arg_8], rbx
0x1403e3ff1  mov     [rsp-8+arg_10], rsi
0x1403e3ff6  mov     [rsp-8+arg_18], rdi
0x1403e3ffb  push    rbp
0x1403e3ffc  mov     rbp, rsp
0x1403e3fff  sub     rsp, 70h
0x1403e4003  mov     rax, cs:__security_cookie
0x1403e400a  xor     rax, rsp
0x1403e400d  mov     [rbp+var_10], rax
0x1403e4011  mov     rbx, rcx
0x1403e4014  mov     rdx, rcx
0x1403e4017  xor     esi, esi
0x1403e4019  lea     rcx, [rbp+hFile]
0x1403e401d  mov     r9d, 2200000h
0x1403e4023  mov     r8d, 10180h
0x1403e4029  mov     dil, sil
0x1403e402c  call    __std_fs_open_handle
0x1403e4031  mov     ecx, eax
0x1403e4033  test    eax, eax
0x1403e4035  jnz     short loc_1403E4072
0x1403e4037  mov     dil, 1
0x1403e403a  mov     rbx, [rbp+hFile]
0x1403e403e  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1403e4042  mov     r9d, 4; dwBufferSize
0x1403e4048  mov     [rbp+FileInformation], 13h
0x1403e404f  mov     rcx, rbx; hFile
0x1403e4052  lea     edx, [r9+11h]; FileInformationClass
0x1403e4056  call    cs:SetFileInformationByHandle
0x1403e405c  test    eax, eax
0x1403e405e  jz      short loc_1403E40DC
0x1403e4060  mov     byte ptr [rbp+var_50], 1
0x1403e4064  mov     dword ptr [rbp+var_50+4], esi
0x1403e4067  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1403e406b  jz      short loc_1403E40B6
0x1403e406d  mov     rcx, rbx
0x1403e4070  jmp     short loc_1403E40A8
0x1403e4072  cmp     eax, 5
0x1403e4075  jnz     loc_1403E41E1
0x1403e407b  mov     r9d, 2200000h
0x1403e4081  lea     rcx, [rbp+hFile]
0x1403e4085  mov     r8d, 10000h
0x1403e408b  mov     rdx, rbx
0x1403e408e  call    __std_fs_open_handle
0x1403e4093  test    eax, eax
0x1403e4095  jz      short loc_1403E403A
0x1403e4097  mov     byte ptr [rbp+var_50], sil
0x1403e409b  mov     dword ptr [rbp+var_50+4], eax
0x1403e409e  mov     rcx, [rbp+hFile]; hObject
0x1403e40a2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1403e40a6  jz      short loc_1403E40B6
0x1403e40a8  call    cs:__imp_CloseHandle
0x1403e40ae  test    eax, eax
0x1403e40b0  jz      loc_1403E420F
0x1403e40b6  mov     rax, [rbp+var_50]
0x1403e40ba  mov     rcx, [rbp+var_10]
0x1403e40be  xor     rcx, rsp; StackCookie
0x1403e40c1  call    __security_check_cookie
0x1403e40c6  lea     r11, [rsp+70h+var_s0]
0x1403e40cb  mov     rbx, [r11+18h]
0x1403e40cf  mov     rsi, [r11+20h]
0x1403e40d3  mov     rdi, [r11+28h]
0x1403e40d7  mov     rsp, r11
0x1403e40da  pop     rbp
0x1403e40db  retn
0x1403e40dc  call    cs:__imp_GetLastError
0x1403e40e2  mov     ecx, eax
0x1403e40e4  sub     ecx, 1
0x1403e40e7  jz      short loc_1403E40FF
0x1403e40e9  sub     ecx, 31h ; '1'
0x1403e40ec  jz      short loc_1403E40FF
0x1403e40ee  cmp     ecx, 25h ; '%'
0x1403e40f1  jz      short loc_1403E40FF
0x1403e40f3  mov     byte ptr [rbp+var_50], sil
0x1403e40f7  mov     dword ptr [rbp+var_50+4], eax
0x1403e40fa  jmp     loc_1403E4067
0x1403e40ff  mov     rcx, rbx
0x1403e4102  call    ?_Set_delete_flag@?A0x4361391f@@YA?AW4__std_win_error@@W4__std_fs_file_handle@@@Z
0x1403e4107  test    eax, eax
0x1403e4109  jz      loc_1403E4060
0x1403e410f  cmp     eax, 5
0x1403e4112  jnz     short loc_1403E40F3
0x1403e4114  test    dil, dil
0x1403e4117  jz      short loc_1403E40F3
0x1403e4119  lea     edi, [rax+23h]
0x1403e411c  xor     edx, edx; FileInformationClass
0x1403e411e  mov     r9d, edi; dwBufferSize
0x1403e4121  lea     r8, [rbp+var_38]; lpFileInformation
0x1403e4125  mov     rcx, rbx; hFile
0x1403e4128  call    cs:GetFileInformationByHandleEx
0x1403e412e  test    eax, eax
0x1403e4130  jnz     short loc_1403E4161
0x1403e4132  mov     byte ptr [rbp+var_50], sil
0x1403e4136  call    cs:__imp_GetLastError
0x1403e413c  mov     dword ptr [rbp+var_50+4], eax
0x1403e413f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1403e4143  jz      loc_1403E40B6
0x1403e4149  mov     rcx, rbx; hObject
0x1403e414c  call    cs:__imp_CloseHandle
0x1403e4152  test    eax, eax
0x1403e4154  jnz     loc_1403E40B6
0x1403e415a  call    cs:abort
0x1403e4161  mov     eax, [rbp+var_18]
0x1403e4164  test    al, 1
0x1403e4166  jz      short loc_1403E41DB
0x1403e4168  xor     eax, 1
0x1403e416b  lea     r8, [rbp+var_38]; lpFileInformation
0x1403e416f  mov     r9d, edi; dwBufferSize
0x1403e4172  mov     [rbp+var_18], eax
0x1403e4175  xor     edx, edx; FileInformationClass
0x1403e4177  mov     rcx, rbx; hFile
0x1403e417a  call    cs:SetFileInformationByHandle
0x1403e4180  test    eax, eax
0x1403e4182  jz      short loc_1403E4132
0x1403e4184  mov     rcx, rbx
0x1403e4187  call    ?_Set_delete_flag@?A0x4361391f@@YA?AW4__std_win_error@@W4__std_fs_file_handle@@@Z
0x1403e418c  test    eax, eax
0x1403e418e  jnz     short loc_1403E4199
0x1403e4190  mov     byte ptr [rbp+var_50], 1
0x1403e4194  mov     dword ptr [rbp+var_50+4], esi
0x1403e4197  jmp     short loc_1403E413F
0x1403e4199  cmp     eax, 5
0x1403e419c  jnz     short loc_1403E41CC
0x1403e419e  or      [rbp+var_18], 1
0x1403e41a2  lea     r8, [rbp+var_38]; lpFileInformation
0x1403e41a6  mov     r9d, edi; dwBufferSize
0x1403e41a9  xor     edx, edx; FileInformationClass
0x1403e41ab  mov     rcx, rbx; hFile
0x1403e41ae  call    cs:SetFileInformationByHandle
0x1403e41b4  mov     byte ptr [rbp+var_50], sil
0x1403e41b8  test    eax, eax
0x1403e41ba  jz      loc_1403E4136
0x1403e41c0  mov     dword ptr [rbp+var_50+4], 5
0x1403e41c7  jmp     loc_1403E413F
0x1403e41cc  mov     byte ptr [rbp+var_50], sil
0x1403e41d0  call    cs:__imp_GetLastError
0x1403e41d6  jmp     loc_1403E40F7
0x1403e41db  mov     byte ptr [rbp+var_50], sil
0x1403e41df  jmp     short loc_1403E41C0
0x1403e41e1  mov     byte ptr [rbp+var_50], sil
0x1403e41e5  sub     eax, 2
0x1403e41e8  jz      short loc_1403E4205
0x1403e41ea  sub     eax, 1
0x1403e41ed  jz      short loc_1403E4205
0x1403e41ef  sub     eax, 32h ; '2'
0x1403e41f2  jz      short loc_1403E4205
0x1403e41f4  sub     eax, 0Bh
0x1403e41f7  jz      short loc_1403E4205
0x1403e41f9  sub     eax, 3Bh ; ';'
0x1403e41fc  jz      short loc_1403E4205
0x1403e41fe  cmp     eax, 90h
0x1403e4203  jnz     short loc_1403E4207
0x1403e4205  mov     ecx, esi
0x1403e4207  mov     dword ptr [rbp+var_50+4], ecx
0x1403e420a  jmp     loc_1403E409E
0x1403e420f  call    cs:abort
```
