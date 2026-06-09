# CheckToSeeIfSameDir

- ea: `0x14006d8b0`
- end: `0x14006ddd6`
- name: `CheckToSeeIfSameDir`
- size: `1318`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, wchar_t *String2)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000b9bc`
- `0x14001e140`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14000c450`
- `0x14006a3a4`
- `0x14006d8b0`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x14006d952`
- `KERNEL32!GetTempFileNameW` at `0x14006d952`
- `KERNEL32!GetFileInformationByHandle` at `0x14006dc88`
- `KERNEL32!GetFileInformationByHandle` at `0x14006dcd7`
- `KERNEL32!GetFileInformationByHandle` at `0x14006dc88`
- `KERNEL32!GetFileInformationByHandle` at `0x14006dcd7`
- `KERNEL32!GetLastError` at `0x14006d95c`
- `KERNEL32!GetLastError` at `0x14006d9ca`
- `KERNEL32!GetLastError` at `0x14006db3f`
- `KERNEL32!GetLastError` at `0x14006db8b`
- `KERNEL32!GetLastError` at `0x14006dbf6`
- `KERNEL32!GetLastError` at `0x14006dc92`
- `KERNEL32!GetLastError` at `0x14006dce1`
- `KERNEL32!GetLastError` at `0x14006dd80`
- `KERNEL32!GetLastError` at `0x14006d95c`
- `KERNEL32!GetLastError` at `0x14006d9ca`
- `KERNEL32!GetLastError` at `0x14006db3f`
- `KERNEL32!GetLastError` at `0x14006db8b`
- `KERNEL32!GetLastError` at `0x14006dbf6`
- `KERNEL32!GetLastError` at `0x14006dc92`
- `KERNEL32!GetLastError` at `0x14006dce1`
- `KERNEL32!GetLastError` at `0x14006dd80`
- `KERNEL32!CloseHandle` at `0x14006db69`
- `KERNEL32!CloseHandle` at `0x14006dbbd`
- `KERNEL32!CloseHandle` at `0x14006db69`
- `KERNEL32!CloseHandle` at `0x14006dbbd`
- `KERNEL32!DeleteFileW` at `0x14006dd5e`
- `KERNEL32!DeleteFileW` at `0x14006dd5e`
- `msvcrt!wcsrchr` at `0x14006da1e`
- `msvcrt!wcsrchr` at `0x14006da1e`
- `msvcrt!_wcsicmp` at `0x14006d929`
- `msvcrt!_wcsicmp` at `0x14006d929`

## pseudocode

```c
int __fastcall CheckToSeeIfSameDir(LPCWSTR lpPathName, wchar_t *String2, _DWORD *a3)
{
  int result; // eax
  __int64 v7; // r9
  DWORD v8; // eax
  int v9; // ebx
  void *File; // r15
  DWORD LastError; // eax
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r14
  unsigned __int16 *v15; // rax
  WCHAR *v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rcx
  WCHAR *v19; // rcx
  int v20; // eax
  __int64 v21; // r9
  DWORD v22; // eax
  DWORD v23; // eax
  CMapDeviceId *v24; // rcx
  __int64 v25; // rdx
  char v26; // al
  struct _BY_HANDLE_FILE_INFORMATION v27; // [rsp+40h] [rbp-C0h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-88h] BYREF
  WCHAR TempFileName[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName[520]; // [rsp+2C0h] [rbp+1C0h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  }
  result = _wcsicmp(lpPathName, String2);
  if ( !result )
  {
    *a3 = 1;
    return result;
  }
  if ( GetTempFileNameW(lpPathName, L"TST", 0, TempFileName) )
  {
    File = (void *)InternalSafeCreateFile(TempFileName, 0, 3u, v7, 3u, 0);
    if ( File == (void *)-1LL )
    {
      LastError = GetLastError();
      v9 = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_71:
        if ( !DeleteFileW(TempFileName)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = GetLastError();
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            73,
            (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
            (unsigned int)TempFileName,
            v26);
        }
        return v9;
      }
      v13 = 65;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, LastError);
      goto LABEL_71;
    }
    v14 = -1;
    v15 = wcsrchr(TempFileName, 0x5Cu);
    v16 = FileName;
    v17 = 520;
    v18 = 2147483646;
    do
    {
      if ( !v18 )
        break;
      if ( !*String2 )
        break;
      *v16++ = *String2++;
      --v18;
      --v17;
    }
    while ( v17 );
    v19 = v16 - 1;
    if ( v17 )
      v19 = v16;
    *v19 = 0;
    if ( !v17 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 122);
      }
      v9 = 122;
      goto LABEL_41;
    }
    v20 = StringCchCatW(FileName, 520, v15);
    LOWORD(v9) = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
          (unsigned __int16)v20);
      }
      v9 = (unsigned __int16)v9;
      goto LABEL_41;
    }
    v14 = InternalSafeCreateFile(FileName, 0, 3u, v21, 3u, 0);
    if ( v14 == -1 )
    {
      v22 = GetLastError();
      v9 = v22;
      if ( v22 != 8 && v22 != 14 )
      {
        v9 = 0;
LABEL_40:
        *a3 = 0;
        goto LABEL_41;
      }
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      v25 = 68;
    }
    else
    {
      memset(&FileInformation, 0, sizeof(FileInformation));
      memset(&v27, 0, sizeof(v27));
      if ( GetFileInformationByHandle(File, &FileInformation) )
      {
        if ( GetFileInformationByHandle((HANDLE)v14, &v27) )
        {
          v9 = 0;
          if ( FileInformation.nFileIndexHigh != v27.nFileIndexHigh
            || FileInformation.nFileIndexLow != v27.nFileIndexLow
            || FileInformation.dwVolumeSerialNumber != v27.dwVolumeSerialNumber )
          {
            goto LABEL_40;
          }
          *a3 = 1;
LABEL_41:
          if ( !CloseHandle(File)
            && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v23 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v23);
          }
          if ( v14 == -1
            || CloseHandle((HANDLE)v14)
            || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_71;
          }
          LastError = GetLastError();
          v12 = WPP_GLOBAL_Control;
          v13 = 72;
          goto LABEL_17;
        }
        v22 = GetLastError();
        v9 = v22;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_41;
        }
        v25 = 70;
      }
      else
      {
        v22 = GetLastError();
        v9 = v22;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_41;
        }
        v25 = 69;
      }
    }
    WPP_SF_d(*((_QWORD *)v24 + 2), v25, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v22);
    goto LABEL_41;
  }
  v8 = GetLastError();
  v9 = v8;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v8);
  }
  return v9;
}

```

## disassembly

```asm
0x14006d8b0  mov     [rsp-8+arg_18], rbx
0x14006d8b5  push    rbp
0x14006d8b6  push    rsi
0x14006d8b7  push    rdi
0x14006d8b8  push    r12
0x14006d8ba  push    r13
0x14006d8bc  push    r14
0x14006d8be  push    r15
0x14006d8c0  lea     rbp, [rsp-5E0h]
0x14006d8c8  sub     rsp, 6E0h
0x14006d8cf  mov     rax, cs:__security_cookie
0x14006d8d6  xor     rax, rsp
0x14006d8d9  mov     [rbp+610h+var_40], rax
0x14006d8e0  mov     rdi, r8
0x14006d8e3  mov     rsi, rdx
0x14006d8e6  mov     rbx, rcx
0x14006d8e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d8f0  lea     r14, WPP_GLOBAL_Control
0x14006d8f7  mov     r12d, 2
0x14006d8fd  cmp     rcx, r14
0x14006d900  jz      short loc_14006D923
0x14006d902  test    [rcx+1Ch], r12b
0x14006d906  jz      short loc_14006D923
0x14006d908  cmp     byte ptr [rcx+19h], 5
0x14006d90c  jb      short loc_14006D923
0x14006d90e  mov     rcx, [rcx+10h]
0x14006d912  lea     edx, [r12+3Dh]
0x14006d917  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006d91e  call    WPP_SF_
0x14006d923  mov     rdx, rsi; String2
0x14006d926  mov     rcx, rbx; String1
0x14006d929  call    cs:__imp__wcsicmp
0x14006d92f  xor     r13d, r13d
0x14006d932  test    eax, eax
0x14006d934  jnz     short loc_14006D941
0x14006d936  mov     dword ptr [rdi], 1
0x14006d93c  jmp     loc_14006DDAC
0x14006d941  lea     r9, [rbp+610h+TempFileName]; lpTempFileName
0x14006d945  xor     r8d, r8d; uUnique
0x14006d948  lea     rdx, PrefixString; "TST"
0x14006d94f  mov     rcx, rbx; lpPathName
0x14006d952  call    cs:__imp_GetTempFileNameW
0x14006d958  test    eax, eax
0x14006d95a  jnz     short loc_14006D9A5
0x14006d95c  call    cs:__imp_GetLastError
0x14006d962  mov     ebx, eax
0x14006d964  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d96b  cmp     rcx, r14
0x14006d96e  jz      loc_14006DDAA
0x14006d974  test    [rcx+1Ch], r12b
0x14006d978  jz      loc_14006DDAA
0x14006d97e  cmp     [rcx+19h], r12b
0x14006d982  jb      loc_14006DDAA
0x14006d988  mov     rcx, [rcx+10h]
0x14006d98c  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006d993  mov     edx, 40h ; '@'
0x14006d998  mov     r9d, eax
0x14006d99b  call    WPP_SF_d
0x14006d9a0  jmp     loc_14006DDAA
0x14006d9a5  mov     eax, 3
0x14006d9aa  mov     [rsp+710h+var_6E8], r13d; int
0x14006d9af  mov     r8d, eax; dwShareMode
0x14006d9b2  mov     [rsp+710h+var_6F0], eax; DWORD
0x14006d9b6  xor     edx, edx; dwDesiredAccess
0x14006d9b8  lea     rcx, [rbp+610h+TempFileName]; lpFileName
0x14006d9bc  call    InternalSafeCreateFile
0x14006d9c1  mov     r15, rax
0x14006d9c4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006d9c8  jnz     short loc_14006DA12
0x14006d9ca  call    cs:__imp_GetLastError
0x14006d9d0  mov     ebx, eax
0x14006d9d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d9d9  cmp     rcx, r14
0x14006d9dc  jz      loc_14006DD5A
0x14006d9e2  test    [rcx+1Ch], r12b
0x14006d9e6  jz      loc_14006DD5A
0x14006d9ec  cmp     [rcx+19h], r12b
0x14006d9f0  jb      loc_14006DD5A
0x14006d9f6  lea     edx, [r15+42h]
0x14006d9fa  mov     rcx, [rcx+10h]
0x14006d9fe  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006da05  mov     r9d, eax
0x14006da08  call    WPP_SF_d
0x14006da0d  jmp     loc_14006DD5A
0x14006da12  or      r14, 0FFFFFFFFFFFFFFFFh
0x14006da16  lea     rcx, [rbp+610h+TempFileName]; Str
0x14006da1a  lea     edx, [r14+5Dh]; Ch
0x14006da1e  call    cs:__imp_wcsrchr
0x14006da24  mov     r10d, 208h
0x14006da2a  lea     rdx, [rbp+610h+FileName]
0x14006da31  mov     ebx, r10d
0x14006da34  mov     ecx, 7FFFFFFEh
0x14006da39  test    rcx, rcx
0x14006da3c  jz      short loc_14006DA5B
0x14006da3e  movzx   r8d, word ptr [rsi]
0x14006da42  test    r8w, r8w
0x14006da46  jz      short loc_14006DA5B
0x14006da48  mov     [rdx], r8w
0x14006da4c  add     rsi, r12
0x14006da4f  add     rdx, r12
0x14006da52  dec     rcx
0x14006da55  sub     rbx, 1
0x14006da59  jnz     short loc_14006DA39
0x14006da5b  test    rbx, rbx
0x14006da5e  lea     rcx, [rdx-2]
0x14006da62  cmovnz  rcx, rdx
0x14006da66  mov     [rcx], r13w
0x14006da6a  jnz     short loc_14006DABF
0x14006da6c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006da73  lea     rdi, WPP_GLOBAL_Control
0x14006da7a  cmp     rcx, rdi
0x14006da7d  jz      short loc_14006DAB0
0x14006da7f  test    [rcx+1Ch], r12b
0x14006da83  jz      short loc_14006DAB0
0x14006da85  cmp     [rcx+19h], r12b
0x14006da89  jb      short loc_14006DAB0
0x14006da8b  mov     rcx, [rcx+10h]
0x14006da8f  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006da96  mov     rax, rbx
0x14006da99  mov     edx, 42h ; 'B'
0x14006da9e  neg     rax
0x14006daa1  sbb     r9d, r9d
0x14006daa4  not     r9d
0x14006daa7  and     r9d, 7Ah
0x14006daab  call    WPP_SF_d
0x14006dab0  neg     rbx
0x14006dab3  sbb     ebx, ebx
0x14006dab5  not     ebx
0x14006dab7  and     ebx, 7Ah
0x14006daba  jmp     loc_14006DB66
0x14006dabf  mov     r8, rax; unsigned __int16 *
0x14006dac2  lea     rcx, [rbp+610h+FileName]; unsigned __int16 *
0x14006dac9  mov     rdx, r10; unsigned __int64
0x14006dacc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006dad1  mov     ebx, eax
0x14006dad3  test    eax, eax
0x14006dad5  jns     short loc_14006DB14
0x14006dad7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dade  lea     rdi, WPP_GLOBAL_Control
0x14006dae5  cmp     rcx, rdi
0x14006dae8  jz      short loc_14006DB0F
0x14006daea  test    [rcx+1Ch], r12b
0x14006daee  jz      short loc_14006DB0F
0x14006daf0  cmp     [rcx+19h], r12b
0x14006daf4  jb      short loc_14006DB0F
0x14006daf6  mov     rcx, [rcx+10h]
0x14006dafa  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006db01  movzx   r9d, bx
0x14006db05  mov     edx, 43h ; 'C'
0x14006db0a  call    WPP_SF_d
0x14006db0f  movzx   ebx, bx
0x14006db12  jmp     short loc_14006DB66
0x14006db14  mov     r8d, 3; dwShareMode
0x14006db1a  mov     [rsp+710h+var_6E8], r13d; int
0x14006db1f  xor     edx, edx; dwDesiredAccess
0x14006db21  mov     [rsp+710h+var_6F0], r8d; DWORD
0x14006db26  lea     rcx, [rbp+610h+FileName]; lpFileName
0x14006db2d  call    InternalSafeCreateFile
0x14006db32  mov     r14, rax
0x14006db35  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006db39  jnz     loc_14006DC55
0x14006db3f  call    cs:__imp_GetLastError
0x14006db45  mov     ebx, eax
0x14006db47  cmp     eax, 8
0x14006db4a  jz      loc_14006DC0D
0x14006db50  cmp     eax, 0Eh
0x14006db53  jz      loc_14006DC0D
0x14006db59  mov     ebx, r13d
0x14006db5c  mov     [rdi], r13d
0x14006db5f  lea     rdi, WPP_GLOBAL_Control
0x14006db66  mov     rcx, r15; hObject
0x14006db69  call    cs:__imp_CloseHandle
0x14006db6f  test    eax, eax
0x14006db71  jnz     short loc_14006DBB0
0x14006db73  mov     rax, cs:WPP_GLOBAL_Control
0x14006db7a  cmp     rax, rdi
0x14006db7d  jz      short loc_14006DBB0
0x14006db7f  test    [rax+1Ch], r12b
0x14006db83  jz      short loc_14006DBB0
0x14006db85  cmp     [rax+19h], r12b
0x14006db89  jb      short loc_14006DBB0
0x14006db8b  call    cs:__imp_GetLastError
0x14006db91  mov     rcx, cs:WPP_GLOBAL_Control
0x14006db98  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006db9f  mov     edx, 47h ; 'G'
0x14006dba4  mov     r9d, eax
0x14006dba7  mov     rcx, [rcx+10h]
0x14006dbab  call    WPP_SF_d
0x14006dbb0  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14006dbb4  jz      loc_14006DD53
0x14006dbba  mov     rcx, r14; hObject
0x14006dbbd  call    cs:__imp_CloseHandle
0x14006dbc3  test    eax, eax
0x14006dbc5  jnz     loc_14006DD53
0x14006dbcb  mov     rax, cs:WPP_GLOBAL_Control
0x14006dbd2  lea     r14, WPP_GLOBAL_Control
0x14006dbd9  cmp     rax, r14
0x14006dbdc  jz      loc_14006DD5A
0x14006dbe2  test    [rax+1Ch], r12b
0x14006dbe6  jz      loc_14006DD5A
0x14006dbec  cmp     [rax+19h], r12b
0x14006dbf0  jb      loc_14006DD5A
0x14006dbf6  call    cs:__imp_GetLastError
0x14006dbfc  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dc03  mov     edx, 48h ; 'H'
0x14006dc08  jmp     loc_14006D9FA
0x14006dc0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dc14  lea     rdi, WPP_GLOBAL_Control
0x14006dc1b  cmp     rcx, rdi
0x14006dc1e  jz      loc_14006DB66
0x14006dc24  test    [rcx+1Ch], r12b
0x14006dc28  jz      loc_14006DB66
0x14006dc2e  cmp     [rcx+19h], r12b
0x14006dc32  jb      loc_14006DB66
0x14006dc38  mov     edx, 44h ; 'D'
0x14006dc3d  mov     rcx, [rcx+10h]
0x14006dc41  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006dc48  mov     r9d, eax
0x14006dc4b  call    WPP_SF_d
0x14006dc50  jmp     loc_14006DB66
0x14006dc55  xorps   xmm0, xmm0
0x14006dc58  lea     rdx, [rsp+710h+FileInformation]; lpFileInformation
0x14006dc5d  xorps   xmm1, xmm1
0x14006dc60  xor     eax, eax
0x14006dc62  mov     rcx, r15; hFile
0x14006dc65  mov     [rbp+610h+FileInformation.nFileIndexLow], eax
0x14006dc68  movups  xmmword ptr [rsp+710h+FileInformation.dwFileAttributes], xmm0
0x14006dc6d  mov     [rsp+710h+var_6D0.nFileIndexLow], eax
0x14006dc71  movups  xmmword ptr [rbp+610h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x14006dc75  movups  xmmword ptr [rbp+610h+FileInformation.nFileSizeHigh], xmm0
0x14006dc79  movups  xmmword ptr [rsp+710h+var_6D0.dwFileAttributes], xmm1
0x14006dc7e  movups  xmmword ptr [rsp+710h+var_6D0.ftLastAccessTime.dwHighDateTime], xmm1
0x14006dc83  movups  xmmword ptr [rsp+710h+var_6D0.nFileSizeHigh], xmm1
0x14006dc88  call    cs:__imp_GetFileInformationByHandle
0x14006dc8e  test    eax, eax
0x14006dc90  jnz     short loc_14006DCCF
0x14006dc92  call    cs:__imp_GetLastError
0x14006dc98  mov     ebx, eax
0x14006dc9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dca1  lea     rdi, WPP_GLOBAL_Control
0x14006dca8  cmp     rcx, rdi
0x14006dcab  jz      loc_14006DB66
0x14006dcb1  test    [rcx+1Ch], r12b
0x14006dcb5  jz      loc_14006DB66
0x14006dcbb  cmp     [rcx+19h], r12b
0x14006dcbf  jb      loc_14006DB66
0x14006dcc5  mov     edx, 45h ; 'E'
0x14006dcca  jmp     loc_14006DC3D
0x14006dccf  lea     rdx, [rsp+710h+var_6D0]; lpFileInformation
0x14006dcd4  mov     rcx, r14; hFile
0x14006dcd7  call    cs:__imp_GetFileInformationByHandle
0x14006dcdd  test    eax, eax
0x14006dcdf  jnz     short loc_14006DD1E
0x14006dce1  call    cs:__imp_GetLastError
0x14006dce7  mov     ebx, eax
0x14006dce9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dcf0  lea     rdi, WPP_GLOBAL_Control
0x14006dcf7  cmp     rcx, rdi
0x14006dcfa  jz      loc_14006DB66
0x14006dd00  test    [rcx+1Ch], r12b
0x14006dd04  jz      loc_14006DB66
0x14006dd0a  cmp     [rcx+19h], r12b
0x14006dd0e  jb      loc_14006DB66
0x14006dd14  mov     edx, 46h ; 'F'
0x14006dd19  jmp     loc_14006DC3D
0x14006dd1e  mov     eax, [rsp+710h+var_6D0.nFileIndexHigh]
0x14006dd22  mov     ebx, r13d
0x14006dd25  cmp     [rbp+610h+FileInformation.nFileIndexHigh], eax
0x14006dd28  jnz     loc_14006DB5C
0x14006dd2e  mov     eax, [rsp+710h+var_6D0.nFileIndexLow]
0x14006dd32  cmp     [rbp+610h+FileInformation.nFileIndexLow], eax
0x14006dd35  jnz     loc_14006DB5C
0x14006dd3b  mov     eax, [rsp+710h+var_6D0.dwVolumeSerialNumber]
0x14006dd3f  cmp     [rbp+610h+FileInformation.dwVolumeSerialNumber], eax
0x14006dd42  jnz     loc_14006DB5C
0x14006dd48  mov     dword ptr [rdi], 1
0x14006dd4e  jmp     loc_14006DB5F
0x14006dd53  lea     r14, WPP_GLOBAL_Control
0x14006dd5a  lea     rcx, [rbp+610h+TempFileName]; lpFileName
0x14006dd5e  call    cs:__imp_DeleteFileW
0x14006dd64  test    eax, eax
0x14006dd66  jnz     short loc_14006DDAA
0x14006dd68  mov     rax, cs:WPP_GLOBAL_Control
0x14006dd6f  cmp     rax, r14
0x14006dd72  jz      short loc_14006DDAA
0x14006dd74  test    [rax+1Ch], r12b
0x14006dd78  jz      short loc_14006DDAA
0x14006dd7a  cmp     [rax+19h], r12b
0x14006dd7e  jb      short loc_14006DDAA
0x14006dd80  call    cs:__imp_GetLastError
0x14006dd86  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dd8d  lea     r9, [rbp+610h+TempFileName]
0x14006dd91  mov     edx, 49h ; 'I'
0x14006dd96  mov     [rsp+710h+var_6F0], eax
0x14006dd9a  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006dda1  mov     rcx, [rcx+10h]
0x14006dda5  call    WPP_SF_Sd
0x14006ddaa  mov     eax, ebx
0x14006ddac  mov     rcx, [rbp+610h+var_40]
0x14006ddb3  xor     rcx, rsp; StackCookie
  ... truncated ...
```
